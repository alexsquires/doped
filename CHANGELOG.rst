Change Log
==========

v.2.0.5
----------
- Update oxi-state handling to:
    - Use pre-assigned oxi states if present
    - Handle `pymatgen` oxi-state guessing failures (non-integer oxi states, inaccurate oxi states with
      max_sites, failures for extremely large systems etc)
- Update default `probability_threshold` from 0.01 to 0.0075.
- Account for rare possibility of user being on a non UTF-8 system.
- Italicise "V" for vacancy in plotting.
- SMTG-UCL -> SMTG-Bham
- Tests and formatting updates.

v.2.0.4
----------
- Add supercell re-ordering tests for parsing
- Ensure final _relaxed_ defect site (for interstitials and substitutions) is used for finite-size
  charge corrections
- Consolidate functions and input sets with `ShakeNBreak`
- Update defect generation tests
- Use more efficient Wyckoff determination code

v.2.0.3
----------
- Sort defect entries in ``DefectPhaseDiagram`` for deterministic behaviour (particularly for plotting).
- Tests updates (archive test plots, update extrinsic generation tests etc).
- Avoid long stacklevel issue which cropped up in ``python3.8`` tests for ``SnB``
- Update PDF figure `savefig` settings, and add `_get_backend` function.

v.2.0.2
----------
- Refactor `_check_user_potcars()` to `DefectDictSet` rather than `DefectRelaxSet`, and add `write_input
  ()` method (which runs `_check_user_potcars()` first).
- Update defect generation tests
- Add troubleshooting docs page and update tips docs page

v.2.0.1
----------
- Update naming handling in ``DefectPhaseDiagram`` to be more robust/flexible, following failure case
  noted by @utf 🙌
- Ensure package data files are correctly included in the package distribution, again noted by @utf 🙌
- Updates to chemical potentials code.
- Refactoring of site-matching code.
- Tests updates and code cleanup.

v.2.0.0
----------
- Major overhaul to rebase onto the new `pymatgen` defects code (`>v2022.7.25`).
- Add documentation (https://doped.readthedocs.io/en/latest)
- Add `DefectsGenerator` class with major upgrade in functionality.
- Add `DefectsSet` classes in `vasp.py`

v.1.1.2
----------
- Cap `numpy` to `1.23` to avoid `pymatgen` dependency issues.
- Update example workbook to use recommended `CubicSupercellTransformation`
- Add/remove some `TODO`s

v1.1.1
----------
- `doped` now installable from `conda-forge`! 🎉
- Major overhaul of primary parsing workflow (in `defect_entry_from_paths()`):
    - Automatic charge-state determination (throwing warning when user specification doesn't match auto-determined)
    - Automatic charge correction determination and application
    - Improved error handling and more informative warning messages
- Add `test_defectsmaker.py`, `test_corrections.py` and `test_analysis.py` -> significantly improve test coverage
- Add `_convert_dielectric_to_tensor()` function to be more flexible to user input
- Remove old unsupported/deprecated code.
- Add check and warning if multiple output files (`vasprun.xml`/`OUTCAR`/`LOCPOT`) present in bulk/defect directory.
- Minor bug fixes, formatting, docstrings improvement, the usual
- Add and remove `TODO`s


v1.0.6
----------
- Start keeping a `CHANGELOG`
- `README` updates to give step-by-step instructions on setting up MP API key, `POTCAR`s for `pymatgen` and virtual `conda` environments for `doped` and `ShakeNBreak`
- Major overhaul of `vasp_input` functions setup to be far more streamlined and customisable.
- Major overhaul of `chemical_potentials` code; now with improved algorithm for selecting potential competing phases
- Update of example notebooks
- Add tests for parsing calculations, chemical_potentials and vasp_input
- Add GH Actions workflows (for tests, GH releases and pypi packaging)
- Adopt recommended versioning convention based on dates
- General tidy up, docstring padding, formatting and `TODO` addition/removal
- Ensure all inputs/outputs are `JSON`able, now recommending this for better forward/backward compatibility
- Refactor `dope_stuff` to `plotting` and `analysis` to be more clear and PROfessional, yo
- Refactor from hard-coded defaults / slightly-less-human-readable `json` files to `yaml` files with default settings.
- Refactor `defectsmaker` output, more efficient, cleaner and informative
