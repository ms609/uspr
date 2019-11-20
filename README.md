# uspr

[![Build Status](https://travis-ci.org/ms609/uspr.svg?branch=master)](https://travis-ci.org/ms609/uspr)
[![codecov](https://codecov.io/gh/ms609/uspr/branch/master/graph/badge.svg)](https://codecov.io/gh/ms609/uspr)
[![CRAN Status Badge](http://www.r-pkg.org/badges/version/uspr)](https://cran.r-project.org/package=uspr)
[![CRAN Downloads](http://cranlogs.r-pkg.org/badges/uspr)](https://cran.r-project.org/package=uspr)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3522726.svg)](http://doi.org/10.5281/zenodo.3522725)<!--[![Project Status: Inactive – The project has reached a stable, usable state but is no longer being actively developed; support/maintenance will be provided as time allows.](http://www.repostatus.org/badges/latest/inactive.svg)](http://www.repostatus.org/#inactive)
-->
[![Project Status: Active – – The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)

This package allows the calculation of SPR, TBR and Replug distances between
unrooted phylogenetic trees from within R, using Chris Whidden's `uspr` C++ code.

The uSPR distance is a natural distance metric with respect to phylogenetic tree search, as common tree search and sampling software mainly use SPR operations (or NNI operations, a subset of SPR operations). The uSPR distance is also a lower bound on the number of lateral gene transfer events required to explain the difference between a reference/species tree and a gene tree.

Note that the uSPR distance is NP-hard to compute (as are the TBR and replug distances) and most of the algorithms used in this software scale exponentially with the distance computed. This version of uspr is aimed at trees with up to 50 leaves and uSPR distances up to 14.

If you are interested in comparing rooted trees in terms of SPR operations, you should use [rspr](https://github.com/cwhidden/rspr) instead. rspr is also much more efficient and can easily handle pairs of binary rooted trees with 200+ leaves and distances > 50.
rspr is not yet incorporated in this R package; please 
[contact the maintainer](https://github.com/ms609/uspr/issues/2)
if this would be useful to you.

The C++ code within this package is discussed in Whidden and Matsen (2017), which
provides more information on the motivation behind this project, the algorithms used and their expected performance.

# Installation

Install and load the library from CRAN (coming soon!) as follows:
```
install.packages('uspr')
library('uspr')
```

If you're feeling brave, you can install the development version thus:
```r
if(!require(devtools)) install.packages("devtools")
devtools::install_github('ms609/uspr')
```

Advanced users wishing to use check out the source code using git should note
that the project contains
[submodules](https://github.blog/2016-02-01-working-with-submodules/).
To download the contents of these subdirectories, check out the project using
`git clone --recursive https://github.com/ms609/uspr`,
or if you've already checked out the project, run
`git submodule update --init --recursive`.  

# Usage

If you use uspr in your research, please cite:

Chris Whidden and Frederick A. Matsen IV. Calculating the Unrooted Subtree-Prune-and-Regraft Distance. eprint arXiv:1511.07529. http://arxiv.org/abs/1511.07529

Please note that the 'uspr' project is released with a
[Contributor Code of Conduct](CODE_OF_CONDUCT.md).
By contributing to this project, you agree to abide by its terms.
