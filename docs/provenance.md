# Provenance and handling

This repository groups materials supplied for H3C HM2004-DU / FTTR research.
The original archives are kept unchanged under `artifacts/original/`; selected
files have been extracted for easier inspection and are grouped by purpose.

## Source inventory

| Repository path | Supplied source | Notes |
| --- | --- | --- |
| `artifacts/original/h3c_hm2004_du_miniolt_fpga-port.zip` | FTTR/FMCS source package | Contains implementation sources, tools, vendor-kernel artifacts, and technical documents. Retained as an archive; only its Markdown reference documents are extracted under `docs/fttr/reference/`. |
| `artifacts/original/h3c-firmware.zip` | H3C firmware archive | Source of the extracted Ethernet/MD32, FPGA, and Wi-Fi firmware samples. |
| `artifacts/original/h3c-npu.zip` | H3C NPU archive | Source of the extracted NPU files and accompanying report. |
| `boards/hm2004/an7581-h3c-hm2004-du.dts` | Separately supplied HM2004-DU DTS | Preserved as a board reference; its configuration should be treated as a research input, not independently verified hardware documentation. |

`manifests/SHA256SUMS` records checksums for original archives, the board DTS,
and extracted binary samples. Regenerate or verify the manifest whenever any
of those files are intentionally replaced.

## Redistribution and safety

The presence of a file here does not establish that it may be redistributed.
No blanket license or redistribution permission is asserted for vendor
firmware, kernel modules, FPGA bitstreams, or archived source material. Check
the rights and applicable terms for each item before making this repository
public or distributing copies.

Do not flash samples from this repository to a device without validating the
exact hardware revision, image format, and recovery procedure. Keep original
device backups before conducting firmware experiments.

## Known caveats

- The FTTR source package is an incomplete research/port snapshot, not proof of
  a complete or bootable HM2004 OpenWrt implementation.
- The NPU report is retained as supplied. Its Chinese text appears to have
  encoding damage; treat its descriptions as unverified until checked against
  the original device or source.
- The firmware archives and DTS may refer to different extraction contexts or
  revisions. The checksums establish file identity only, not compatibility.
