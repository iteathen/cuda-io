# CUDA-IO specifications

**Architecture/ownership authority is accepted; no production I/O capability specification is accepted yet.**

- [`SPEC-0001-native-boundary-and-js-only-implementation.md`](SPEC-0001-native-boundary-and-js-only-implementation.md) — accepted cross-cutting rule that CUDA-IO remains JavaScript/TypeScript, CUDA-JS owns native storage/DMA/memory/provider integration, and source/sink/storage semantics remain here. This specification does not select a provider or authorize an I/O profile.

The [activation roadmap](https://github.com/iteathen/cuda-io/issues/3) organizes assessment. Production implementation must first have a bounded, consumer-backed semantic contract accepted under the [development instructions](../../AGENTS.md).

Start with the [project charter](../PROJECT_CHARTER.md) and [architecture decision](../decisions/README.md) to understand the intended scope.
