# Trunchbull benchmark ports

Central source repository for third-party benchmarks ported to Trunchbull's
zero-SDK benchmark authoring contract.

## Ports

| Benchmark | Location | Status |
| --- | --- | --- |
| SkateBench | [`benchmarks/skatebench`](benchmarks/skatebench) | Complete: 8 cases with upstream-compatible grading |

Each port keeps its config, eval modules, case data, upstream license, and
source provenance together:

```text
benchmarks/
└── benchmark-name/
    ├── benchmark.config.ts
    ├── evals/
    ├── README.md
    ├── LICENSE.upstream
    └── provenance.json
```

Benchmark authors do not install a Trunchbull SDK or CLI. Ports use plain
JavaScript or TypeScript configuration and declarative evaluators. Tool-bearing
ports may use Vercel AI SDK tool objects.

## Publishing a port

In Trunchbull's benchmark publishing screen, enter this repository URL and the
port's config path. For SkateBench:

```text
Repository: https://github.com/PabloG6/skatebench-trunchbull-port
Config path: benchmarks/skatebench/benchmark.config.ts
```

Tool, eval, and data paths are resolved relative to the selected config file,
which lets this repository hold multiple independent ports.

## Adding a port

1. Create `benchmarks/<benchmark-name>/`.
2. Pin the upstream repository and commit in `provenance.json`.
3. Preserve the upstream license.
4. Convert each source task into an independently scored eval case.
5. Document semantic differences and unsupported features in the port README.
6. Add the port to the table above.
