# Changelog

This changelog follows the format defined at:
https://keepachangelog.com/en/1.0.0/

## [1.4.5]

- Adjusted Saltelli sampling to follow recommendation of Owen (2020) 
  (http://arxiv.org/abs/2008.08051; https://github.com/scipy/scipy/pull/10844#issuecomment-672186615)
- Initial support for parallel analysis
- Updated Sobol' G-function analytic results (PR #464, Issues #335 #461)
- Sobol' analysis: Optional storage of intermediate resample results to allow analysis of variation (PR #462)

### Documentation

- Updated Salteli sampling examples to use powers of 2 following recommendations
- Added `citations.cff` file

### Development

- Upgrade PyScaffold to v4
- Replaced recommonmark with MyST (PR #466)


## [1.4.0]

Shortlist of changes since v1.3.x

### Added

- High Dimensional Model Representation (HDMR) method (PR #275)
- PAWN method (PR #415)
- Support for sampling/analysis method chaining (PR #339)
- Support for truncated normal distribution (PR #383)
- Confidence Interval estimation for FAST-based methods (PR #375)
- Initial support for parallel model evaluation

### Documentation

- Defining non-uniform sampling now explicitly documented
- Many general documentation improvements
- Added FAQ

### Development

- Generalized support for non-uniform sampling methods (PR #346)


## [1.3.13]

### Added

- Many documentation improvements
- Explicitly mention extended FAST in documentation
- Saltelli sampling: Warnings displayed when selected samples do not meet 
  requirements (PR #416).
- Group sampling and analysis enabled for Sobol' and morris
- Enhanced DataFrame support for groups

### Bug Fixes:

- Conversion to DataFrame when groups are defined with Sobol' results
  (PR #413 and Issue #387)

## [1.3.0]

### Added

- Various minor performance enhancements (PR #253 #264)
- Added some visualisation methods (PR #259)
- Tidying up of the Command Line Interfance, and num samples (PR #260 #291)
- Improved efficiency of summing distances in local optimization (PR #246)
- Revamped fast method for consistency (PR #239)
- Updated Sobol-G function to modified G-function (#269)

### Bug Fixes:

- Method of morris didn't adjust with levels above 4 (PR #252)
- Add missing seed option for morris sampling
- Handle singular value matrix cases (PR #251)
- Fixed typo (#205)
- Updated import of scipy comb function (PR #243)

### Documentation:

- Update documentation for Morris and DSGM methods (#261 #266)

### Development Features:

- Updated PyScaffold to version 3.2.2 (#267)
- Updated Travis and package config (#285)

## [1.1.0]

### New Features:

- Refactored Method of Morris so the Ruano et al. local approach is default

### Bug Fixes:

- Inputs to morris.analyze are provided as floats
- Removed calls to standard random library as inconsistent between Python 2 & 3
- First row in Sobol sequences should be zero, not empty

### Documentation:

- Added a Code of Conduct
- Added DAETools, BCMD and others to citations - thanks for using SALib!
- Removed misleading keyword arguments in docs and readme examples
- Updated documentation for Method of Morris following refactor
- Improved existing documentation where lacking e.g. for fractional factorial
  method

### Development Features:

- Implemented automatic deployment to PyPi
- Fixed a bug preventing automatic deployment to PyPi upon tagging a branch
- Removed postgres from travis config

## [1.0.0]

Release of our stable version of SALIB to coincide with an submission to JOSS:

- Added a paper for submission to the Journal of Open-source Software
- Updated back-end for documentation on read-the-docs
- Updated the back-end for version introspection using PyScaffold, rather than
  versioneer
- Updated the Travis-CI scripts
- Moved the tests out of the SALib package and migrated to using pytest

## [0.7.1]

Improvements to Morris sampling and Sobol groups/distributions

- Adds improved sampling for the Morris method
  (thanks to @JoerivanEngelen) and group sampling/analysis for the Sobol method
  (thanks to @calvinwhealton).
- @calvinwhealton has also added non-uniform distributions to the Sobol
  sampling.  This will be a baseline for adding this to the other methods in
  the future.
- Also includes several minor bug fixes.

## [0.7.0]

New documentation, doc strings and installation requirements

- @dhadka has kindly contributed a wealth of documentation to the project,
  including doc strings in every module
- no longer test for numpy <1.8.0 and matplotlib < 1.4.3, and these
  requirements are implemented in a new setup script.

## [0.6.3]

Parallel option for Sobol method

- New option to run analyze.sobol function in parallel using multiprocessing

## [0.6.2]

This release does not contain any new functionality, but SALib now is citable
using a Digital Object Identifier (DOI), which can be found in the readme.

Some minor updates are included:

- morris: sigma has been removed from the grouped-morris results and plots,
  replaced by mu_star_conf - a bootstrapped confidence interval.
  Mu_star_conf is not equivalent to sigma when used in the non-grouped method of
  morris, but its all we have when using groups.
- some minor updates to the tests in the plotting module

## [0.6.0]

- Set up to include and test plotting functions
- Specific plotting functions for Morris
- Fractional Factorial SA from Saltelli et al.
- Repo transferred to SALib organization, update setup and URLs
- Small bugfixes

## [0.5.0]

- Vectorized bootstrap calculations for Morris and Sobol
- Optional trajectory optimization with Gurobi, and tests for it
- Several minor bugfixes
- Starting with v0.5, SALib is released under the MIT license.

## [0.4.0]

- Better Python API without requiring file read/write to the OS.
  Consistent functional API to sampling methods so that they return numpy
  matrices. Analysis methods now accept numpy matrices instead of data file
  names. This does not change the CLI at all, but makes it much easier to use
  from native Python.
- Also expanded tests for regression and the Sobol method.

## [0.3.0]

Improvements to Morris sampling and analysis methods,
some bugfixes to make consistent with previous versions of the methods.

## [0.2.0]

Improvements to Morris sampling methods (support for group sampling,
and optimized trajectories). Much better test coverage, and fixed Python 3
compatibility.

## [0.1.0]

First numbered release. Contains reasonably well-tested versions of the Sobol,
Morris, and FAST methods. Also contains newer additions of DGSM and delta
methods which are not as well-tested yet. Contains setup.py for installation.
