# EstadisticasPoliciales
Datos oij
---
title: "Datos Oij"
author: "Ximena Alvarez"
date: '2022-06-20'
output: html_document
---

```{r Tabla DT, echo=FALSE}
datos_oij %>%
  datatable(options = list(
    papeLength = 15,
    language = list(url = '//cdn.datatables.net/plug-ins/1.10.11/i18n/Spanish.json'),
    colnames(datos_oij) <- c("Delitos","Fecha","Víctima","Edad","Género","Provincia")
  ))
```



```{r  graficos de barras, echo=FALSE}
  
```


```{r grafico de barras,echo = FALSE}
#ggplot2_barras_proporcion <-
  datos_oij %>%
  ggplot(aes(x = cut, y = stat(prop), group = 1)) +
  geom_bar() +
  ggtitle("Delitos por Fecha") +
  xlab("Fecha") +
  ylab("Delito") +
  theme_minimal()
ggplot(datos_oij)
```




```{r Tabla DT Delitos}
datos_oij %>%
datatable(options = list(
papeLength = 15,
language = list(url = '//cdn.datatables.net/plug-ins/1.10.11/i18n/Spanish.json'),
 colnames(datos_oij) <- c ("Asalto","Hurto","Robo de vehiculo","Tacha de Vehiculo","Homicidio") ("masculino","femenino","desconocido")
))
```{r graficos apiladps}
datos_por_genero <- datos_oij
ggplot2_barras_apiladas_cantidad <-
  datos_por_genero %>%
  ggplot(aes(x = cut, fill = clarity)) +
  geom_bar() +
  ggtitle("Delitos por nombre") +
  xlab("Género") +
  ylab("delito") +
  labs(fill = "Claridad") +
  theme_minimal()
ggplot(datos_por_genero)
