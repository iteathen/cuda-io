# CUDA-IO Status

**Updated:** 2026-09-06

**Architecture/ownership:** accepted independent GPU I/O semantic owner under SPEC-0001.
**Production implementation/API:** not authorized / none.
**Native/provider support:** none claimed.

## Current work

- #1 ownership/bootstrap authority — completed.
- #2 repository-control/protected-main alignment — completed; `main` is protected and the selected CUDA-family settings were read back.
- #3 is the current bounded source/sink and direct-storage activation roadmap; it remains planning/assessment authority, not a production specification.

## Next executable decision

Select one concrete consumer-backed bounded source/sink profile and define a staged-path reference for semantic comparison before any direct-storage realization. Production implementation still requires an accepted specification with finite ranges, lifecycle, failure and cleanup semantics.

CUDA-JS retains native memory/DMA/registration/provider lifecycle and any future bounded cuFile/GDS mechanism. I/O-specific source/sink, buffering, chunking and backpressure semantics remain CUDA-IO. `iteathen/CUDA-MM` is now the accepted **reserved architecture/ownership home** for reusable cross-domain physical memory-management policy, but it is not a current CUDA-IO dependency: CUDA-MM #3/#4 and a separate bounded production contract must activate it first. Generic placement/spill/pool/migration policy may route there later; I/O-specific chunk/out-of-core/source policy remains here. GPUDirect-RDMA/network communication semantics route to `cuda-comm`; dataset/filesystem/database meaning remains outside CUDA-IO.

## Governance

Protected-main and repository-setting alignment is complete. No local CI workflow currently exists, so no required status-check name is fabricated.

No roadmap entry, provider availability, CUDA-MM repository existence or completed governance bootstrap is production implementation authority.
