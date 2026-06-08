# Reinforcement-learning-discovered sinusoidal charge-injection modulation for electro-thermo-convection

This repository contains the source code and numerical results associated with the manuscript:

**Reinforcement-learning-discovered sinusoidal charge-injection modulation for flow stabilization and heat transfer enhancement in electro-thermo-convection**

The paper is currently under preparation. Bibliographic details, DOI, and the final citation will be updated after publication.

## Repository contents

```text
.
├── code/
│   ├── gamma2/      # Reinforcement-learning and OpenFOAM setup for Gamma = 2
│   ├── gamma35/     # Reinforcement-learning and OpenFOAM setup for Gamma = 3.5
│   └── gamma6/      # Reinforcement-learning and OpenFOAM setup for Gamma = 6
├── results/         # Optimized actions and trained actor weights used for post-processing
├── LICENSE
├── CITATION.cff
├── requirements.txt
└── CODE_AVAILABILITY.md
```

Each `gamma*` directory contains the reinforcement-learning scripts and the corresponding OpenFOAM case template. The three cases use the same workflow with different control/search spaces and simulation settings.

## Software requirements

The Python workflow requires:

- Python 3.9 or newer
- PyTorch
- NumPy
- SwanLab, only if experiment logging is enabled

The flow solver workflow requires:

- OpenFOAM
- the `eZYFoam` solver available in the shell environment
- MPI for parallel cases

The exact OpenFOAM/eZYFoam installation is system dependent. Before running the scripts, make sure that commands such as `eZYFoam`, `foamListTimes`, `postProcess`, and, for parallel runs, `mpirun` and `reconstructPar`, are available from the working shell.

## Python environment

Install the Python dependencies with:

```bash
pip install -r requirements.txt
```

If SwanLab logging is not required, set `log_switch` to `False` in the corresponding `SAC_1_hyperparameters.py` file.

## Running training

Enter one case directory and run the training script:

```bash
cd code/gamma2
python SAC_1_train.py
```

Use `code/gamma35` and `code/gamma6` for the other two cases. The hyperparameters are defined in each case-specific `SAC_1_hyperparameters.py`.

The released configuration starts a fresh run by default:

```python
'continue_or_restart': False
'load_dir': ''
```

## Evaluating a trained actor

The evaluation scripts intentionally leave `MODEL_PATH` blank. Set it to a trained actor file before evaluation, for example:

```python
MODEL_PATH = "../../results/gamma2.pth"
```

Then run:

```bash
cd code/gamma2
python SAC_1_eval.py
```

The output reports the deterministic action predicted by the trained actor in physical units.

## Results

The `results/` directory contains:

- `gamma2.csv`, `gamma3.5.csv`, and `gamma6.csv`: action-reward records used for analysis.
- `gamma2.pth`, `gamma3.5.pth`, and `gamma6.pth`: trained actor weights corresponding to the three cases.

See `results/README.md` for details.

## Notes on generated OpenFOAM files

Compiled OpenFOAM dynamic-code artifacts, decomposed `processor*` directories, runtime `runs/`, `logs/`, and `postProcessing/` directories are not part of the source release. They are generated during simulation and are excluded by `.gitignore`.

## Citation

Please cite the associated manuscript when using this repository. Until the paper is published, use the metadata in `CITATION.cff` and update it with the final bibliographic information when available.

## License

This project is released under the MIT License. See `LICENSE` for details.
