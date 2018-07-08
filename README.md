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

<!--html_preserve-->

<script type="application/json" data-for="htmlwidget-04ce78d6f315a26316df">{"x":{"attrs":{"labels":["month","BBVA","BCP","Interbank","Scotiabank"],"legend":"auto","retainDateWindow":false,"axes":{"x":{"pixelsPerLabel":60}}},"scale":"monthly","annotations":[],"shadings":[],"events":[],"format":"date","data":[["2011-01-01T00:00:00.000Z","2011-02-01T00:00:00.000Z","2011-03-01T00:00:00.000Z","2011-04-01T00:00:00.000Z","2011-05-01T00:00:00.000Z","2011-06-01T00:00:00.000Z","2011-07-01T00:00:00.000Z","2011-08-01T00:00:00.000Z","2011-09-01T00:00:00.000Z","2011-10-01T00:00:00.000Z","2011-11-01T00:00:00.000Z","2011-12-01T00:00:00.000Z","2012-01-01T00:00:00.000Z","2012-02-01T00:00:00.000Z","2012-03-01T00:00:00.000Z","2012-04-01T00:00:00.000Z","2012-05-01T00:00:00.000Z","2012-06-01T00:00:00.000Z","2012-07-01T00:00:00.000Z","2012-08-01T00:00:00.000Z","2012-09-01T00:00:00.000Z","2012-10-01T00:00:00.000Z","2012-11-01T00:00:00.000Z","2012-12-01T00:00:00.000Z","2013-01-01T00:00:00.000Z","2013-02-01T00:00:00.000Z","2013-03-01T00:00:00.000Z","2013-04-01T00:00:00.000Z","2013-05-01T00:00:00.000Z","2013-06-01T00:00:00.000Z","2013-07-01T00:00:00.000Z","2013-08-01T00:00:00.000Z","2013-09-01T00:00:00.000Z","2013-10-01T00:00:00.000Z","2013-11-01T00:00:00.000Z","2013-12-01T00:00:00.000Z","2014-01-01T00:00:00.000Z","2014-02-01T00:00:00.000Z","2014-03-01T00:00:00.000Z","2014-04-01T00:00:00.000Z","2014-05-01T00:00:00.000Z","2014-06-01T00:00:00.000Z","2014-07-01T00:00:00.000Z","2014-08-01T00:00:00.000Z","2014-09-01T00:00:00.000Z","2014-10-01T00:00:00.000Z","2014-11-01T00:00:00.000Z","2014-12-01T00:00:00.000Z","2015-01-01T00:00:00.000Z","2015-02-01T00:00:00.000Z","2015-03-01T00:00:00.000Z","2015-04-01T00:00:00.000Z","2015-05-01T00:00:00.000Z","2015-06-01T00:00:00.000Z","2015-07-01T00:00:00.000Z"],[1.14,1.16,1.1,1.12,1.13,1.04,1.05,1.13,1.05,1.08,1.03,0.92,1.03,1.16,1.11,1.25,1.23,1.2,1.16,1.24,1.19,1.24,1.27,1.19,1.47,1.5,1.52,1.68,1.71,1.62,1.74,1.78,1.79,1.82,1.81,1.74,1.99,2.1,2.03,2.14,2.24,1.96,2.26,2.29,2.27,2.45,2.38,2.23,2.43,2.45,2.31,2.41,2.47,2.31,2.46],[1.41,1.39,1.45,1.37,1.38,1.42,1.43,1.46,1.46,1.5,1.46,1.42,1.46,1.52,1.59,1.64,1.65,1.69,1.69,1.72,1.67,1.78,1.78,1.68,1.79,1.83,1.98,2.03,2.11,2.09,2.1,2.15,2.18,2.23,2.26,2.27,2.36,2.26,2.42,2.38,2.45,2.43,2.39,2.43,2.37,2.31,2.31,2.3,2.37,2.34,2.31,2.32,2.36,2.43,2.46],[1.65,1.53,1.5,1.55,1.55,1.55,1.65,1.63,1.57,1.6,1.66,1.5,1.65,1.71,1.7,1.78,1.89,1.82,1.82,1.8,1.83,1.84,1.77,1.84,1.94,1.91,1.94,1.92,1.92,1.87,1.81,1.78,1.78,1.77,1.75,1.75,1.88,1.91,1.88,1.9,1.94,1.91,1.94,1.91,2,2.03,2.09,2.49,2.5,2.54,2.28,2.29,2.31,2.41,2.41],[1.51,1.47,1.43,1.51,1.45,1.5,1.51,1.53,1.48,1.53,1.46,1.48,1.47,1.5,1.59,1.62,1.67,1.68,1.63,1.66,1.63,1.73,1.73,1.77,1.74,1.75,1.83,1.87,1.89,1.85,1.87,1.89,1.88,2.01,2.02,2.06,2.21,2.28,2.24,2.26,2.33,2.28,2.33,2.32,2.22,2.34,2.4,2.43,2.56,2.61,2.64,2.7,2.92,3.09,2.99]]},"evals":[],"jsHooks":[]}</script>
<!--/html_preserve-->
Codigo de conducta
------------------

Por favor considerar que este paquete cuenta con un [Codigo de Conducta
del Contribuidor](CODE_OF_CONDUCT.md). Al participar en este proyecto o
utilizarlo, se asume que estas de acuerdo con estos terminos.
