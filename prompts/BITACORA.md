# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.

Herramienta de IA usada: ChatGPT

## Ejercicio 2: Zero-shot, one-shot y few-shot

### Resultados

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Sí/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot | 5 | Número, etiqueta y explicación del comentario | No |
| One-shot | 5 | Comentario -> etiqueta | Sí |
| Few-shot | 5 | "Comentario" -> etiqueta | Sí |


### Observación

Observé que los tres prompts lograron clasificar correctamente los comentarios, pero el formato de las respuestas fue diferente. Con few-shot la IA siguió de manera más clara el formato de los ejemplos, por lo que los ejemplos ayudan a controlar mejor cómo queremos recibir la respuesta.

## Ejercicio 3: Chain of Thought
### Resultados

| Pedido | Respuesta de la IA | Muestra los pasos (Sí/No) | Correcta (Sí/No) |
|--------|--------------------|---------------------------|------------------|
| Directo | 318.60 | No | Sí |
| Paso a paso | 318.60 | Sí | Sí |

### Observación
Ver los pasos es útil porque permite revisar cómo la IA llegó al resultado y detectar en qué parte podría estar un error. En este caso, la respuesta directa fue correcta, pero la respuesta paso a paso permitió comprobar cada cálculo antes de aceptar el resultado final.

## Ejercicio 4: Role prompting
### Resultados

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|--------------------------------|-----------------------|----------------------|
| A. Sin rol | Sencillo | Sí, usa ejemplos y código | Una persona que está empezando |
| B. Rol docente | Muy sencillo | Sí, usa ejemplos, analogías y código | Estudiantes que nunca han programado |
| C. Rol senior | Técnico | Sí, usa código y conceptos de Java | Un desarrollador o estudiante con experiencia |

### Observación

Observé que al cambiar el rol también cambió la forma de explicar la variable. El rol docente utilizó ejemplos y palabras más sencillas, mientras que el rol de desarrollador Java senior utilizó términos más técnicos y conceptos específicos de Java. La versión sin rol quedó en un punto intermedio.

## Ejercicio 5: Descomposicion

### Resultado del pedido de una sola vez

Al pedir directamente que se cree un sistema de inventario, la IA entregó un sistema completo en Python. Incluyó opciones para mostrar productos, agregar productos, actualizar stock, buscar productos y salir.

### Resultado por pasos

**Paso 1:** La IA propuso 5 requisitos principales para el sistema: registrar, consultar, actualizar stock, eliminar y buscar productos.

**Paso 2:** A partir de esos requisitos, diseñó 3 clases en Java: `Producto`, `Inventario` y `SistemaInventario`, indicando sus atributos y responsabilidades.

**Paso 3:** La IA creó el código de la clase `Producto` en Java con sus atributos, un constructor y los métodos get y set.

**Paso 4:** La IA revisó el código y propuso 3 mejoras: validar el precio y la cantidad, validar los datos dentro de los métodos set y agregar el método `toString()`.

### Comparación

El pedido de una sola vez produjo directamente un sistema completo en Python, mientras que la descomposición permitió trabajar el sistema por partes y obtener primero los requisitos, después el diseño de clases, luego el código de `Producto` y finalmente algunas mejoras. Al dividir el problema, fue más fácil seguir el proceso de desarrollo y revisar cada parte antes de continuar.


## Ejercicio 6: Prompt estructurado y autocritica

### Prompt estructurado

```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea
despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada,
resultado esperado.</formato>
```
### Autocritica
```text
Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste.
```

### Evaluación

| Criterio | Cumple | Observación |
|----------|--------|-------------|
| Tiene 4 columnas solicitadas | Sí | La tabla contiene ID, escenario, datos de entrada y resultado esperado. |
| Considera el bloqueo después de 3 intentos | Sí | Incluye el caso CP-03 y el intento de acceso después del bloqueo en CP-04. |
| Incluye campos vacíos | Sí | La autocrítica agregó CP-07, CP-08 y CP-09. |
| Indica qué casos fueron agregados | Sí | La IA indicó que agregó CP-07, CP-08, CP-09, CP-10, CP-11 y CP-12. |
| Evita casos repetidos o sin sentido | Sí | Los casos agregados cubren diferentes validaciones del login. |

### Observación

El prompt estructurado permitió obtener una respuesta más ordenada porque indicó el rol, el contexto, la tarea y el formato. Después de realizar la autocrítica, la IA detectó que faltaban casos de validación como campos vacíos, correo sin @ y contraseña con espacios. Esto permitió ampliar los casos de prueba y hacer la tabla más completa.