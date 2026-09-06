# CUDA-IO Status

**Updated:** 2026-09-05

**Architecture/governance:** independent GPU I/O semantic owner integrated.
**Production implementation/API:** not authorized / none.
**Native/provider support:** none claimed.

## Current work

- #1 established the durable ownership/bootstrap authority — completed.
- #2 tracks repository controls and protected-main alignment; `main` remains unprotected.
- #3 is the current bounded source/sink and direct-storage activation roadmap; it is planning/assessment authority, not a production specification.

## Next executable decision

Select one concrete consumer-backed bounded source/sink profile and define a staged-path reference for semantic comparison before any direct-storage realization. Production implementation still requires an accepted specification with finite ranges, lifecycle, failure and cleanup semantics.

CUDA-JS retains generic lower memory/DMA/provider lifecycle and any future cuFile mechanism ownership. GPUDirect-RDMA/network communication semantics route to `cuda-comm`; dataset/filesystem/database meaning remains outside CUDA-IO.

No roadmap entry, repository creation or completed governance bootstrap is production implementation authority.
