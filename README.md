# Datat-n-1

1.Base de datos sobre cronología de epidemias, que contenga información sobre al menos su duración y el patógeno que la ocasionó. 
```{r}
library(htmltab)
link = "https://es.wikipedia.org/wiki/Anexo:Cronolog%C3%ADa_de_epidemias"
path = "/html/body/div[3]/div[3]/div[5]/div[1]/table[2]/tbody"
install.packages("htmltab")
dataWS = htmltab(link, path)
head(dataWS)
```
