# Results

This directory contains the action-reward records and trained actor weights associated with the three cases considered in the manuscript.

## Files

| File | Description |
| --- | --- |
| `gamma2.csv` | Action-reward records for the Gamma = 2 case. |
| `gamma2.pth` | Trained actor weights for the Gamma = 2 case. |
| `gamma3.5.csv` | Action-reward records for the Gamma = 3.5 case. |
| `gamma3.5.pth` | Trained actor weights for the Gamma = 3.5 case. |
| `gamma6.csv` | Action-reward records for the Gamma = 6 case. |
| `gamma6.pth` | Trained actor weights for the Gamma = 6 case. |

The `.pth` files can be used with the corresponding `SAC_1_eval.py` scripts after setting `MODEL_PATH`.
