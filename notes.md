Delete

- .Rproj.user/
- .Rhistory
- ..Rcheck/
- ..pdf
- .Rdata
- testing/


Repository size

~ 120 mb


Documentation

- is docs/ required if using branch gh-pages?
- ignore rendered vignette?



README

- L14 alt "baRulho" 



NEWS

- Link to PRs and issues



CI
- tic



R/
- ohun_package.R
    - "parallelization of tasks" 
        - using which parallel backend?
    - extra NULL L48, 49

Using internal functions from another package in 12 cases, though given all 12 are from warbleR and the maintainer of ohun is also the maintainer of warbleR this seems ok


- stop2, warning2 function are custom functions so the call isnt printed.. why?

with `stop2`
R: label_detection(reference = matrix(lbh_reference[-1, ]), detection = lbh_reference)
Error: 'reference' is not of a class 'data.frame' or 'selection_table'

with `stop`
R: label_detection(reference = matrix(lbh_reference[-1, ]), detection = lbh_reference)
Error in label_detection(reference = matrix(lbh_reference[-1, ]), detection = lbh_reference) : 
  'reference' is not of a class 'data.frame' or 'selection_table'

`stop2` is used 105 times across 14 files

`warning2` is used 3 times across 3 files


Warnings are suppressed in feature_reference.R 3 times and in optimize_energy_detector.R 2 times


Curly braces are variably used 

eg. in `find_templates`
```
    t2xy <- function(t) {
      t2p <- 2 * pi * t + 0 * pi / 180
      list(x = radius * cos(t2p), y = radius * sin(t2p))
    }

    if (plot)
      plot(
        space[, 1] + mean_dim1,
        space[, 2] + mean_dim2,
        pch = 20,
        cex = 2,
        col = color,
        xlab = xlab,
        ylab = ylab
      )
```


DESCRIPTION
- dependencies
    - see below for run pak::pkg_deps_tree("ohun")
- listing in Depends

> A more classic example of Depends is how the censored package depends on the parsnip and survival packages. Parsnip provides a unified interface for fitting models, and censored is an extension package for survival analysis. Censored is not useful without parsnip and survival, so it makes sense to list them in Depends.
(from https://r-pkgs.org/dependencies-mindset-background.html#sec-dependencies-imports-vs-depends)

see https://github.com/leeper/Depends

Nested Depends:
- From warbleR
    - tuneR, seewave (>= 2.0.1), NatureSounds
- From tuneR
    - None
- From seewave
    - None
- From NatureSounds
    - knitr


- Date/Publication field?
- Config/testthat/edition field?
- Repository field?


Vignettes

- consider splitting up ohun.Rmd into multiple vignettes
    - Get started vignette
        - Background and theory
        - How does ohun fit in
        - What other packages does ohun interface with
        - Overview of functions provided by ohun
    - Energy based detection
    - Template based detection
    - FAQ / best practices / advice / tips

- clean
    - remove &nbsp; 
    - remove &#x3A; from title
    - remove old outpuit format
    - example printing has `[39m[90m|`



Contribution

- title "Contributing to CONTRIBUTING.md"
- Code of conduct link is broken
- No code of conduct found in repository
- Note the rOpenSci Code of Conduct, especially the Reporting Guidelines section: https://ropensci.org/code-of-conduct/. An issue board may be ok in some cases, but an alternative, private method of communication would be helpful as well
- TODO minor edits

# Checks



Data
- Data stored as R objects in data/ 



R/
- good file names


Dependencies
- importFrom, ... all in R/ohun-package.R


Double @@ in email, though seems to render well on marce10.github.io/ohun


# Deps tree

R: pak::pkg_deps_tree("ohun")
✔ Updated metadata database: 2.20 MB in 6 files.                          
✔ Updating metadata database ... done                                     
ohun 0.1.0 [new][bld][dl] (2.64 MB)                                        
├─tuneR 1.4.3 [new][bld][cmp][dl] (427.79 kB)
│ └─signal 0.7-7 [new][bld][cmp][dl] (1.96 MB)
│   └─MASS 7.3-58.2 -> 7.3-59 [upd][bld][cmp][dl] (515.84 kB)
├─warbleR 1.1.28 [new][bld][cmp][dl] (4.49 MB)
│ ├─tuneR
│ ├─seewave 2.2.0 [new][bld][dl] (2.69 MB)
│ │ └─tuneR
│ ├─NatureSounds 1.0.4 [new][bld][dl] (4.40 MB)
│ │ ├─knitr 1.42 [new][bld][dl] (893.59 kB)
│ │ │ ├─evaluate 0.20 [new][bld][dl] (26.66 kB)
│ │ │ ├─highr 0.10 [new][bld][dl] (15.08 kB)
│ │ │ │ └─xfun 0.39 [new][bld][cmp][dl] (135.48 kB)
│ │ │ ├─yaml 2.3.7 [new][bld][cmp][dl] (94.33 kB)
│ │ │ └─xfun
│ │ └─tuneR
│ ├─dtw 1.23-1 [new][bld][cmp][dl] (746.72 kB)
│ │ └─proxy 0.4-27 [new][bld][cmp][dl] (74.62 kB)
│ ├─fftw 1.0-7 [new][bld][cmp][dl] (42.45 kB)
│ ├─monitoR 1.0.7 [new][bld][dl] (2.90 MB)
│ │ └─tuneR
│ ├─pbapply 1.7-0 [new][bld][dl] (23.81 kB)
│ ├─RCurl 1.98-1.12 [new][bld][cmp][dl] (731.48 kB)
│ │ └─bitops 1.0-7 [new][bld][cmp][dl] (10.81 kB)
│ ├─rjson 0.2.21 [new][bld][cmp][dl] (116.51 kB)
│ ├─Rcpp 1.0.10 [new][bld][cmp][dl] (2.94 MB)
│ ├─knitr
│ ├─crayon 1.5.2 [new][bld][dl] (40.57 kB)
│ └─bioacoustics 0.2.8 [new][bld][cmp][dl] (829.33 kB)
│   ├─htmltools 0.5.5 [new][bld][cmp][dl] (131.88 kB)
│   │ ├─digest 0.6.31 [new][bld][cmp][dl] (163.50 kB)
│   │ ├─base64enc 0.1-3 [new][bld][cmp][dl] (7.83 kB)
│   │ ├─rlang 1.1.1 [new][bld][cmp][dl] (762.53 kB)
│   │ ├─fastmap 1.1.1 [new][bld][cmp][dl] (46.41 kB)
│   │ └─ellipsis 0.3.2 [new][bld][cmp][dl] (8.07 kB)
│   │   └─rlang
│   ├─moments 0.14.1 [new][bld][dl] (7.64 kB)
│   ├─Rcpp
│   ├─stringr 1.5.0 [new][bld][dl] (175.70 kB)
│   │ ├─cli 3.6.1 [new][bld][cmp][dl] (567.29 kB)
│   │ ├─glue 1.6.2 [new][bld][cmp][dl] (106.51 kB)
│   │ ├─lifecycle 1.0.3 [new][bld][dl] (106.85 kB)
│   │ │ ├─cli
│   │ │ ├─glue
│   │ │ └─rlang
│   │ ├─magrittr 2.0.3 [new][bld][cmp][dl] (267.07 kB)
│   │ ├─rlang
│   │ ├─stringi 1.7.12 [new][bld][cmp][dl] (7.60 MB)
│   │ └─vctrs 0.6.2 [new][bld][cmp][dl] (964.63 kB)
│   │   ├─cli
│   │   ├─glue
│   │   ├─lifecycle
│   │   └─rlang
│   └─tuneR
├─pbapply
├─viridis 0.6.3 [new][bld][dl] (3.05 MB)
│ ├─viridisLite 0.4.2 [new][bld][dl] (1.27 MB)
│ ├─ggplot2 3.4.2 [new][bld][dl] (3.15 MB)
│ │ ├─cli
│ │ ├─glue
│ │ ├─gtable 0.3.3 [new][bld][dl] (130.06 kB)
│ │ │ ├─cli
│ │ │ ├─glue
│ │ │ ├─lifecycle
│ │ │ └─rlang
│ │ ├─isoband 0.2.7 [new][bld][cmp][dl] (1.59 MB)
│ │ ├─lifecycle
│ │ ├─MASS
│ │ ├─mgcv 1.8-42 
│ │ │ ├─nlme 3.1-162 
│ │ │ │ └─lattice 0.20-45 -> 0.21-8 [upd][bld][cmp][dl] (589.33 kB)
│ │ │ └─Matrix 1.5-3 -> 1.5-4 [upd][bld][cmp][dl] (2.18 MB)
│ │ │   └─lattice
│ │ ├─rlang
│ │ ├─scales 1.2.1 [new][bld][dl] (270.61 kB)
│ │ │ ├─farver 2.1.1 [new][bld][cmp][dl] (1.27 MB)
│ │ │ ├─labeling 0.4.2 [new][bld][dl] (10.16 kB)
│ │ │ ├─lifecycle
│ │ │ ├─munsell 0.5.0 [new][bld][dl] (182.65 kB)
│ │ │ │ └─colorspace 2.1-0 [new][bld][cmp][dl] (2.12 MB)
│ │ │ ├─R6 2.5.1 [new][bld][dl] (63.42 kB)
│ │ │ ├─RColorBrewer 1.1-3 [new][bld][dl] (11.64 kB)
│ │ │ ├─rlang
│ │ │ └─viridisLite
│ │ ├─tibble 3.2.1 [new][bld][cmp][dl] (565.98 kB)
│ │ │ ├─fansi 1.0.4 [new][bld][cmp][dl] (482.06 kB)
│ │ │ ├─lifecycle
│ │ │ ├─magrittr
│ │ │ ├─pillar 1.9.0 [new][bld][dl] (444.53 kB)
│ │ │ │ ├─cli
│ │ │ │ ├─fansi
│ │ │ │ ├─glue
│ │ │ │ ├─lifecycle
│ │ │ │ ├─rlang
│ │ │ │ ├─utf8 1.2.3 [new][bld][cmp][dl] (241.41 kB)
│ │ │ │ └─vctrs
│ │ │ ├─pkgconfig 2.0.3 [new][bld][dl] (6.08 kB)
│ │ │ ├─rlang
│ │ │ └─vctrs
│ │ ├─vctrs
│ │ └─withr 2.5.0 [new][bld][dl] (102.09 kB)
│ └─gridExtra 2.3 [new][bld][dl] (1.06 MB)
│   └─gtable
├─crayon
├─seewave
├─RCurl
├─fftw
├─knitr
├─rjson
├─rlang
├─sp 1.6-0 [new][bld][cmp][dl] (1.03 MB)
│ └─lattice
├─igraph 1.4.2 [new][bld][cmp][dl] (3.31 MB)
│ ├─magrittr
│ ├─Matrix
│ ├─pkgconfig
│ ├─rlang
│ └─cpp11 0.4.3 [new][bld][dl] (304.53 kB)
└─Sim.DiffProc 4.8 [new][bld][cmp][dl] (1.12 MB)
  ├─Deriv 4.1.3 [new][bld][dl] (37.21 kB)
  └─MASS