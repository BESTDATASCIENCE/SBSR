<!-- README.md is generated from README.Rmd. Please edit that file -->
SBSR <img src="man/figures/logo.png" align="right" height="140" width="139"/>
=============================================================================

[![lifecycle](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing)

SBSR es un paquete disenado para trabajar facilmente con data publica de
la SBS. Este proyecto es creado por [BEST](http://besteamperu.org).
Aprende a utilizarlo en `vignette("SBSR")` o
<https://bestdatascience.github.io/SBSR/index.html>.

Instalacion
-----------

    # Instalemos primero los paquetes necesarios de forma inteligente! Usemos la siguiente funcion: copiala y pega en tu consola de R, o ponlo en un script y usa control control + enter.

    rpak <- function(pkg){
        new.pkg <- pkg[!(pkg %in% installed.packages()[, "Package"])]
        if (length(new.pkg)) 
            install.packages(new.pkg, dependencies = TRUE)
        sapply(pkg, require, character.only = TRUE)
    }

    # los paquetes que necesitamos!

    packages <- c("ggplot2", "dplyr", "reshape2","tidyr","xts","zoo","dygraphs","devtools","reshape2","lubridate")
    rpak(packages)

    # Instala la ultima version de nuestro paquete usando
    devtools::install_github("BESTDATASCIENCE/SBSR")

Uso
---

El paquete cuenta con data de los bancos y lo puedes usar facilmente
utilizando esta funcion:

    packs=c("SBSR","xts","dplyr","tidyr","dygraphs","ggplot2","reshape2","lubridate")
    invisible(lapply(packs,library,character=T))
    data("bancos")

    bd<-bancos %>% filter (Entidad %in% c("BCP","BBVA","Scotiabank","Interbank")) %>% select(Entidad,morosidad,Fecha)

    bd<-bd %>%
      spread(Entidad, morosidad)
    bd<-xts(bd[,2:5],order.by = as.Date(bd$Fecha))
    dygraph(bd)

![SBS1](/img1.png)

Codigo de conducta
------------------

Por favor considerar que este paquete cuenta con un [Codigo de Conducta
del Contribuidor](CODE_OF_CONDUCT.md). Al participar en este proyecto o
utilizarlo, se asume que estas de acuerdo con estos terminos.
