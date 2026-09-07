# Repository context: cuda-io

Universal engineering and design guidance comes from the account-global `AGENTS.md`.

## Mission and ownership

CUDA-IO owns reusable GPU data-source/data-sink and storage-I/O semantics when accepted: source/sink and region identity, bounded read/write/stream plans, offsets/ranges/chunking, completion/failure/backpressure, and staged-vs-direct equivalence.

CUDA-JS owns CUDA memory/transfer/provider mechanisms. Filesystem, dataset, database, tablebase, checkpoint/model, and network-communication semantics remain with their natural owners.

## Local routing

Accepted `docs/decisions/`, `docs/specs/`, repository status/roadmap, and current issues own local implementation/activation truth.

## Local constraints

Dependency direction is `cuda-io -> public cuda-js`. Maintained code uses JavaScript/ESM plus accepted Device-JS through public lower contracts; no Python, direct native/FFI/provider escape path, hand PTX, or private CUDA-JS imports.