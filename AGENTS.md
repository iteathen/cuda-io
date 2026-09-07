# CUDA-IO Agent Entry Point

Read before changing the repository.

Authority: explicit owner instruction -> this file -> accepted ADRs -> accepted specs -> charter -> status/roadmap/issues.

Use `assess -> research -> reassess -> plan -> execute -> qualify -> review -> cleanup/document` and `LEGO -> SOLID -> CUPID -> KISS`.

LEGO is the outer architecture rule: ownership, universality, replaceability, scope containment, damage-limiting encapsulation, supported connection surfaces, and context containment. **The application/system is the outermost LEGO.** Its supported external inputs, outputs, commands, events, data contracts, and lifecycle entry/exit points are its public **studs/surfaces**. Large sections, subsystems, components, and large objects should preferentially compose smaller child LEGOs when that preserves cohesion; the parent owns the external responsibility and hides child topology.

A LEGO is too large when one agent cannot hold its complete authoritative working set—contract/studs/surfaces, implementation, invariants, lifecycle/resource/failure rules, tests/conformance, and immediate dependency/consumer interfaces—in focused attention with substantial headroom for reasoning and review. Context fit is a first-class boundary criterion alongside semantic, lifecycle, resource/failure, substitution, and change cohesion. When exceeded, recursively split at the strongest real seam or narrow scope; do not create arbitrary modules that duplicate truth or require cross-boundary internal knowledge. Callers connect through deliberate studs/surfaces and never drill through a parent to a private child. Inside a valid LEGO, SOLID structures responsibilities and dependency direction, CUPID shapes the implementation, and KISS removes remaining unjustified complexity; lower levels may not defeat higher ones.

CUDA-IO owns reusable GPU data-source/data-sink and storage-I/O semantics when separately accepted: source/sink and region identity, bounded read/write/stream plans, offset/range/chunking requests, completion/failure/backpressure and staged-vs-direct equivalence.

CUDA-IO does not own CUDA memory/views/DMA/provider lifecycle, cuFile/GDS handles/registration, filesystem/dataset/tablebase/checkpoint/model meaning, database semantics, or network communication. GPUDirect RDMA belongs to the communication lane; CUDA-JS owns the raw mechanism.

Dependency direction: `cuda-io -> public cuda-js`. Optional consumers retain their domain meaning.

Direct native/FFI/CUDA C++/PTX/private CUDA-JS imports or duplicated transfer/resource lifecycle are lower-layer ownership signals. Do not implement workarounds here.

Maintained code, when authorized, is JavaScript/ESM plus accepted restricted Device-JS through public lower-layer contracts. No Python, maintained native code, direct FFI/Driver access, hand PTX, or subprocess-native implementation without a successor decision.

Repository creation/roadmaps authorize no production API/source. Issue #3 is the activation roadmap; accepted specs are required before implementation. Issue #2 owns GitHub controls/protected-main alignment.

Completion requires exact-effect review, relevant qualification, cleanup and honest claim limits.

## Execution efficiency / mutation hygiene

These are **default suggestions, not mandatory sequencing rules**. Use them when they reduce uncertainty, duplication, or avoidable mutation risk. Current validated information and repository-specific authority can justify a different sequence; do not perform a step merely for procedural completeness.

- **Read before write when the read can materially improve the decision.** Reuse prior validated context when its assumptions still hold. A safe, isolated, informative write can itself be research.
- **Prefer one ownership unit at a time when that keeps reasoning and review clear.** Cross ownership boundaries deliberately when the real problem or solution spans them.
- **Introduce new mechanisms when they solve a real problem.** Avoid gratuitous machinery, not invention.
- **When state is unexpected, stop and assess before acting.** Then choose whether to preserve it, repair forward, or roll back; rollback is not the default.
- **Qualify proportionally.** Validate before propagation when remaining uncertainty would become meaningfully more expensive. For simple, well-understood, mechanical changes, propagate then qualify once when that is cheaper and equally sound.
- **Reuse valid evidence and established conclusions.** Do not repeat research or validation solely to satisfy process form.
- Prefer the path that uses available information to reduce uncertainty and rework at reasonable cost while preserving correctness, ownership, recoverability, and honest evidence.
