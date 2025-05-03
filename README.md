#EJERCICIO 1
=========================================
paso 1: Crear repositorio

paso 2: Descargar e instalar docker

paso 3: Seleccionar archivo txt para recuento de palabras 

paso 4: Descargar archivo.pdf desde: https://xfrank.wordpress.com/wp-content/uploads/2011/11/harry-potter-71.pdf

paso 5: Convertir a formato .txt mediante la herramienta online https://www.pdf2go.com/ y convertirlo como .txt

paso 6: Descargar el script de docker: hadoop-mapreduce-examples-2.7.1-sources.jar

paso 7: Mover a la carpeta docker-hadoop el archivo harry-potter-71.txt y el script anteriormente descargado

paso 8: Acceder al contenedor mediante el comando:
"docker exec -it namenode bash", donde bash indica abrirlo en una máquina virtual desde Windows

paso 9: Crear la carpeta que alojara los archivos cargados mediante la instrucción: 

hdfs dfs -mkdir /user/root/entrada_contador

paso 10: Cambio a carpeta temporal:  cd /tmp

paso 11: Ejecutar proceso de Mapreduce:

hadoop jar hadoop-mapreduce-examples-2.7.1-sources.jar org.apache.hadoop.examples.WordCount entrada_contador salida_contador

paso 12: Observar resultados mediante la instrucción:

hdfs dfs -cat /user/root/salida_contador/*

paso 13: Validar que el archivo resultante se encuentre alojado en la carpeta

hdfs dfs -ls /user/root/salida_contador

paso 14: Exportar archivo resultante y nombrarlo:

hdfs dfs -cat /user/root/output_contador/part-r-00000 > /tmp/harry-potter-copy.txt

paso 15: Regresar a carpeta base y ejecutar: 

docker cp namenode:/tmp/harry-potter-copy.txt .

*Para validar que se haya copiado correctamente*

paso 16: Abrir archivo local para validar que se realizó correctamente.

#EJERCICIO 2 
##Sudoku
=========================================

paso 1: Descargar hadoop-examples-2.7.1-sources.jar

paso 2: Descargar puzzle1.dta

paso 3: Copiar ambos archivos a la carpeta temporal del contenedor

paso 4: Acceder al contenedor en el nodo maestro insertando la linea de codigo:

docker exec -it namenode bash en la terminal actual 

abriendo un nuevo shell emulando una terminal (uso en Windows)

paso 5: Acceder a la carpeta temporal y ejecutar la clase MapReduce/Sudoku para "resolver" el archivo puzzle1.dta

paso 6: Guardar el resultado en un archivo *solucion_puzzle1.dta*, salir del shell

paso 7: Copiar el archivo al repositorio de Github.

Nota: Intente replicar el ejercicio con un archivo diferente, pero la repuesta fue que no se encontraron ninguna solución  a pesar de ser un ejemplo ya resuelto extraído de Google. 

Revisar puzzle2_original.txt y puzzle2.dta




