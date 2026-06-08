# Code Availability

The source code and numerical results accompanying the manuscript will be made publicly available in this repository.

At this stage, the manuscript is still under preparation. The repository metadata, citation information, and paper link will be updated after publication or formal release.

## Included material

- Reinforcement-learning scripts for the three aspect-ratio cases.
- OpenFOAM case templates required to reproduce the simulations.
- Optimized-action records and trained actor weights used for post-processing.

## Excluded generated material

The following files are intentionally excluded from version control:

- decomposed OpenFOAM `processor*` directories;
- compiled OpenFOAM `dynamicCode` artifacts;
- runtime `runs/`, `logs/`, and `postProcessing/` directories;
- Python cache files.

These files are generated during training or simulation and are not required as source files.
