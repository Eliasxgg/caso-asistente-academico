# Resultados del proyecto y lo que aprendí

## Qué me permitió construir y entender

El resultado fue un prototipo capaz de responder consultas académicas a partir de una base de datos: materias, horarios, docentes, aulas, evaluaciones, eventos y contactos. Lo trabajamos en grupo, con asistencia importante de IA para la implementación.

El aprendizaje que destaco es **cómo relacionar una necesidad de información con la lógica de un programa y los datos necesarios para resolverla**. El bot no solo tenía que contestar: debía reconocer qué se estaba preguntando y consultar la información correspondiente.

## Python y la lógica de una respuesta

Al trabajar con el bot reforcé conocimientos básicos de Python y la lectura del recorrido del código: funciones que reciben datos, condiciones que seleccionan un comportamiento y estructuras que conservan la información obtenida.

Por ejemplo, una pregunta por un docente y una pregunta por un aula pueden referirse a la misma materia, pero requieren respuestas distintas. Eso me ayudó a comprender para qué sirven las condiciones y por qué conviene separar la recepción de la pregunta, la identificación de datos y la construcción de la respuesta.

Mi participación se centró en plantear cambios, preguntar cómo resolverlos y revisar el resultado de la implementación asistida. El aprendizaje estuvo también en entender la lógica que pedíamos y relacionarla con el comportamiento que observábamos.

## Fundamentos de TensorFlow y Keras

En clase practicamos de forma manual el funcionamiento básico de TensorFlow/Keras. Con el proyecto relacioné esa base con un problema concreto: **clasificar preguntas en intenciones**.

Me familiaricé con el recorrido de preparar ejemplos de texto, asociarlos con categorías, representarlos para el modelo, entrenarlo y utilizarlo para clasificar una nueva pregunta. Comprendí que las categorías y los ejemplos delimitan lo que el clasificador puede reconocer.

En esta versión hay 18 intenciones y 480 frases de entrenamiento. La presencia de una BiLSTM forma parte de la implementación asistida; lo que destaco personalmente es el aprendizaje inicial del proceso de clasificación y su integración en una aplicación. Mi siguiente paso es profundizar en la elección de arquitectura y en cómo evaluar el modelo por mi cuenta.

## Distinguir intención y entidad

Aprendí a separar **qué quiere saber la persona** de **sobre qué dato está preguntando**.

| Pregunta | Intención | Dato que hace falta identificar |
|---|---|---|
| ¿Quién da Sistemas Expertos? | Consultar el docente | Materia: Sistemas Expertos |
| ¿Dónde es Sistemas Expertos? | Consultar el aula | La misma materia |
| ¿Qué clases tengo el lunes? | Consultar el horario de un día | Día: lunes; perfil seleccionado |

Reconocer una intención no basta si se identifica mal la materia. Esta distinción me ayudó a entender por qué un bot puede responder con una frase bien formada y, aun así, no resolver la consulta correcta.

## Consultar datos relacionados en SQL Server

El proyecto me ayudó a comprender el papel de una base relacional detrás del bot. El estudiante se relaciona con sus horarios, el horario con una materia y la materia con un docente. Para responder hay que recorrer esas relaciones y seleccionar la información adecuada.

Por ejemplo, para «¿qué tengo el lunes?» no basta con tener una lista general de materias: se necesita el perfil, el día y el horario. Para responder por un docente, en cambio, se consulta la materia identificada y su profesor asociado.

La conexión y los scripts se construyeron con ayuda de IA. El aprendizaje que destaco es entender la relación entre los datos y la respuesta, además de trabajar con la integración de Python y SQL Server en un caso académico.

## Conectar interfaz, lógica y base de datos

Trabajar con la versión web me permitió relacionar tres partes de una aplicación: la pantalla donde se escribe, la lógica que procesa la consulta y la base que conserva la información.

La interfaz utiliza Flask para enviar la pregunta al programa y devolver su respuesta al chat. Comprender ese recorrido ayuda a ubicar dónde revisar un comportamiento: que una pregunta no se resuelva puede deberse a la intención, a la materia identificada o a la información consultada, no solamente al texto que se ve en pantalla.

Es un aprendizaje básico de integración: relacionar el recorrido de la petición con sus componentes y con la respuesta observada. La programación de la interfaz y de sus conexiones fue asistida.

## Definir y revisar el comportamiento esperado

Al orientar el proyecto aprendí a concretar una petición general como «que responda los horarios». Había que precisar de qué estudiante, qué día, qué materia y qué información debía aparecer.

Eso también cambió la forma de revisar las respuestas: no bastaba con recibir un mensaje. Teníamos que comprobar si correspondía a la pregunta y a los datos usados como referencia. Este aprendizaje se relaciona con análisis de necesidades, definición de requisitos y revisión funcional.

Las 30 pruebas automatizadas de la preparación actual son una mejora posterior asistida. Respaldan casos concretos del laboratorio; no se presentan como pruebas que escribí manualmente en clase ni como una medida de exactitud general.

## Decisiones que puedo explicar mejor a partir del caso

| Decisión | Qué ayuda a entender |
|---|---|
| Consultar registros para responder | El horario o docente debe salir de la información relacionada, no de una respuesta genérica memorizada |
| Separar intención y entidad | Dos preguntas pueden mencionar la misma materia y necesitar datos diferentes |
| Conservar la relación con el perfil | Compartir una materia no implica compartir todas las evaluaciones personales |
| Distinguir modelo y reglas | Una respuesta correcta puede provenir de una condición programada; eso no prueba un acierto del clasificador |
| Revisar consultas que fallan | Una puntuación alta no garantiza que se haya entendido bien la pregunta |

La adaptación de 2026 hace más visibles estas decisiones mediante diagnóstico, datos ficticios y pruebas. Las correcciones de esa etapa están diferenciadas del trabajo académico original en [Participación](PARTICIPACION.md).

## Qué aporta este proyecto a mi perfil

Este caso respalda **conocimientos básicos de Python, fundamentos de clasificación con TensorFlow/Keras y comprensión de la integración con SQL Server**. También muestra mi participación al convertir preguntas de un usuario en un comportamiento esperado y revisar si la información devuelta tiene sentido.

Esa base es útil para seguir aprendiendo sobre consultas de datos, integración de aplicaciones y diagnóstico funcional. El valor que muestro es el recorrido desde la pregunta hasta el dato, mi participación real y los aspectos que debo seguir practicando.

La [galería de evidencias](EVIDENCIAS.md) permite contrastar estos ejemplos con la interfaz. La [validación](VALIDACION_Y_LIMITES.md) distingue las funciones comprobadas de los límites del prototipo.
