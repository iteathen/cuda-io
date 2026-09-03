# cuda-io

Reusable, application-neutral GPU storage/data-source/data-sink semantics above CUDA-JS mechanisms.

**Status:** architecture/governance bootstrap; production implementation not authorized.

CUDA-IO owns provider-neutral source/sink/region/transfer meaning. CUDA-JS remains the owner of memory registration, DMA, transfer operations and an eventual bounded GPUDirect Storage/cuFile provider mechanism.

GPUDirect RDMA/network communication belongs through `cuda-comm`, not this repository.

Tracking: #1 ownership/bootstrap, #2 repository controls, #3 semantic roadmap.

No package/API/provider/support/performance claim exists yet.