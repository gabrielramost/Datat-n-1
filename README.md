# Datatón 1 - Solución

Librerías que se utilizarán:

```{r}
library(htmltab)
library(rio)
```

## 1. Base de datos sobre cronología de epidemias, que contenga información sobre al menos su duración y el patógeno que la ocasionó. 

Los datos los obtiene de Wikipedia (que se hace referencia en las instrucciones) 

```{r}
link = "https://es.wikipedia.org/wiki/Anexo:Cronolog%C3%ADa_de_epidemias"
path = "/html/body/div[3]/div[3]/div[5]/div[1]/table[3]"
data1 = htmltab(link, path)
export(data1,"data1.sav")
```

## 2. Base de datos simple que contenga información sobre el número de vacunas aplicadas, el número de personas con una dosis, el número de personas con dos dosis, los vacunados del día de hoy, y las dosis aplicadas en el 8tavo vacunatón.

Los datos los obtiene del tablero de control que se hace referencia en las instrucciones: https://www.minsa.gob.pe/reunis/data/vacunas-covid19.asp

Esa información la registra en un data frame.

```{r}
aplic.vacun=c(23840964)
Una.dosis=c(14383248)
Dos.dosis=c(9457716)
Hoy.vacun=c(9978)
Oct.vacunaton=c(845258)
data2=data.frame(aplic.vacun,Una.dosis,Dos.dosis,Hoy.vacun,Oct.vacunaton)
export(data2,"data2.sav")
```

## 3. Base de datos sobre los Centros de Vacunación COVID-19 en el Perú

Los datos los obtiene del portal de datos abiertos del gobierno que se hace referencia en las instrucciones: https://www.datosabiertos.gob.pe/

```{r}
data3=import("https://cloud.minsa.gob.pe/s/96XbzfYBCGcwtp7/download") #también podía descargarlo y cargarlos desde su PC: https://www.datosabiertos.gob.pe/dataset/centros-de-vacunacion
export(data3,"data3.sav")
```

## 4. Base de datos sobre la Programación Vacunación COVID-19 en el Perú

Los datos los obtiene del portal de datos abiertos del gobierno que se hace referencia en las instrucciones: https://www.datosabiertos.gob.pe/

```{r}
data4=import("https://cloud.minsa.gob.pe/s/2JDNRLMGs4CmngN/download") #también podía descargarlo y cargarlos desde su PC: https://www.datosabiertos.gob.pe/dataset/programacion-de-vacunas
export(data4,"data4.sav")
```

## 5. Un mapa del Perú por distritos.

Los datos los obtiene de GEO GPS Perú, portal que se hizo referencia en la clase: https://www.geogpsperu.com/

+ En primer lugar, debía descargar el shapefile correcto de la siguiente dirección: https://www.geogpsperu.com/2018/02/limite-distrital-politico-shapefile-ign.html

+ Luego, debía convertirlo en formato topojson con mapshaper(https://mapshaper.org/); desde ahí, subia los archivos de la carpeta, los simplificaba como topojson.

+ Finalmente, subía ese archivo a GitHub. Las instrucciones no requerían necesariamente que usted abra en mapa en R, solo se solicitaba el archivo topojson


**Todos los archivos obtenidos, debía cargarlos en su repositorio github, además de los códigos utilizados en formato html**
