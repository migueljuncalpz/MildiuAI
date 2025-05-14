# Detección de Enfermedades en Plantaciones de Albariño

## 📦 Descripción del Proyecto
Este proyecto tiene como objetivo desarrollar un modelo de Machine Learning para la detección de enfermedades en plantaciones de Albariño mediante la clasificación de imágenes. Se utilizarán técnicas de Transfer Learning y Fine-Tuning para entrenar un modelo capaz de identificar las siguientes patologías:

- Mildiu (Plasmopara viticola)
- Oídio (Uncinula necator)
- Botritis (Botrytis cinerea)
- Black Rot (Guignardia bidwellii)
- Hojas Sanas

## ✅ Estructura del Proyecto
```
/MildiuAI/
│
├── data/
│   ├── raw/                # Imágenes sin procesar, agrupadas por enfermedad
│   ├── processed/          # Imágenes preprocesadas (redimensionadas, normalizadas)
│   ├── augmented/          # Imágenes aumentadas
│   └── metadata.csv        # Archivo CSV con etiquetas y paths
│
├── notebooks/
│   ├── 01-data-exploration.ipynb
│   ├── 02-preprocessing.ipynb
│   ├── 03-training.ipynb
│   └── 04-evaluation.ipynb
│
├── src/
│   ├── data/
│   │   ├── data_loader.py   # Carga y preprocesamiento
│   │   └── augment.py       # Aumentación de datos
│   │
│   ├── models/
│   │   ├── cnn_model.py     # Modelo CNN
│   │   └── train.py         # Script de entrenamiento
│   │
│   └── utils/
│       └── metrics.py       # Cálculo de métricas
│
├── config/
│   └── config.yaml          # Parámetros generales
│
├── logs/
│   └── training.log         # Logs de entrenamiento
│
├── requirements.txt         # Dependencias del proyecto
├── Dockerfile               # Configuración de Docker
├── README.md                # Documentación del proyecto
└── .gitignore               # Archivos a ignorar
```

## 🚀 Requisitos
- Python 3.10+
- TensorFlow 2.x / PyTorch
- OpenCV
- Albumentations
- Matplotlib
- Pandas
- NumPy

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

## 📂 Preparación del Dataset
1. Crear las carpetas necesarias:

```bash
mkdir -p data/raw data/processed data/augmented
```

2. Añadir imágenes etiquetadas en la carpeta `data/raw` siguiendo la estructura de carpetas por clase.

3. Generar el archivo `metadata.csv` con el formato:

```
path,label
/data/raw/mildew/img1.jpg,mildew
/data/raw/oidium/img2.jpg,oidium
```

## 🛠️ Ejecución
- Preprocesamiento de datos:

```bash
python src/data/data_loader.py
```

- Entrenamiento del modelo:

```bash
python src/models/train.py
```

- Evaluación del modelo:

```bash
python src/utils/metrics.py
```

## 🧠 Modelos Utilizados
- CNN básica con capas convolucionales y fully connected.
- Transfer Learning utilizando ResNet50.

## 📝 Licencia
Este proyecto está bajo la Licencia MIT.
