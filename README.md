# RNN del agua de jamaica

Widget didáctico e interactivo para explicar, paso a paso, cómo una **red neuronal recurrente (RNN)** lee una frase y la clasifica en **positivo**, **negativo** o **neutral**.

Frase de ejemplo: *«El agua de jamaica fría está sabrosa aunque al tiempo no está tan mal»*.

**Demo en línea:** https://nanperez.github.io/example-rnn/

## Qué incluye

1. **Mini dataset etiquetado** (27 frases, 9 por clase). Se pueden agregar o eliminar frases; los cambios se guardan en el navegador de cada persona.
2. **De palabras a números**: tokenización, vocabulario, `<UNK>` y embeddings.
3. **Arquitectura**: ecuaciones de una RNN simple tipo Elman y tabla de parámetros aprendidos.
4. **Entrenamiento** con descenso de gradiente y retropropagación en el tiempo (BPTT), con curvas de pérdida y exactitud.
5. **Lectura paso a paso**: cálculo de cada estado oculto h_t y mapa de calor de la memoria.
6. **Clasificación final** con softmax y prueba de frases nuevas.

Además permite **comparar one-hot contra embedding aprendido**, con validación cruzada dejando una fuera.

## Hiperparámetros que ajusta el usuario

| Hiperparámetro | Qué controla |
|---|---|
| Representación de palabras | Embedding aprendido u one-hot |
| `d` | Dimensión del embedding |
| `H` | Tamaño del estado oculto (memoria) |
| `η` | Tasa de aprendizaje |
| Épocas | Recorridos completos del dataset |
| `c` | Recorte de gradiente |
| Semilla | Pesos iniciales y orden de las frases |

Parámetros que aprende la red: `E`, `W_xh`, `W_hh`, `b_h`, `W_hy`, `b_y`.

## Uso

Es un solo archivo `index.html`, sin dependencias ni compilación; todo el entrenamiento ocurre en el navegador. Solo carga tipografías de Google Fonts (si no hay conexión, usa las del sistema).

Para verlo localmente basta con abrir `index.html` en el navegador.

### Publicar en GitHub Pages

1. Crea un repositorio público (por ejemplo `example-rnn`) y sube `index.html`, `README.md` y `.nojekyll`.
2. En **Settings → Pages**, elige *Deploy from a branch*, rama `main`, carpeta `/ (root)`.
3. En uno o dos minutos queda disponible en `https://<usuario>.github.io/example-rnn/`.

## Fuentes

El ejemplo está basado en:

- Video: <https://www.youtube.com/watch?v=x6E44DDWg5Q>
- Jurafsky, D. y Martin, J. H. *Speech and Language Processing* (3.ª ed., borrador). Capítulo 14: «RNNs and LSTMs». <https://web.stanford.edu/~jurafsky/slp3/14.pdf>

## Declaratoria de uso de IA generativa

Este material se desarrolló con apoyo de inteligencia artificial generativa (Claude Opus 5.5, de Anthropic), bajo la supervisión de la Dra. Nancy P.C., Instituto de Investigaciones en Inteligencia Artificial, Universidad Veracruzana.

La herramienta se usó para generar el código del widget, el mini dataset de ejemplo y los textos explicativos. La autora definió los objetivos didácticos, la frase de ejemplo, las clases, los requisitos de interactividad y las fuentes de referencia; además revisó, ajustó y validó el contenido final. La responsabilidad sobre el material es de la autora.

Octubre de 2026.
