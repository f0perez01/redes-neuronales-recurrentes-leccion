# Motivación: ¿Por qué RNN?
- Redes tradicionales (MLP, CNN) no capturan dependencias en secuencias.
- Necesitamos **memoria** para tareas secuenciales (texto, series de tiempo, video).
- Limitación: los modelos vistos hasta ahora tratan cada dato como independiente.

# La idea central de las RNN
- Introducen **recurrencia**: el estado oculto mantiene información del pasado.
- Fórmula básica:  
  `h_t = g(f1(x_t), f2(h_{t-1}))`
- Componentes:  
  - x_t: entrada en el paso t  
  - h_t: estado oculto (memoria)  
  - f1, f2: funciones paramétricas entrenables  
  - t: paso de la secuencia (tiempo u orden).

# RNN como redes de memoria
- El estado oculto h_t resume la historia de la secuencia.  
- Analogía: CNN capturan estructura espacial, RNN capturan estructura temporal.  
- Variantes de salida:  
  - Una salida por cada paso (muchos a muchos).  
  - Una salida final (muchos a uno).  
- Se pueden apilar múltiples capas.

# Aplicaciones de RNN
- Seguimiento en videos.  
- Predicción de sentimiento (incluye RNN bidireccionales).  
- Generación de texto.  
- Captioning de imágenes (CNN + RNN).  

# Entrenamiento de RNN
- Función de pérdida depende de la tarea (cross-entropy, MSE, ranking).  
- Entrenamiento con **Backpropagation Through Time (BPTT)**.  
- Problemas principales:  
  1. **Costo computacional alto** → *truncated backprop*.  
  2. **Vanishing y exploding gradients** → dificultad en secuencias largas.

# Soluciones a los problemas
- **GRU (Gated Recurrent Unit):**  
  - Compuertas de actualización y reset.  
  - Controlan qué se olvida y qué se agrega.  
- **LSTM (Long Short-Term Memory):**  
  - Introducen celda de memoria separada del estado.  
  - Mantienen un flujo de gradiente estable.  
- En la práctica: GRU y LSTM son los más usados.

# Caso de estudio: Image Captioning
- *Automated Image Captioning* (Karpathy & Fei-Fei Li, 2015).  
- CNN extrae características visuales.  
- RNN genera la descripción secuencial de la imagen.  
- Ejemplo de combinación de arquitecturas.

# Conclusiones
- RNN permiten modelar secuencias de largo arbitrario.  
- El compartir parámetros recurrentes les da gran poder y flexibilidad.  
- Usadas en muchos dominios (texto, audio, video, biomedicina).  
- Problemas de gradiente en secuencias largas resueltos con LSTM y GRU.  

# Lecturas recomendadas
- Understanding LSTM Networks: http://colah.github.io/posts/2015-08-Understanding-LSTMs/  
- Exploring LSTMs: http://blog.echen.me/2017/05/30/exploring-lstms/  
- Visualizing memorization in RNNs: https://distill.pub/2019/memorization-inrnns/  
- The Unreasonable Effectiveness of RNNs (Karpathy): http://karpathy.github.io/2015/05/21/rnn-effectiveness/
