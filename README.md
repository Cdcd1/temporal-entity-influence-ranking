# Temporal entity influence ranking: public data assets

This repository holds the public data assets and source information for the manuscript on overall and history-relative entity influence ranking in temporal heterogeneous graphs.

## Available files

- [`data/HiDy/raw/data.zip`](data/HiDy/raw/data.zip): the unchanged HiDy v1.10 archive from [Zenodo record 12630355](https://doi.org/10.5281/zenodo.12630355).
- [`data/HiDy/task/`](data/HiDy/task/): our normalized HiDy event graph, candidate sets, split boundaries, and derived ranking labels. The [HiDy data card](data/HiDy/README.md) and [task protocol](data/HiDy/task_protocol.json) describe their provenance and construction.
- [`data/sources/README.md`](data/sources/README.md): original download locations for all four public domains used in the paper.
- [`SHA256SUMS`](SHA256SUMS): checksums for every hosted data file.

To check the copied files, run `shasum -a 256 -c SHA256SUMS` from the repository root.

The publicly hosted HiDy files are distributed with attribution under the source dataset's [CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/). The normalized graph and ranking labels were derived from the cited HiDy release. The other public source datasets remain at their original repositories; download them from the links in `data/sources/README.md`. The restricted Chinese equity network is not included.

This is an initial public data release. The data and checksums here are fixed to the manuscript's existing HiDy task package; additional reproducibility scripts and public-domain configurations can be added after their source and dependency audit.
