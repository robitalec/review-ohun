Delete

- .Rproj.user/
- .Rhistory
- ..Rcheck/
- ..pdf
- .Rdata
- testing/



Documentation

- is docs/ required if using branch gh-pages?
- ignore rendered vignette?



README

- L14 alt "baRulho" 



NEWS

- Link to PRs and issues



R/
- ohun_package.R
    - "parallelization of tasks" 
        - using which parallel backend?
    - extra NULL L48, 49

Using internal functions from another package in 12 cases, though given all 12 are from warbleR and the maintainer of ohun is also the maintainer of warbleR this seems ok


DESCRIPTION
- dependencies
    - TODO: run pak::pkg_deps_tree("ohun")
- listing in Depends

> A more classic example of Depends is how the censored package depends on the parsnip and survival packages. Parsnip provides a unified interface for fitting models, and censored is an extension package for survival analysis. Censored is not useful without parsnip and survival, so it makes sense to list them in Depends.
(from https://r-pkgs.org/dependencies-mindset-background.html#sec-dependencies-imports-vs-depends)

see https://github.com/leeper/Depends



# Checks

Data
- Data stored as R objects in data/ 
