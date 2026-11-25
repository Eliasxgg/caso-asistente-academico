# Validación y límites

La evidencia corresponde a la versión Flask y a su laboratorio local con datos ficticios, comprobados el **25 de noviembre de 2026**.

## Validación funcional

La suite de la implementación privada terminó con **30 pruebas aprobadas**. Utiliza SQL Server y el modelo del laboratorio, no una conexión institucional. El resultado está registrado en la revisión privada de la preparación; este repositorio no distribuye los tests ni su código.

| Grupo de casos | Qué se comprobó |
|---|---|
| Arranque y modelo | Salud de la aplicación, carga del modelo, 18 salidas, presencia de BiLSTM y dataset de 480 frases |
| Consultas académicas | Horarios, materias, docentes, aulas, evaluaciones, eventos y contactos |
| Perfiles y sesiones | Sesiones separadas, cierre y rechazo de perfiles fuera de la demo |
| Acceso SQL | Parámetros de consulta, denegación de actualización para el usuario lector y evaluaciones personales separadas entre perfiles |
| Fechas | Consulta de una fecha ISO válida y manejo de una fecha imposible |
| Peticiones y errores | Entrada inválida, longitud, origen de la petición y error sin detalles internos al cliente |

Una prueba de estas funciones no equivale a una auditoría de seguridad integral ni a una medición de capacidad bajo carga.

## Qué se observa directamente en las capturas

El [registro de evidencias](EVIDENCIAS.md) vincula cada imagen con la pregunta realizada y el resultado visible. Se comprobó el recorrido en el navegador: ingreso del perfil ficticio, consulta y presentación de respuesta dentro de la interfaz. Las capturas son evidencia de esos ejemplos, no de todos los posibles mensajes.

En particular, la imagen de evaluaciones muestra las del perfil Uno. La exclusión de la evaluación privada del perfil Dos se comprobó además mediante las pruebas SQL; una sola captura no demuestra por sí misma todos los controles de separación.

## Lo que no significa el resultado

- **30 pruebas aprobadas no es 100 % de exactitud del bot.** Son casos funcionales seleccionados.
- **480 frases no son 480 consultas independientes de evaluación.** Corresponden al entrenamiento.
- **18 intenciones no implican comprensión general.** La salida se limita a etiquetas del dominio y reglas programadas.
- **La puntuación no es exactitud.** El modelo puede asignar una puntuación alta a una intención incorrecta.
- **Las reglas y el modelo se evalúan por separado.** En las capturas se observa que las reglas resuelven las consultas mostradas; no se presentan esas respuestas como aciertos exclusivamente neuronales.

No se realizó una evaluación independiente de lenguaje libre de esta versión. No se traslada aquí el resultado de evaluación de una variante anterior del proyecto.

## Límites conocidos

Los nombres incompletos, alias y coincidencias difusas pueden llevar a identificar una materia equivocada. Las preguntas compuestas, ambiguas o ajenas al dominio pueden producir respuestas inadecuadas. La aplicación es un prototipo; el perfil ficticio no demuestra autenticación ni control de acceso para estudiantes reales.

Las fechas se generan al inicializar el laboratorio y permanecen guardadas. Conforme pasa el tiempo, una evaluación deja de estar dentro del período de próximas actividades. Las capturas conservan lo observado en su fecha y no representan un calendario actualizado.

## Mejoras propuestas

1. Crear una evaluación separada, con frases nuevas por intención y consultas fuera de dominio; revisar errores por clase, no solo un total.
2. Detectar materias o fechas ambiguas y pedir aclaraciones antes de consultar.
3. Revisar alias con materias similares y ampliar pruebas de aislamiento de datos.
4. Antes de un piloto real, definir permisos, autenticación, autorización y tratamiento de datos con la institución correspondiente.

Estas acciones son propuestas para evolucionar el prototipo. No se afirma haber medido satisfacción, ahorro de tiempo, adopción institucional ni reemplazo de un servicio universitario.
