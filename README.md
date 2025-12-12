# 📘 Proyecto de Prueba – Entorno Virtual + Jupyter Notebook

Este proyecto incluye un entorno básico para trabajar con Python, Jupyter Notebook y librerías de análisis de datos como pandas, numpy y matplotlib.

A continuación se detallan los pasos para que cualquier persona pueda replicar el entorno en su computadora.

## 🚀 1. Clonar el repositorio

git clone <URL-del-repo>  
cd prueba1

## 🐍 2. Crear el entorno virtual

### OPCION 1: Windows – PowerShell

```bash
python -m venv venv
```

### Activar el entorno:

```bash
venv\Scripts\Activate
```

### OPCION 2: Git Bash

```bash
python -m venv venv
source venv/Scripts/activate
```

### Una vez activado, deberías ver algo así:

```bash
(venv) user@PC:~/proyecto
```

## 📦 3. Instalar dependencias desde requirements.txt

### Con el entorno virtual activado, ejecutar:

```bash
python -m pip install -r requirements.txt
```

Esto instalará exactamente las mismas librerías usadas en el proyecto.

## 📓 4. Ejecutar Jupyter Notebook

Una vez instaladas las dependencias ejecutar:

```bash
jupyter notebook
```

Esto abrirá una ventana en tu navegador con la interfaz de Jupyter.  
Si no se abre automáticamente, podés entrar manualmente a:

```
http://localhost:8888
```

## 📒 5. Abrir el notebook del proyecto

### Dentro de Jupyter Notebook:

Navegá hasta el archivo

```
prueba.ipynb
```

Hacé clic para abrirlo.

Ejecutá las celdas con Shift + Enter.

# CONEXION A LA BASES DE DATOS POSTGRESQL

## 2️⃣ Instalar el conector de Postgres en tu venv

En tu proyecto (con el venv activado):

```bash
python -m pip install psycopg2-binary sqlalchemy
```

## ✅ 1. Crear tu archivo .env

En la raíz de tu proyecto (donde está requirements.txt), creá un archivo:

```bash
.env
```

Dentro poné tus variables (sin comillas):

```bash
DB_USER=postgres
DB_PASSWORD=tu_password_real
DB_HOST=localhost
DB_PORT=5432
DB_NAME=northwind
```

## ✅ 2. Instalar la librería para leer .env

Dentro de tu entorno virtual:

```bash
pip install python-dotenv
```

Esto permite cargar las variables en Python usando load_dotenv().

## ✅ 3. Usar el .env dentro de tu archivo de conexión

En tu Jupyter Notebook o archivo .py:  
archivo: conexion_bd.ipynb

```bash
import os
from dotenv import load_dotenv
from sqlalchemy import create_engine
import pandas as pd

# Cargar variables del archivo .env
load_dotenv()

usuario = os.getenv("DB_USER")
password = os.getenv("DB_PASSWORD")
host = os.getenv("DB_HOST")
puerto = os.getenv("DB_PORT")
base = os.getenv("DB_NAME")

# Crear el engine
url = f"postgresql+psycopg2://{usuario}:{password}@{host}:{puerto}/{base}"
engine = create_engine(url)

# Probar conexión
df = pd.read_sql("SELECT * FROM public.customers LIMIT 5;", engine)
df

```
