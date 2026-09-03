# CUDA-IO Project Charter

**Status:** Accepted architecture after bootstrap integration; production implementation not authorized.

## Purpose

Own reusable provider-neutral GPU I/O semantics without turning CUDA-JS into a storage framework or absorbing downstream data meaning.

## Owns, when separately accepted

- data-source/data-sink and file/storage-region identity;
- bounded read/write/streaming plans;
- offset/range/chunking and semantic alignment requirements;
- completion, failure, retry/backpressure and staged-vs-direct equivalence;
- finite storage-to-GPU and GPU-to-storage pipeline meaning.

## Does not own

Filesystem/application dataset semantics; model/checkpoint/tablebase/book meaning; database/table semantics; CUDA memory/views/transfers/DMA/provider lifecycle; cuFile/GDS handles; or network/RDMA communication semantics.

## Provider boundary

CUDA-JS owns the lower memory registration, DMA, transfer-operation and bounded cuFile/GDS provider mechanisms when selected. CUDA-IO owns provider-neutral I/O meaning above them. `cuda-comm` owns reusable network/RDMA communication semantics.

## Dependency direction

`cuda-io -> public cuda-js`.

## Activation gate

Issue #3 selects a concrete reusable profile and staged baseline. Production source/API requires an accepted bounded specification and independent byte/lifecycle evidence.

## Non-goals

Filesystem framework, storage engine, database, product caching policy, or native provider implementation here.