
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SBSR

SBSR es un paquete diseñado para trabajar facilmente con data pública de
la SBS. Este proyecto es creado por [BEST](http://besteamperu.org).
Aprende a utilizarlo en `vignette("SBSR")` o
<https://bestdatascience.github.io/SBSR/index.html>.

## Instalación

``` r
# Instala primero devtools
install.packages("devtools")

# Instala la última versión usando
devtools::install_github("BESTDATASCIENCE/SBSR")
```

## Uso

Run pkgdown from the package directory each time you release your
package:

``` r
library(SBSR)
data("bancos")
View(bancos)
```

## Codigo de conducta

Por favor considerar que este paquete cuenta con [Contributor Code of
Conduct](CODE_OF_CONDUCT.md). Al participar en este proyecto o
utilizarlo, se asume que estás de acuerdo con estos términos.
