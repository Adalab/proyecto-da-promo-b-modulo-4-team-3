# PROYECTO MODULO 4 - EQUIPO 3

## OBJETIVO: EVALUAR PRESENCIA MUJER EN EL CINE

### DOS ENFOQUES:

- Mujer en industria (en puestos de poder)
- Mujer en la trama

#### ***Mujer en industria***

Para ello hemos recogido datos de un dataset denominado "The Movies Dataset": https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset

Hemos recopilado informacion acerca de las películas (incluyendo, titulo, id, y imdb_id), género cinematográfico, personal que trabaja en los diferentes departamentos que han participado en la película, y año de lanzamiento.  

Todo esto nos ha permitido obtener insights valiosos para poder extraer conclusiones acerca de esta cuestión. 

Para poder realizar la preparación de los datos hemos usado dos csv, uno llamado metadata y otro llamado credits. 

En algunos campos la información estaba dentro de listas que contenian strings y dentro diccionarios ["{}"] por lo que para extraer los datos además de iterar la lista hemos necesitado importar la libreria ast para usar un método llamado ast.literal_eval() que permitia "quitar" los strings y acceder al diccionario que encerraban.  



#### ***Mujer en la trama***

En este caso el enfoque es distinto, tratar de valorar si la mujer es relevante para el desarrollo de la trama. 

Lo hemos hecho a traves del test de Bechdel, que califica las peliculas una de estas 5 categorías:

- ok: Mujeres tienen conversaciones importantes para la trama entre ellas y un papel relevante en general. 

- no talk: Las mujeres no tienen ninguna conversacion relevante entre ellas. 

- men: Las mujeres sí tienen conversaciones relevantes entre ellas pero todas acerca de hombres. 

- no woman: No hay mujeres con importancia en la trama. 

- dubious: Cajón de sastre donde se mete aquello que es un poco ambiguo y no se sabe muy bien como calificarlo. 

En base a estos 5 puntos las peliculas se puntuan como PASS (supera el test de Bechdel) o FAIL (no supera el test de Bechdel)

Los datos los hemos extraido de: https://data.world/carolee/women-in-movies/workspace/file?filename=movies.csv

Estas películas las hemos relacionado mediante el metodo de pandas merge con el csv limpio de industria usando el imdb id presente en ambos csv. 

La información adicional que aporta el csv de bechdel test es: puntuacion (clean_test (ok, men, no talk, no woman, dubious) y binary (PASS o FAIL)), además de aportar información sobre presupuesto, ingresos domésticos e internacionales reales y ajustados al año 2013 (para poder realizar comparativas más justas entre años diversos (valoramos desde 1971 hasta 2013)).



