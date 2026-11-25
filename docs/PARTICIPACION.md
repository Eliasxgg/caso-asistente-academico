# Participación, aprendizajes y procedencia

## Contexto del trabajo

Bot Antijosué fue un proyecto grupal de Sistemas Expertos, ciclo 8 de 2025. La idea fue explorar consultas más específicas de información académica en una simulación. No fue una integración autorizada con la base real de la universidad ni una sustitución de su bot oficial.

## Mi participación

En clase practiqué las bases de TensorFlow/Keras. Para el trabajo final participé aportando el contexto, horarios y pensum de referencia del equipo, planteando cómo esperábamos que respondiera el bot y revisando los resultados de las consultas. La base académica combinaba referencias reales del grupo con registros inventados; por eso no se utiliza en esta presentación pública.

El alcance que puedo explicar a partir del proyecto es inicial: clasificación de intenciones, relación entre entidades y consultas, integración de Python con SQL Server y revisión de un prototipo web. No presento la presencia de una BiLSTM en el código como prueba de dominio avanzado de redes recurrentes ni atribuyo todo el desarrollo a una sola persona.

## Uso de IA

Utilizamos IA de forma importante para construir y ajustar el bot, la interfaz y la integración SQL. El grupo planteaba preguntas, pedía cambios y comprobaba respuestas; gran parte de la implementación final fue asistida. Esto se distingue de los ejercicios básicos escritos manualmente en clase.

La preparación de noviembre de 2026 también fue asistida por el agente: organización del entorno Docker, datos ficticios, configuración privada, compatibilidad de dependencias, carga del modelo, correcciones, pruebas y documentación. No atribuyo retrospectivamente esas mejoras al desarrollo manual del ciclo académico.

## Qué conserva la adaptación

Se utiliza como base la versión Flask del proyecto, con su interfaz, lógica de respuestas y extractor de entidades. Se conserva la familia de arquitectura BiLSTM y el conjunto de intenciones encontrado en esa versión. La adaptación hace explícito el entrenamiento y la combinación con reglas, y permite ejecutar un laboratorio con una base ficticia separada.

Entre las correcciones posteriores se encuentran la configuración SQL por entorno, la clave de sesión aleatoria, el escape de mensajes antes de mostrarlos, el manejo de fechas y el filtro por estudiante de las evaluaciones personales. Son mejoras de preparación; no resultados de un despliegue institucional.

## Recursos y publicación

Esta carpeta contiene únicamente el caso documental y capturas de la demostración. No se redistribuyen la implementación, modelos, frases de entrenamiento, scripts SQL, respaldos ni registros académicos originales. No se declara una licencia permisiva sobre el código del equipo. Las tecnologías mencionadas conservan sus respectivas licencias y marcas.

El objetivo de este caso es mostrar con transparencia qué resolvía el prototipo, qué aprendí, cómo se comprobó y qué falta mejorar.
