# Contributing guide

This document covers general guidelines across the organization. Individual projects add their own build and test instructions in their own `CONTRIBUTING.md`.

## General guidelines

If you haven't contributed to open-source before, we recommend you read [this excellent guide by GitHub on how to contribute to open source](https://opensource.guide/how-to-contribute). The guide is long, so you can gloss over things you're familiar with.

If you're not already familiar with it, we follow the [fork and pull model](https://help.github.com/articles/about-collaborative-development-models) on GitHub. Also, check out this recommended [git workflow](https://www.asmeurer.com/git-workflow/).

## Where does this go?

| You want to... | Go to |
|---|---|
| Report a bug or ask for a feature | The issue tracker of the project it affects |
| Ask how to do something | [Discussions](https://github.com/composeq/.github/discussions) |
| Fix a bug, improve docs, add a test | PR to that project |
| Change a shared Arrow schema field | RFC → [`composeq/rfcs`](https://github.com/composeq/rfcs) |
| Change grammar or operator semantics | RFC → [`composeq/rfcs`](https://github.com/composeq/rfcs) |
| Change what a kernel is defined to compute | RFC → [`composeq/rfcs`](https://github.com/composeq/rfcs) |
| Report a security issue | security@composeq.dev |
| Report a Code of Conduct violation | conduct@composeq.dev |

## Contributing to a specification

Schemas, GIQL, and kernel semantics are versioned specifications with a change process. See [GOVERNANCE.md](GOVERNANCE.md) for the full RFC lifecycle.

## Licensing

All CompoSeq projects are permissively OSI licensed (e.g., MIT, Apache-2.0). Contributions are accepted under the license of the project you're contributing to. There is no CLA.

## Generative AI

Whether you use AI assistance or not, you are responsible for the code you submit. This also includes the licensing of submitted code. Your submission should present a best attempt to improve a publicly shared resource with clean, thoughtful code, and concise and accurate descriptions. You are expected to understand what you are submitting and therefore be able to explain proposed changes convincingly. We reserve the right to flag and/or reject any PR we believe violates this policy.


## Security

Do not report vulnerabilities in public issues. Email security@composeq.dev. We'll acknowledge within 5 business days and keep you updated. We'll credit you when it's fixed, unless you'd rather we didn't.