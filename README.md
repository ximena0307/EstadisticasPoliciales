# EstadisticasPoliciales
Datos oij
title: "estadistica"
author: "Ximena Alvarez Ch"
date: '2022-06-20'
output: html_document
---

```{r setup, include=FALSE}
datos_oij<- estadisticaspoliciales2021
install.packages("lubridate")
library(lubridate)
install.packages ("deploy")
library("deploy")
install.packages("plotly")
library(plotly)
library(terra)
# Carga de otros paquetes
library(readr) 
library(dplyr) 
```


```{r tabla DT, echo=FALSE}
datos_oij%>%
  datatable(options = list(
    papeLenght = 15 ,
    language = list(url = '//cnd.datatables.net/plug-ins/1.10.11/i18n/Spanish,json'),
    colnames(datos_oij) <- c("Delitos","Fecha", "Víctima","Edad","Género","Provincia")
  ))
```
```{r graficos barras simples, valores de conteo}
ggplot2_delitosmensuales<-(datos_oij)
  
ggplot2_delitosmensuales<-datos_oij%>% mutate(Fecha = lubridate :: month(Fecha))
mes <-
  c(
  "enero","febrero","marzo","abril","mayo","junio","julio","agosto","setiembre","octubre","noviembre","diciembre")
    ggplot2_delitosmensuales<-datos_oij%>% mutate(delito= Delito)     

ggplot2_delitos<-datos_oij

ggplot

colnames(delito)
colnames(mes)


ggplot2_delitosmensuales <-
  datos_oij %>%
  ggplot(aes(x = Delito)) +
  geom_bar() +
  ggtitle("Delitos Mensuales") +
  xlab("delito")+
  ylab("mes")+
  theme_minimal()
ggplotly(ggplot2_delitosmensuales)

```



```{r graficos barras apiladas, echo=FALSE}

ggplot2_barras_proporciondelitos <-
  datos_oij %>%
  ggplot(aes(x = Delito)) +
  geom_bar() +
  ggtitle("Proporcion delitos") +
  xlab("delito") +
  ylab("Proporción") +
  theme_minimal()

ggplotly(ggplot2_barras_proporciondelitos) 
```

