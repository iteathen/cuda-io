# ADR-0001: Independent GPU I/O Semantic Owner

**Status:** Accepted
**Date:** 2026-09-02

## Context

GPU-resident applications may need staged or direct storage paths, but file/region/read-write/completion meaning is not CUDA runtime vocabulary and should not be duplicated in models, data systems, tablebases or training products. GPUDirect Storage is a lower data-movement mechanism; GPUDirect RDMA is a communication mechanism.

## Decision

`cuda-io` owns reusable provider-neutral GPU I/O semantics. CUDA-JS owns memory/DMA/transfer/provider resources. `cuda-comm` owns reusable network/RDMA communication meaning. Downstream consumers retain dataset/product semantics.

## Deletion test

Deleting any consumer leaves CUDA-IO coherent; deleting CUDA-IO leaves CUDA-JS coherent as a generic runtime.

## Implementation gate

Issue #3 must select a bounded consumer-backed profile and staged-path reference before any production source/API. Native GDS/cuFile work remains lower-layer authority.

## Consequences

Direct-storage acceleration can evolve without defining the public I/O meaning, and downstream products do not need to recreate GPU transfer semantics.