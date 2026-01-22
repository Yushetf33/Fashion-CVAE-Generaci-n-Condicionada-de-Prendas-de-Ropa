# Fashion-CVAE: Generación Condicionada y Análisis del Espacio Latente 👗👟

Este proyecto implementa un **Autoencoder Variacional Condicional (CVAE)** utilizando **PyTorch** para la síntesis y manipulación de imágenes del dataset **Fashion-MNIST**. El modelo no solo es capaz de generar prendas de ropa desde cero, sino que permite un control preciso sobre la categoría de la prenda generada.



## 🚀 Características del Proyecto

* **Arquitectura Convolucional:** Utiliza capas `Conv2d` y `ConvTranspose2d` para capturar jerarquías espaciales y texturas en imágenes de 28x28.
* **Generación Condicionada:** Implementación de condicionamiento mediante vectores *one-hot* integrados tanto en el proceso de codificación como en el de decodificación.
* **Análisis Avanzado:** Incluye herramientas de diagnóstico visual para validar la calidad del espacio latente.

---

## 🧠 Estructura del Modelo

El modelo se divide en tres componentes principales:

1.  **Encoder:** Recibe la imagen y la etiqueta (mapeada a un canal extra). Comprime la información en parámetros estadísticos $\mu$ y $\sigma$.
2.  **Reparameterization Trick:** Permite el entrenamiento mediante backpropagation muestreando de la distribución latente sin romper el flujo del gradiente.
3.  **Decoder:** Toma un vector latente $z$ y una etiqueta de clase para reconstruir la prenda específica.



---

## 📊 Visualizaciones y Resultados

El repositorio incluye varios métodos de evaluación cualitativa:

### 1. Generación por Categoría
Muestra una matriz de 10x10 donde cada fila representa una categoría de Fashion-MNIST (camisetas, botas, bolsos, etc.) generada a partir de ruido aleatorio.

### 2. Reducción de Dimensionalidad (t-SNE)
Proyección del espacio latente de alta dimensión a 2D para observar cómo el modelo agrupa de forma natural las prendas similares (ej. calzado agrupado lejos de prendas superiores).

### 3. Latent Traversal
Exploración de dimensiones individuales del vector latente para identificar qué atributos físicos (como el largo de las mangas o la inclinación) controla cada variable.



### 4. Morphing entre Clases
Transición suave entre etiquetas. Por ejemplo, la transformación gradual de una **Zapatilla (clase 7)** a un **Botín (clase 9)**, demostrando la continuidad del espacio aprendido.

---

## 🛠️ Instalación y Uso

1. **Clonar repositorio:**
   ```bash
   git clone [https://github.com/Yushetf33/fashion-cvae.git](https://github.com/Yushetf33/fashion-cvae.git)
   cd fashion-cvae
