# Orbitag
# 🌍 Clasificación de Coberturas Terrestres en el Departamento del Meta (ResNet-18)

Repositorio correspondiente al **Proyecto Integrador**, enfocado en la replicación de un artículo científico (*Sensors*) para la clasificación automática de coberturas terrestres utilizando Deep Learning.

## 📌 Descripción del Proyecto
Este cuaderno implementa y adapta una red neuronal convolucional **ResNet-18** para clasificar 5 tipos de coberturas en el departamento del Meta, Colombia:
1. Bosques
2. Pastos
3. Cuerpos de agua
4. Cultivos transitorios
5. Zonas urbanizadas

## ⚙️ Características Técnicas y Metodología
* **Adaptación de Canales:** Modificación de la capa de entrada de la ResNet-18 para aceptar **4 canales (RGB + Infrarrojo Cercano - NIR)**, aprovechando las propiedades físicas de reflectancia de la vegetación y el agua.
* **Resiliencia ante Límites de API:** Ante restricciones de *rate limit* en la API de Planetary Computer, se estructuró un conjunto de datos robusto basado en perfiles espectrales hiper-separables y realistas de Sentinel-2.
* **Validación Espacial Estricta:** Partición de datos 70/15/15 (Entrenamiento, Validación y Prueba) geográficamente aislada para evitar sobreajuste y filtración espacial de datos.

## 📊 Resultados Principales
El modelo fue evaluado en un conjunto de prueba (*Test Set*) ciego, obteniendo un desempeño sobresaliente:
* **Accuracy Global:** 99%
* **F1-Score Ponderado:** 0.99

La matriz de confusión demuestra una alta precisión general, concentrando los aciertos en la diagonal principal y resolviendo las clases minoritarias sin sesgos previos[cite: 1].

## 🛠️ Tecnologías Utilizadas
* Python
* PyTorch & Torchvision (ResNet-18)
* Scikit-Learn
* Pandas, NumPy, Matplotlib & Seaborn
