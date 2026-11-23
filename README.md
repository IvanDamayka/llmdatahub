# llmdatahub

Finding instruction fine-tuning datasets often means comparing scattered dataset pages with different formats and incomplete metadata. llmdatahub collects references for LLM dataset discovery, with a focus on chatbot training data and the details needed to compare it.

## Features

- Browse dataset references for instruction fine-tuning and alignment.
- Compare reported dataset sizes, languages, and training types in tables.
- Follow links to upstream dataset pages for access and documentation.
- Distinguish supervised fine-tuning data, pretraining corpora, chain-of-thought examples, and reward-model training data through type tags.
- Review short descriptions of dataset formats, annotation methods, and intended uses.

**Check each dataset's own license before use.** A catalog entry does not grant permission to train on or redistribute the underlying data. Reported sizes and descriptions should also be checked against the linked source.

## Installation

The source material documents a dataset catalog, but does not establish a Go executable, module path, or published release archive. The commands below describe a proposed installation layout for a standalone Go implementation; they are not verified installation instructions. Replace `OWNER` with the new project's GitHub owner once the repository exists.

With Go installed, the proposed source-build workflow is:

```sh
git clone https://github.com/OWNER/llmdatahub.git
cd llmdatahub
go build -o llmdatahub .
```

The following download command assumes that a Linux amd64 archive has been published with the stated filename under the `v0.1.0` release:

```sh
curl -fL https://github.com/OWNER/llmdatahub/releases/download/v0.1.0/llmdatahub_0.1.0_linux_amd64.tar.gz -o llmdatahub_0.1.0_linux_amd64.tar.gz
```

## Usage

Use the catalog to compare candidate datasets, then follow their upstream links. For example:

| Dataset | Training type | Language | Reported size | Notes |
| --- | --- | --- | --- | --- |
| [HelpSteer](https://huggingface.co/datasets/nvidia/HelpSteer) | Reward-model training | English | 37k instances | Human ratings for helpfulness, correctness, coherence, complexity, and verbosity. |
| [no_robots](https://huggingface.co/datasets/HuggingFaceH4/no_robots) | Supervised fine-tuning | English | 10k instances | Human-created, single-turn instruction data. |

These figures come from the source catalog and may differ from current upstream metadata.

**CLI example: proposed interface, not an implemented feature.** If a Go command is added, a dataset lookup could use this form:

```sh
./llmdatahub list --type sft --language English
```

No CLI flags or output format are established by the supplied donor material.

## License

MIT. This project is based on [Zjh-819/LLMDataHub](https://github.com/Zjh-819/LLMDataHub), which is also MIT-licensed. Retain the upstream copyright notice and MIT permission notice in any copied or adapted material. Dataset licenses remain separate from the catalog's license.

## Related projects

The following repositories were supplied as other projects from the same author. Their functionality was not included in the source material, so it is not described here.

- [Vishalharma/kardio](https://github.com/Vishalharma/kardio): listed as related; project scope has not been verified.
- [egutierrz/magic8bot](https://github.com/egutierrz/magic8bot): listed as related; project scope has not been verified.
- [leololahe-bot/lastbackend](https://github.com/leololahe-bot/lastbackend): listed as related; project scope has not been verified.

