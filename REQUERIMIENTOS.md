# Caso de Uso para MVP con AI

# Presentacion

- Casos de aplicacion
  - Mejorar mesa ayuda
  - Recetas
  - Jurisprudencia
  - Recomendaciones en funcion de historia en los "documentos"
  - Copilot propietario
  - Nutricion
  - Formacion inicial de Personal
- Pros/Contra de AI local/nube
- Ejecucion en funcion de respuestas de la IA

# Producto DEMO
## Objetivo
Desarrollar un sistema basado en inteligencia artificial que mejore la gestión y consulta de información en una empresa utilizando datos de fuentes estáticas (documentos) y dinámicas (actividad en GitLab privado). Este sistema facilitará la búsqueda de información relevante y generará documentación automatizada a partir de los datos existentes.

## Actores Principales
- **Usuario del sistema**: Cualquier miembro del equipo (desarrolladores, gerentes de proyectos, etc.) que necesite consultar documentación, actividad de proyectos, o solicitar generación de documentación mejorada.
- **Chatbot privado**: Interfaz de consulta que permite al usuario acceder a la información del proyecto y la documentación.
- **Agente de generación de documentación**: Componente encargado de crear documentación mejorada a partir de los datos de los pasos 1 y 2.

## Flujo de Trabajo del MVP

### 1. Entrenamiento del Modelo a partir de Documentos Estáticos
- El sistema utiliza un conjunto de documentos Word y PDF estáticos que contienen documentación de guías, especificaciones técnicas y otros datos relevantes.
- Se realiza un fine-tuning del modelo AI con estos documentos, adaptándolo para entender el lenguaje y los temas específicos de la empresa.
- Este proceso asegura que el sistema pueda comprender y generar respuestas relevantes y precisas basadas en estos documentos.

### 2. Consulta de Información Dinámica utilizando RAG
- El sistema implementa Retrieval-Augmented Generation (RAG) para extraer información actualizada de un GitLab privado.
- Permite consultar:
  - Miembros del equipo y sus roles en los proyectos.
  - Issues abiertos, cerrados o pendientes en proyectos.
  - Actividad reciente como commits y merge requests.
- Al combinar el modelo fine-tuned con RAG, el sistema puede generar respuestas contextualizadas utilizando tanto la información estática de los documentos como la dinámica del GitLab.

### 3. Chatbot Privado para Consulta
- El sistema integra un chatbot privado que permite a los usuarios realizar preguntas como:
  - “¿Quién está asignado al issue #123?”
  - “Muéstrame los commits recientes en el proyecto X.”
  - “¿Cómo se implementa X según la documentación?”
- El chatbot busca en la base de datos de documentos estáticos y en el GitLab para proporcionar respuestas precisas.

## Caso de Uso Detallado

**Caso**: Juan, un gerente de proyectos, necesita saber quién está trabajando en el issue #567 del proyecto "WebApp" y también quiere un resumen de la actividad de los últimos 7 días.

**Flujo**:
1. Juan accede al chatbot privado y hace la consulta: “¿Quién está trabajando en el issue #567?”
2. El chatbot utiliza RAG para buscar en el GitLab privado y responde con la lista de miembros asignados.
3. Juan luego solicita: “Dame un resumen de la actividad de la última semana en el proyecto WebApp.”
4. El chatbot responde con un resumen generado por el agente, que incluye los commits recientes, cambios en issues y un resumen de la documentación relacionada.

## Beneficios
- Ahorro de tiempo al automatizar consultas repetitivas y la generación de documentación.
- Actualización continua gracias a la integración con GitLab y la capacidad de generar respuestas contextuales con RAG.
- Mejora en la documentación con un agente que proporciona reportes y documentación actualizados basados en la actividad real de los proyectos.

Este MVP proporciona una solución eficiente para gestionar tanto documentación estática como dinámica, mejorando la productividad y organización del equipo.

## IMPLEMENTACION

## UI

- Permite setear una carpeta compartida en samba con archivos PDF, WORD y Excel. Permite hacer preguntas respecto a estos documentos.
- Permite setear un conector a gitlab o github para hacer preguntas sobre issues, miembros, actividad, etc.
- Permite de alguna forma generar archivos actualizados en funcion de lo que conece de los puntos anteriores.
