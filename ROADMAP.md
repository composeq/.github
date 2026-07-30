# CompoSeq Roadmap

Our roadmap follows a sequence of themes following the flow of data. It covers the shared interfaces and the work spanning projects. Individual member projects keep their own roadmaps.


## Transport: formats in, Arrow out

One consistent interface and schema to a genomic file format. Oxbow already ships Arrow-native readers, and polars-bio's datafusion-bio-formats layer presents the same formats to query engines as async, partitioned table providers with cloud-native reads.

- Unified Arrow schema specification (sequence, alignment, variant, annotation), which also define a Parquet on-disk layout
- Convergence of oxbow and datafusion-bio-formats on a single shared parser backend
- Zero-copy handoff via the Arrow C Stream and PyCapsule interfaces
- Matrix and sparse modalities (pairs, cooler/2D contact data) under the same schema model *(exploring)*


## Execution: genomic spatial kernels

The operations we spend time on (spatial joins and rasterization) defined and implemented correctly, fast, and callable from the engines people already use.

- Interval overlap and nearest joins
- Operator-primitive specification and conformance suite: coordinate conventions, nearest-feature tie-breaking, coverage/pileup aggregation, strand handling
- Spatial-join algebra completion: cluster, merge, and transitive closures
- Rasterization and pileup kernels, run-length-encoded and dense output, spanning coverage, read pileup, point-event histograms, variant one-hots, and interval masks
- Kernels exposed in DataFusion as scalar UDFs, aggregate UDAFs, and table-valued UTVFs
- Kernels exposed in DuckDB via UDF/UDAF/UTVF bindings *(exploring)*
- Hardware acceleration for the rasterization inner loop *(exploring)*


## Composability: GIQL

A portable genomic query dialect that transpiles to multiple backends, so a query outlives the engine it was written against. The [prototype](https://github.com/abdenlab/giql) demonstrates feasibility but has no external users yet; the direction is to harden it into a governed specification.

- GIQL specification v1.0
- Conformance suite, runnable by third parties against their own backend
- Transpilation targets: standard SQL as the naive correctness reference, then DuckDB SQL and datafusion-bio UDFs
- Benchmark methodology and published results


## Tensors: Arrow to GPU without unnecessary intermediates

- Zero-copy Arrow to tensor loader via DLPack, framework-agnostic across PyTorch, JAX, and NumPy
- tangermeme and bpnet-lite migrated to the shared loader, with their file-based APIs kept as a compatibility layer
- ENCODE-compendium reference workload (~10k tracks, from BAM/BED, cloud-only) and gnomAD-scale variant-effect scoring *(exploring)*
- Inverse operation, tensor-to-Arrow, for inference outputs feeding analysis, storage, and visualization *(exploring)*

The loader must sustain a data rate exceeding the model's forward-backward pass, so training stays compute-bound rather than I/O-bound. If it doesn't, the loader has failed, and we will report it as a failure. Stretch goal: beat the forward pass alone, so inference is compute-bound too.


## Agents: declarative interfaces, honestly evaluated

Agents should operate genomic data through inspectable, portable queries instead of generating brittle shell pipelines against a dozen idiosyncratic tools.

- Locally-hosted MCP services and skills exposing the query and transport layers, with progressive disclosure so agents discover capability without loading everything into context
- Agent skills for bpnet-lite and tangermeme model training that invoke CompoSeq processing transparently
- A harness for generating and validating GIQL transpilation targets for new engines *(exploring)*
- Evaluation on external agent benchmarks: BioAgent Bench, PromptBio-Bench, BioMysteryBench *(exploring)*

We evaluate against benchmarks we did not write, and publish per-task results including the tasks we lose. The bar is parity with the existing tool ecosystem at a lower budget, not beating everyone.
