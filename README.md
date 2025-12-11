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
