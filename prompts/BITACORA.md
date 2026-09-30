# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: (escribe aqui cual usaste)

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot |5/5 |tabla con explicaciones y notas |no |
| One-shot |5/5 |lista enumerada con respuestas |si |
| Few-shot |5/5 |lista con respuestas |si |


## Ejercicio 3: Chain of Thought
| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo |Solo muestra el calculo de la respuesta, pero no indica el origne de los datos   |si |si |
| Paso a paso |Muestra el paso a paso del proceso del calculo, incluyendo el origen de los datos y toda la descomposición del problema |si |si |


## Ejercicio 4: Role prompting
| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol |sencillo |si |pricipiante interezado en programar |
| B. Rol docente |sencillo |si |estudiante de programacion |
| C. Rol senior |tecnico |si |miembros de un equipo para explicar a sus compañeros |

## Ejercicio 5: Descomposicion
| Comando | Respuesta | Comparacion |
|-------------------|----------------------|------------------------------|
|Voy a crear un sistema de inventario para una tienda pequena en Java. Lista los 5 requisitos principales del sistema.|Entrego los requisitos detalados y una nota sobre su uso |En el pedido directo la IA entrego un sistema ya hecho sin especificar datos , metodos , requisitos ... |
|Con esos requisitos, disena las clases necesarias. Para cada clase indica sus atributos con su tipo de dato.|La IA entrego un reporte detallado de las clases las bibliotecas que usarian y la explicacion de que haria cada metodo de cada clase|En el pedido directo la IA entrego un sistema ya hecho sin especificar datos , metodos , requisitos ...|
|Escribe el codigo Java de la clase Producto con sus atributos, un constructor y los metodos get y set.|La IA entrego el codigo completo y especifico algunos detalles|En el pedido directo la IA entrego un sistema ya hecho sin especificar datos , metodos , requisitos ...|
|Revisa el codigo de la clase Producto y propone 3 mejoras concretas.|La IA detallo las mejoras y entrego el codigo de estas explicando tambien el motivo de ellas|En el pedido directo la IA entrego un sistema ya hecho sin especificar datos , metodos , requisitos ...|
## Ejercicio 6: Prompt estructurado y autocritica
```text
prompt estructurado 
    <rol>Actua como analista de pruebas de software.</rol>
    <contexto>Login web con correo y contrasena. La cuenta se bloquea
    despues de 3 intentos fallidos.</contexto>
    <tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.
    </tarea>
    <formato>Tabla con las columnas: ID, escenario, datos de entrada,
    resultado esperado.</formato>

mensaje de autocritica
    Revisa tu tabla: faltan casos limite como campos vacios, correo sin @
    o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

