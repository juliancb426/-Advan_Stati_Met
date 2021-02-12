# Métodos Estadísticos Avanzados - Competencia
### Por: Andrés Franco, Julián Castelblanco, Alirio Rodríguez

En el repositorio encontrarán documentos archivos, los cuales contienen cada uno de los modelos presentados para la competencia.
Distribuidos de la siguiente forma:

- En la actividad realizada se utilizó las siguientes bases de datos:
  1. "datacountstudents.csv": Modelos de conteo. 
  2. "datacontinuousstudents.csv": Modelos continuos.
  3. "databinarystudents.csv": Modelos de clasificación binaria.
  4. "datasetx.csv": Base de prueba de los modelos seleccionados.
  
- Los domentos explicativos de la actividad realizada son los siguientes:
  1. Model_Count.html 
  2. Model_Continuos.html
  3. Model_Binary.html
  
- También se anexa el código realizado en **RMarkdowm**, presentados de la siguiente forma:
  1. Model_Count.Rmd
  2. Model_Continuos.Rmd
  3. Model_Binary.Rmd
  
- Por último, se anexa las *y_estimadas* por los modelos seleccionados:
  1. y_count.csv
  2. y_continua.csv
  3. y_binaria.csv
  
  **Nota:** la actividad corresponde al documento *task.pdf*.




clean_data<- function(X) {
    X <- str_to_upper(X, locale = "es")
    X <- str_replace_all(X,"[_]", " ")
    X <- str_replace_all(X,"[\\s]+", " ")
    X <- str_replace_all(X,"\\s+$", "")
    X <- str_replace_all(X,"`", "'")
    X <- str_replace_all(X,"´", "'")
    X <- str_replace_all(X,"Ã±", "Ñ")
    X <- str_replace_all(X,"Ã©", "É")
    X <- str_replace_all(X,"Ã-", "Í")
    X <- str_replace_all(X,"Ã", "Í")
    X <- str_trim(X, side = "both")
    X <- chartr('ÁÉÍÓÚ','AEIOU',X)
    return(X)
  }
