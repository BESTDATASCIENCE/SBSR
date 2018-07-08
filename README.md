<!-- README.md is generated from README.Rmd. Please edit that file -->
SBSR <img src="man/figures/logo.png" align="right" >
====================================================

[![lifecycle](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing)

SBSR es un paquete disenado para trabajar facilmente con data publica de
la SBS. Este proyecto es creado por [BEST](http://besteamperu.org).
Aprende a utilizarlo en `vignette("SBSR")` o
<https://bestdatascience.github.io/SBSR/index.html>.

Instalacion
-----------

    # Instala primero devtools
    install.packages("devtools")

    # Instala la Ultima version usando
    devtools::install_github("BESTDATASCIENCE/SBSR")

Uso
---

El paquete cuenta con data de los bancos y lo puedes usar facilmente
utilizando esta funcion:

    library(SBSR)
    data("bancos")
    head(bancos)

Codigo de conducta
------------------

Por favor considerar que este paquete cuenta con [Contributor Code of
Conduct](CODE_OF_CONDUCT.md). Al participar en este proyecto o
utilizarlo, se asume que estas de acuerdo con estos terminos.
