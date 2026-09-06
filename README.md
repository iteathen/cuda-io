# CUDA-IO

CUDA-IO is a planned JavaScript library for reusable GPU storage I/O in the CUDA-JS ecosystem, intended for developers building GPU applications.

## Current state

This repository currently contains the project charter, architecture decision, development guidance, and planning records. **There is no production implementation, installable package, or public API yet.** No native-provider support or performance is claimed.

## Intended scope

The library aims to define data sources and sinks, bounded read/write plans, and staged-versus-direct transfer behavior through public CUDA-JS contracts.

Filesystem, dataset, checkpoint, and model meaning remain with consumers. Network communication belongs to CUDA-COMM; CUDA-JS supplies native transfer mechanisms.

Implementation depends on a concrete consumer need and an accepted specification. The [activation roadmap](https://github.com/iteathen/cuda-io/issues/3) describes candidate work; it is not a commitment that every proposed capability will ship.

## Start here

- [Current status](STATUS.md).
- [Project charter](docs/PROJECT_CHARTER.md) and [documentation](docs/README.md).
- [Development instructions](AGENTS.md) and [shared contribution guide](https://github.com/iteathen/.github/blob/main/CONTRIBUTING.md).
- [Private security reporting](https://github.com/iteathen/.github/blob/main/SECURITY.md).
- [License](LICENSE).
