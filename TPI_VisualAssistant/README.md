**IFTS 24**
# Trabajo Práctico Integrador
# Procesamiento digital de imágenes

**Profesor:** Matías Barreto

**Estudiante:** Gabriela Pari Vaca

## Asistente Visual Interactivo por Voz

Este proyecto, desarrollado en un notebook de Google Colab, implementa un asistente inteligente capaz de ver, escuchar y responder. La aplicación permite a los usuarios interactuar con imágenes a través de comandos de voz, utilizando una combinación de modelos de inteligencia artificial de última generación para el reconocimiento visual, de voz y la generación de respuestas.

El objetivo principal es crear una interfaz hombre-máquina fluida e intuitiva, donde la cámara y el micrófono reemplazan las interacciones tradicionales de teclado y ratón.

### Objetivo del Proyecto

El propósito de esta aplicación es doble:

**Análisis Visual Conversacional:** Permitir que un usuario tome una fotografía usando la cámara de su dispositivo y realice preguntas en lenguaje natural (hablado) sobre el contenido de esa imagen. El sistema debe comprender la pregunta, analizar la imagen y generar una respuesta coherente en texto y voz.

**Interfaz de Usuario Avanzada:** Explorar el uso de interfaces multimodales en Gradio, integrando atajos de teclado (f para foto, v para voz) mediante JavaScript para ofrecer una experiencia de usuario más rápida y accesible, eliminando la necesidad de clics.

En esencia, el proyecto busca fusionar la visión por computadora con el procesamiento del lenguaje natural en una aplicación web interactiva y fácil de usar.


### Tecnologías Utilizadas

La aplicación se construye sobre un stack de tecnologías de Python y modelos de IA, orquestados dentro de un entorno de Google Colab con GPU.
Framework de la Aplicación

**Gradio:** Se utiliza como el framework principal para construir y desplegar la interfaz de usuario web de forma rápida. Permite manejar componentes complejos como la entrada de cámara (webcam), grabación de audio (microphone) y la inyección de JavaScript personalizado para atajos de teclado.

#### Modelos de Inteligencia Artificial

**google/paligemma-3b-mix-224 (PaliGemma):** Es el cerebro del asistente. Este potente modelo multimodal de Google es el encargado de la tarea de Visual Question Answering (VQA). Recibe una imagen y una pregunta en formato de texto para generar una respuesta relevante basada en el contenido visual.

**openai/whisper-tiny (Whisper):** Este modelo de OpenAI se utiliza para el Reconocimiento Automático de Voz (ASR o Speech-to-Text). Se encarga de tomar el audio grabado por el usuario a través del micrófono y transcribirlo a texto. Este texto luego se utiliza como la pregunta para PaliGemma. Se eligió la versión tiny para optimizar los tiempos de carga y el uso de recursos en el entorno de Colab.

### Librerías Principales de Python

**transformers de Hugging Face:** Es la librería clave que actúa como puente para descargar, cargar y utilizar los modelos pre-entrenados (PaliGemma y Whisper) de una manera estandarizada y eficiente.

**torch (PyTorch):** Es el framework de deep learning sobre el cual se ejecutan los modelos. Se encarga de las operaciones con tensores y de la asignación de cómputo a la GPU para acelerar la inferencia.

**gTTS (Google Text-to-Speech):** Esta librería se utiliza para la funcionalidad de Texto a Voz (TTS). Toma la respuesta en texto generada por PaliGemma y la convierte en un archivo de audio .mp3 en español, que luego se reproduce automáticamente en la interfaz.

**Pillow (PIL):** Se usa para el manejo y la manipulación de los datos de las imágenes capturadas por la cámara antes de ser procesadas por el modelo.

### Frontend

**JavaScript:** Se inyecta un pequeño script personalizado en la aplicación de Gradio para capturar eventos de teclado. Esto permite implementar los atajos de teclado ('f' y 'v'), mejorando significativamente la usabilidad y la velocidad de interacción.
