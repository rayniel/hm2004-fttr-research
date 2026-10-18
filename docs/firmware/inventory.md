# Firmware artifact inventory

Extracted samples are grouped by subsystem under `artifacts/firmware/`. The
original ZIP archives remain under `artifacts/original/` as the source copies.
The checksums in [`../../manifests/SHA256SUMS`](../../manifests/SHA256SUMS)
provide identity checks, not authenticity or device compatibility guarantees.

| Subsystem | Files | Source archive | Notes |
| --- | --- | --- | --- |
| FPGA | `FTTR_TOP.sbit` | `h3c-firmware.zip` | FTTR/FMCS FPGA bitstream |
| Ethernet / MD32 | `EthMD32.DSP.bin`, `EthMD32.dm.bin` | `h3c-firmware.zip` | Ethernet-related firmware samples |
| Wi-Fi | `7916_WACPU_RAM_CODE_release.bin`, `mt7916_patch_e1_hdr.bin`, `WIFI_RAM_CODE_MT7916.bin` | `h3c-firmware.zip` | MT7916/Wi-Fi firmware samples |
| NPU | `npu.ko`, `npu_data.bin`, `npu_rv32.bin`, `npu_firmware_report.md` | `h3c-npu.zip` | NPU module, data, firmware, and supplied report |

The reference package archive also contains a `vendor/vmlinux.bin` snapshot and
symbol data inside the ZIP. They have not been extracted into this inventory.

No binaries should be assumed safe to flash or load on a different model,
revision, kernel, or boot chain. See [`../provenance.md`](../provenance.md)
before redistributing any vendor-derived material.
