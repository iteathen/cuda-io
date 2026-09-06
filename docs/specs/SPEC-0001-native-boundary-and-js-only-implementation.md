# SPEC-0001: Native Boundary and JavaScript/TypeScript Implementation

**Status:** Accepted architecture/ownership authority; production I/O profiles remain separately gated.

**Version:** 1.0.0

**Owner:** CUDA-IO

**Lower authority:** `iteathen/CUDA-JS` SPEC-0032

## Purpose

CUDA-IO owns reusable GPU source/sink/storage-I/O semantics. CUDA-JS is the sole native CUDA/provider integration owner.

## Repository implementation rule

Maintained CUDA-IO source is JavaScript/TypeScript. Restricted Device-JS generation is permitted only through public CUDA-JS contracts.

CUDA-IO does not maintain C, C++, CUDA C++, PTX, direct native FFI, native addons, cuFile/GPUDirect bindings, native handles/pointers, ABI structs or platform discovery code. Native evidence may be produced externally and recorded, but native oracle/provider source is not maintained here.

A missing native mechanism routes to CUDA-JS before any local workaround.

## CUDA-IO owns

- source/sink/storage-region identity and versioning;
- offset/range/chunking semantics;
- staged/direct semantic equivalence;
- I/O completion/failure/retry meaning;
- streaming/backpressure/prefetch policy when it is specifically I/O-semantic;
- out-of-core dataflow meaning independent of native provider;
- JavaScript/TypeScript reference/conformance evidence.

## CUDA-JS owns

- native host/device/registered/mapped/managed memory mechanisms;
- native DMA/transfer/operation resources;
- GPUDirect Storage/cuFile or other native provider mechanisms if selected;
- native compatibility, handles, errors and teardown.

CUDA-IO may decide what bytes should be read/written and when I/O semantics require prefetch, but it does not implement native memory registration, DMA or storage-provider FFI.

## Memory-policy boundary

I/O-specific buffering/chunking/backpressure remains CUDA-IO-owned. Generic cross-domain allocation pooling, lifetime reuse, device/managed placement, spill/eviction or physical-memory planning does not belong here merely because I/O is a consumer; such a reusable policy requires its own JavaScript/TypeScript owner if independently justified and must consume public CUDA-JS.

## Activation gate preservation

This specification does not select a storage provider or authorize production I/O APIs. Existing staged-baseline and consumer-backed activation gates remain authoritative.

## Non-goals

No native I/O backend, no filesystem/database abstraction, no direct provider passthrough, no production capability or support claim.
