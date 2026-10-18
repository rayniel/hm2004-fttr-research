# FTTR / FMCS reference

The HM2004-DU source archive describes an FTTR master-OLT subsystem referred to
as FMCS. It includes reverse-engineering documents plus driver, userspace,
LuCI, and OpenWrt package sources. The archive is retained at
[`../../artifacts/original/h3c_hm2004_du_miniolt_fpga-port.zip`](../../artifacts/original/h3c_hm2004_du_miniolt_fpga-port.zip);
it is an incomplete development snapshot, not a complete or verified port.

For convenient reading, the following Markdown files were extracted from the
archive's `fttr-port/docs/` directory and are kept as reference copies:

- [`REVERSE_ENGINEERING.md`](reference/REVERSE_ENGINEERING.md) — hardware,
  firmware, kernel, and evidence notes.
- [`MOLT_API.md`](reference/MOLT_API.md) — recovered M-OLT service interface.
- [`SBIT_FORMAT.md`](reference/SBIT_FORMAT.md) — FPGA bitstream analysis.
- [`VENDOR_KERNEL.md`](reference/VENDOR_KERNEL.md) — vendor-kernel analysis.

These documents preserve claims made by the source package; they are not
independent verification. Check the evidence and revision assumptions before
using them to implement or modify firmware. The package's buildability limits
and open issues are described in its archive README and reference documents.
