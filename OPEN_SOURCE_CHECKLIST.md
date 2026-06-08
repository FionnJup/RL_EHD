# Open-source Release Checklist

Use this checklist before making the GitHub repository public.

- [ ] Confirm that the final repository name is correct.
- [ ] Confirm that the MIT License is the intended license.
- [ ] Update author names in `CITATION.cff`.
- [ ] Add the GitHub repository URL to `repository-code` in `CITATION.cff`.
- [ ] Add DOI, journal, and publication details after the paper is accepted or published.
- [ ] Upload the `code/` directory after confirming that only source files are included.
- [ ] Upload the `results/` directory if the released model weights and CSV files should be public.
- [ ] Verify that no `logs/`, `runs/`, `processor*/`, `postProcessing/`, or `dynamicCode/` directories are committed.
- [ ] Test `python SAC_1_eval.py` after setting `MODEL_PATH` to a released `.pth` file.
