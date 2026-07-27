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

## Adding a port

1. Create `benchmarks/<benchmark-name>/`.
2. Pin the upstream repository and commit in `provenance.json`.
3. Preserve the upstream license.
4. Convert each source task into an independently scored eval case.
5. Document semantic differences and unsupported features in the port README.
6. Add the port to the table above.
