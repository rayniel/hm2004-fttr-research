# HM2004-DU FTTR Research

H3C HM2004-DU hardware and firmware research materials, including board
references, FTTR master-OLT analysis, firmware artifacts, and provenance
records. This repository is a research archive, not a ready-to-build OpenWrt
feed or a complete firmware project.

## Contents

| Path | Purpose |
| --- | --- |
| [`boards/hm2004/`](boards/hm2004/) | HM2004-DU board DTS reference |
| [`docs/hardware/`](docs/hardware/) | Board and platform notes |
| [`docs/fttr/`](docs/fttr/) | FTTR/FMCS architecture and extracted reference documents |
| [`docs/firmware/`](docs/firmware/) | Firmware artifact inventory |
| [`artifacts/original/`](artifacts/original/) | Original source and firmware archives |
| [`artifacts/firmware/`](artifacts/firmware/) | Extracted firmware samples, grouped by subsystem |
| [`manifests/SHA256SUMS`](manifests/SHA256SUMS) | SHA-256 checksums for archived inputs and retained artifacts |

## Scope and status

The reference package contains FMCS driver, userspace, LuCI, and OpenWrt
integration sources alongside reverse-engineering notes. It is retained as an
original archive and is not maintained or represented here as a complete,
working port. The extracted documents under `docs/fttr/reference/` are there
for search and reading; the archive remains the source copy.

Buildable features should be developed and released separately, for example in
a dedicated OpenWrt feed repository. This research repository does not promise
that its binaries are suitable for installation, redistribution, or use on
other device revisions.

## Handling and redistribution

Firmware samples and vendor-derived archives are retained for research. Their
individual redistribution terms have not been independently verified. Check
the applicable rights and provenance before publishing, mirroring, or
redistributing these files. See [`docs/provenance.md`](docs/provenance.md).

## Integrity

Verify listed files from the repository root with:

```sh
sha256sum -c manifests/SHA256SUMS
```
