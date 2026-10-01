# Tarea: Mi prompt avanzado

## Tarea elegida

Diseñar las clases de un sistema de notas sencillo en Java para estudiantes de segundo ciclo.

## Version 1: prompt basico

```text
Diseña las clases de un sistema de notas en Java.
```
## Técnica agregada
En esta primera versión no agregué una técnica específica. Fue un prompt básico para observar qué respuesta generaba la IA.

## Qué mejoró en la respuesta

```text
La IA propuso clases como Estudiante, Curso, Nota, Matricula y SistemaNotas, indicando sus atributos y funciones. Sin embargo, la respuesta era general y no especificaba un rol, un formato concreto ni un proceso de desarrollo.
```

## Version 2: prompt basico
```text
Actua como docente de Java para estudiantes de segundo ciclo. Diseña las clases de un sistema de notas en Java.

Para cada clase indica:
- Nombre de la clase.
- Atributos con su tipo de dato.
- Responsabilidad de la clase.

Al final muestra las relaciones principales entre las clases en una lista.
Usa lenguaje sencillo y evita agregar clases innecesarias.
```
## Técnica agregada
Agregué role prompting, indicando que la IA debía actuar como docente de Java para estudiantes de segundo ciclo. También definí un formato de respuesta y el nivel de lenguaje.

## Qué mejoró en la respuesta
```text
La respuesta se adaptó mejor al nivel de un estudiante de segundo ciclo. La IA organizó cada clase indicando sus atributos y responsabilidades y redujo la cantidad de clases a cuatro. También explicó las relaciones entre ellas de una manera sencilla.
```

## Version 3: prompt final
```text
Actua como docente de Java para estudiantes de segundo ciclo.

<contexto>
Necesito diseñar las clases de un sistema de notas sencillo en Java.
El sistema debe permitir representar estudiantes, cursos y sus notas.
Quiero una solución adecuada para un estudiante de segundo ciclo,
sin agregar clases innecesariamente complejas.
</contexto>

<tarea>
Desarrolla la solución en 3 pasos:

1. Lista los requisitos principales del sistema.
2. Diseña las clases necesarias indicando para cada una:
   - nombre de la clase
   - atributos y tipos de datos
   - responsabilidad
3. Explica las relaciones principales entre las clases.

Ejemplo del formato de una clase:
Clase: Estudiante
Atributos:
- int id
- String nombre
Responsabilidad:
- Guardar los datos básicos del estudiante.

Después revisa tu propuesta y comprueba que las clases sean necesarias,
que sus responsabilidades no se repitan y que la estructura sea coherente
para un proyecto sencillo de Java.
</tarea>

<formato>
Presenta la respuesta con títulos y listas.
Usa lenguaje sencillo.
Al final incluye una sección llamada "Revisión final" con 3 puntos.
</formato>
```
## Técnica agregada
En esta versión agregué descomposición, few-shot, autocrítica y prompt estructurado. También mantuve el role prompting de la versión anterior.

## Qué mejoró en la respuesta
```text
La respuesta final fue más completa y ordenada. Primero obtuvo los requisitos, después diseñó las clases y finalmente explicó sus relaciones. El ejemplo ayudó a indicar el formato esperado y la revisión final permitió comprobar que las clases no fueran innecesarias ni tuvieran responsabilidades repetidas.
```

## Tecnicas usadas en el prompt final

| Técnica | Parte del prompt final | Para qué se utilizó |
|---------|------------------------|---------------------|
| Role prompting | `Actua como docente de Java para estudiantes de segundo ciclo.` | Adaptar la explicación al nivel del estudiante. |
| Prompt estructurado | `<contexto>`, `<tarea>` y `<formato>` | Organizar las instrucciones y hacerlas más claras. |
| Descomposición | `Desarrolla la solución en 3 pasos` | Dividir el problema en requisitos, clases y relaciones. |
| Few-shot | `Ejemplo del formato de una clase` | Mostrar a la IA un ejemplo del formato esperado. |
| Autocrítica | `Después revisa tu propuesta...` | Comprobar que las clases sean necesarias y que sus responsabilidades no se repitan. |

## Evaluacion del resultado

| Criterio | Cumple | Observación |
|----------|--------|-------------|
| Tiene un rol específico | Sí | Se indicó el rol de docente de Java para estudiantes de segundo ciclo. |
| Tiene un formato de respuesta definido | Sí | Se solicitaron títulos, listas y una sección de revisión final. |
| Incluye al menos tres técnicas | Sí | El prompt final combina cinco técnicas. |
| La respuesta está dividida en pasos | Sí | Incluye requisitos, diseño de clases y relaciones. |
| Incluye una revisión del resultado | Sí | La IA agregó una sección de Revisión final con tres puntos. |

## Por que elegi estas tecnicas

Elegí estas técnicas porque necesitaba que la IA entendiera el nivel de conocimiento del estudiante y que la solución no fuera demasiado compleja. El role prompting ayuda a adaptar la explicación al nivel de segundo ciclo. La descomposición permite dividir el diseño en partes más fáciles de revisar. El few-shot ayuda a mostrar el formato que quiero obtener y la autocrítica permite revisar si las clases propuestas son necesarias y si sus responsabilidades están bien separadas. Finalmente, el prompt estructurado permite organizar todas las instrucciones de manera clara.