
## NPU 架构
- NPU 是一个 **RV32 协处理器核**（固件名即 `npu_rv32.bin`）。
- 启动时被加载到设备树预留内存区 `npu_binary@84000000`，基址 `0x84000000`，长度 `0x1000000`（16MB）。
- 相关内核模块/接口：`npu.ko`、`/proc/tc3162/hwnat_npu_*`、`/proc/tc3162/npu_wifi_fast`、`/proc/npu_dump_core_csr`、`/proc/npu_offload_5G`、`/sys/bus/platform/drivers/ecnt-npu`。
- dmesg 显示 `chipid=790a`。

## NPU 固件文件（已提取，md5 校验一致）
| 文件 | 路径 | 大小 | 说明 | md5 |
|---|---|---|---|---|
| npu_rv32.bin | /userfs/npu_rv32.bin | 90644 B | NPU 的 RV32 执行代码 | e2551187360799dadaea241f4973d80a |
| npu_data.bin | /userfs/npu_data.bin | 2764 B | NPU 运行参数/数据 | 18849de11feb56c008742fcb50576ecf |
| npu.ko | /lib/modules/npu.ko | 24768 B | NPU 内核驱动模块 | db43b95d4e2701516cda382ae4ad1cc3 |

其它相关：`/userfs/bin/npu_bridge_cmd`（工具）、`/usr/script/npu_cover_para.sh`、`/usr/script/npu_ixia_para.sh`。

## 分区参考（/proc/mtd）
bootloader / romfile / kernel / rootfs / tclinux(+slave) / opt0(opt1) / ubifs / private_apps / config / h3c / reservearea。
`/userfs` 为可写用户区（容纳 npu_rv32.bin、npu_data.bin 等）；`/lib/modules` 来自根文件系统。

## 想自己备份（在光猫上执行，PC 开 tftp server）
```
tftp -p -l /userfs/npu_rv32.bin -r npu_rv32.bin <PC的IP>
tftp -p -l /userfs/npu_data.bin -r npu_data.bin <PC的IP>
tftp -p -l /lib/modules/npu.ko   -r npu.ko       <PC的IP>
```
设备自带 `/usr/bin/tftp`。

## 备注
- 提取方式：通过 telnet 会话对文件做 base64 回传，再本地解码，md5 与光猫端逐一核对一致，未做任何修改。
- 若要做固件逆向/替换，建议先完整备份对应 MTD 分区（如 mtd13 `h3c`、mtd10 `ubifs`/mtd11 `private_apps`）与 `/userfs`，避免变砖。
