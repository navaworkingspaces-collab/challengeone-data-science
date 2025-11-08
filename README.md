# 📊 Challenge 1 - Análisis de Ventas

## 🎯 Objetivo
Proyecto de análisis de datos para extraer métricas clave de ventas de múltiples tiendas usando Python y bibliotecas de data science.

## 🛠️ Stack Tecnológico

### Lenguaje y Entorno
- **Python 3.8+**
- **Jupyter Notebook** - Entorno de desarrollo interactivo
- **Google Colab** - Alternativa cloud (opcional)

### Bibliotecas Principales
```python
import pandas as pd      # Manipulación y análisis de datos
import matplotlib.pyplot as plt  # Visualizaciones y gráficos
```

## 📦 Datos
Archivos CSV de 4 tiendas diferentes  
Estructura: Productos, precios, categorías, ubicaciones, calificaciones

---

## 🚀 Instalación y Configuración

### 1. Prerrequisitos
```bash
# Instalar Python (si no lo tienes)
# Descargar e instalar Anaconda o Miniconda (recomendado)
```

### 2. Instalar dependencias
```bash
pip install pandas matplotlib jupyter
```

### 3. Clonar/descargar los datos
```bash
# Los datos están en repositorios GitHub raw
# Se cargan directamente desde URLs en el notebook
```

---

## 📁 Estructura del Proyecto
```text
Challenge1/
│
├── Challenge1.ipynb          # Notebook principal con análisis completo
├── datos/                    # Datos descargados (opcional)
│   ├── tienda_1.csv
│   ├── tienda_2.csv
│   ├── tienda_3.csv
│   └── tienda_4.csv
└── README.md                 # Este archivo
```

---

## 🔧 Cómo Ejecutar

### 🖥️ Opción 1: Jupyter Notebook Local
```bash
# Navegar al directorio del proyecto
cd Challenge1

# Iniciar Jupyter
jupyter notebook

# Abrir Challenge1.ipynb y ejecutar celdas en orden
```

### ☁️ Opción 2: Google Colab
1. Subir el notebook a Google Colab  
2. Ejecutar las celdas secuencialmente  
3. Las URLs de datos ya están configuradas  

### 🐍 Opción 3: Script Python
```bash
# Convertir notebook a script (opcional)
jupyter nbconvert --to python Challenge1.ipynb

# Ejecutar como script
python Challenge1.py
```

---

## 📊 Análisis Implementados

### 1. Carga y Exploración de Datos
```python
# Carga desde URLs GitHub
tienda1 = pd.read_csv(url_tienda1)
tienda2 = pd.read_csv(url_tienda2)
# ... etc
```

### 2. Métricas Calculadas
- Ventas totales por tienda → `df['Precio'].sum()`  
- Productos por categoría → `groupby().size()`  
- Valoración promedio → `df['Calificación'].mean()`  
- Productos más/menos vendidos → `groupby().size().sort_values()`  
- Costo de envío promedio → `df['Costo de envío'].mean()`  

### 3. Visualizaciones
- Gráficos de dispersión con **Matplotlib**  
- Análisis de relación precio vs volumen  

---

## 💡 Personalización

### 🔄 Modificar Fuentes de Datos
```python
# Cambiar URLs por archivos locales
tienda1 = pd.read_csv('datos/tienda_1.csv')
```

### ➕ Agregar Nuevas Métricas
```python
# Ejemplo: Ventas mensuales
df['Fecha'] = pd.to_datetime(df['Fecha de Compra'])
ventas_mensuales = df.groupby(df['Fecha'].dt.month)['Precio'].sum()
```

### 🎨 Extender Visualizaciones
```python
# Agregar más tipos de gráficos
import seaborn as sns
sns.boxplot(x='Categoría', y='Precio', data=df)
```

---

## 🐛 Solución de Problemas Comunes

### ❌ Error: Módulo no encontrado
```bash
pip install --upgrade pandas matplotlib
```

### 🌐 Error: URLs no accesibles
- Descargar CSVs manualmente y usar rutas locales  
- Verificar conexión a internet  

### ⚙️ Error: Formato de datos
```python
# Limpiar formato de precios
df['Precio'] = df['Precio'].str.replace(',', '').astype(float)
```

---

## 📈 Próximos Pasos Sugeridos

### 🔧 Mejoras Técnicas
- Agregar análisis temporal con `pd.to_datetime()`  
- Implementar funciones modulares  
- Crear dashboard con **Streamlit**  
- Agregar tests unitarios  

### 📊 Análisis Adicionales
- Análisis de estacionalidad  
- Segmentación de clientes  
- Predicción de ventas con ML  
- Análisis de ubicaciones geográficas  

---

## 🤝 Contribuir
1. **Fork** del proyecto  
2. Crear rama para feature  
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```
3. Commit de cambios  
   ```bash
   git commit -am 'Agregar nueva funcionalidad'
   ```
4. Push a la rama  
   ```bash
   git push origin feature/nueva-funcionalidad
   ```
5. Crear Pull Request  

---

## 📝 Licencia
Este proyecto es educativo - libre para uso académico y aprendizaje.

¿Preguntas? Abre un *issue* o contacta al desarrollador 👨‍💻  

¡Happy coding! 🚀
