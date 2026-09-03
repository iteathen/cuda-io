# CUDA-IO Agent Entry Point

Read before changing the repository.

Authority: explicit owner instruction -> this file -> accepted ADRs -> accepted specs -> charter -> status/roadmap/issues.

Use `assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document` and `LEGO -> SOLID -> CUPID -> KISS`.

CUDA-IO owns reusable GPU data-source/data-sink and storage-I/O semantics when separately accepted: source/sink and region identity, bounded read/write/stream plans, offset/range/chunking requests, completion/failure/backpressure and staged-vs-direct equivalence.

CUDA-IO does not own CUDA memory/views/DMA/provider lifecycle, cuFile/GDS handles/registration, filesystem/dataset/tablebase/checkpoint/model meaning, database semantics, or network communication. GPUDirect RDMA belongs to the communication lane; CUDA-JS owns the raw mechanism.

Dependency direction: `cuda-io -> public cuda-js`. Optional consumers retain their domain meaning.

Direct native/FFI/CUDA C++/PTX/private CUDA-JS imports or duplicated transfer/resource lifecycle are lower-layer ownership signals. Do not implement workarounds here.

Maintained code, when authorized, is JavaScript/ESM plus accepted restricted Device-JS through public lower-layer contracts. No Python, maintained native code, direct FFI/Driver access, hand PTX, or subprocess-native implementation without a successor decision.

Repository creation/roadmaps authorize no production API/source. Issue #3 is the activation roadmap; accepted specs are required before implementation. Issue #2 owns GitHub controls/protected-main alignment.

Completion requires exact-effect review, relevant qualification, cleanup and honest claim limits.