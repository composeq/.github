# CompoSeq

**Composable foundations for genomic data.**

CompoSeq is a collaborative initiative among maintainers of open-source genomics
and machine-learning libraries. We're building a shared, high-performance data
substrate that makes genomic data operate natively within the modern analytics
and ML ecosystems: Apache Arrow, DataFusion, Polars, DuckDB, PyTorch, and more.

The goal is to make genomic workflows **declarative, streaming, out-of-core, and agent-ready**.

> ⚠️ **Early and evolving.** CompoSeq is a young initiative with a clear vision and
> an active roadmap. Follow along, open issues, and get involved.


## Projects

CompoSeq coordinates work across these maintained, adopted projects (each lives in
its home organization):

- **[oxbow](https://github.com/abdenlab/oxbow)** — a format bridge that translates
  conventional genomic file formats into Apache Arrow record batches for any
  Arrow-native engine (Polars, DataFusion, DuckDB).
- **[polars-bio](https://github.com/biodatageeks/polars-bio)** — a high-performance
  Python DataFrame library for genomics: interval operations powered by Apache
  DataFusion, a SQL frontend, indexed parallel I/O, out-of-core streaming, and
  cloud-native reads from S3/GCS.
- **[tangermeme](https://github.com/jmschrei/tangermeme)** — core operations for
  using and analyzing genomic ML models: sequence manipulation, feature
  attribution, variant effect scoring, and DNA design.
- **[bpnet-lite](https://github.com/jmschrei/bpnet-lite)** — compact,
  state-of-the-art sequence-to-function models for predicting chromatin
  accessibility, TF binding, and transcription initiation from DNA sequence.

## Get involved

- 🌐 Website: [composeq.dev](https://composeq.dev)
- 💬 Questions & ideas: open an issue on any of our projects, or email **hello@composeq.dev**
- 🗺️ Roadmap: published at [composeq.dev](https://composeq.dev) *(coming soon)*

## Community

We are committed to a welcoming, harassment-free community. Please read our
[Code of Conduct](https://github.com/composeq/.github/blob/main/CODE_OF_CONDUCT.md).
