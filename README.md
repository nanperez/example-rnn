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

## Créditos

Material de divulgación · Dra. Nancy P.C. · Instituto de Investigaciones en Inteligencia Artificial, Universidad Veracruzana.
