# 📡 ConnectaTel: Análisis del comportamiento de clientes de telecomunicaciones
# 📊 Proyecto de análisis exploratorio de datos (EDA) sobre el perfil y el uso de servicios de los clientes.
## 🎯 1. Objetivo del proyecto
El objetivo de este proyecto es explorar el comportamiento de uso de los clientes de ConnectaTel a partir de sus datos de perfil y consumo de servicios. El análisis busca preparar los datos, identificar problemas de calidad, describir los patrones de uso y segmentar a los usuarios según su actividad y edad.
El trabajo se desarrolla en un notebook de Python y está orientado al análisis exploratorio de datos (EDA), con el fin de generar información que pueda apoyar la comprensión de los clientes y la formulación de hipótesis comerciales.

## 🗂️ 2. Datasets utilizados
El notebook carga tres archivos CSV:
📄 Archivo	📝 Contenido general	🔍 Campos y uso en el análisis
plans.csv	Información de los planes disponibles.	Se carga y explora como parte de la revisión inicial de las fuentes.
users_latam.csv	Información de los usuarios.	Incluye variables como user_id, age, city, plan y reg_date. Se utiliza para analizar el perfil de los clientes.
usage.csv	Registros de actividad de los usuarios.	Incluye campos como id, user_id, type, date, duration y length, que permiten resumir llamadas y mensajes.

Los archivos se esperan inicialmente en la ruta /datasets/, tal como aparece en el notebook:
- /datasets/plans.csv
- /datasets/users_latam.csv
- /datasets/usage.csv
⚠️ Importante: los CSV deben estar disponibles en el entorno de ejecución. Si no se distribuyen junto con el repositorio, cada persona deberá obtenerlos por el medio autorizado y ajustar las rutas de carga si es necesario.

## 🔎 3. Etapas del análisis
El notebook está organizado en las siguientes etapas:
1. Carga y exploración inicial: importación de Pandas, NumPy, Matplotlib y Seaborn; lectura de los tres archivos y revisión de su estructura, dimensiones y tipos de datos.
2. Evaluación de calidad de datos: revisión de valores nulos, duplicados, valores atípicos y valores sentinela, como -999 en age y ? en city.
3. Revisión y estandarización de fechas: conversión de reg_date y date a formato de fecha, e inspección de registros con fechas faltantes o posteriores al periodo considerado por el análisis.
4. Limpieza básica: sustitución del valor sentinela -999 de la edad por la mediana, conversión de ? a un valor nulo en la ciudad y tratamiento de fechas futuras en reg_date. También se examina la ausencia de duration y length según el tipo de registro.
5. Resumen de uso por usuario: cálculo de la cantidad de mensajes, cantidad de llamadas y suma de la duración de llamadas; posteriormente, estas métricas se combinan con el perfil de cada usuario.
6. Análisis estadístico y visualización: revisión de estadísticas descriptivas y distribución de variables como edad, mensajes, llamadas y minutos de llamadas, con gráficos de distribución y diagramas de caja.
7. Detección de valores atípicos: uso de diagramas de caja y del método del rango intercuartílico (IQR) para identificar valores extremos y documentar decisiones sobre su tratamiento.
8. Segmentación de clientes: clasificación de usuarios por nivel de uso (bajo, medio y alto) y por grupos de edad, además de visualizaciones de la distribución de los segmentos.
9. Conclusiones ejecutivas: síntesis de los problemas de calidad detectados, los patrones de uso y las posibles implicaciones para el negocio.

## 🧰 4. Herramientas y librerías
- 🐍 Python
- 🧹 Pandas: carga, limpieza, transformación y agregación de datos.
- 🔢 NumPy: operaciones numéricas.
- 📈 Matplotlib: elaboración de gráficos.
- 🎨 Seaborn: visualización estadística.
- 📓 Jupyter Notebook / Google Colab: ejecución del análisis.
- 
## 🚀 5. Cómo ejecutar el notebook en Google Colab
1. Descarga o guarda el archivo S7 Version-Estudiante-Project-ConnectaTel.ipynb en tu equipo.
2. Abre Google Colab.
3. Selecciona Archivo → Subir notebook y elige el archivo .ipynb. También puedes abrirlo desde Google Drive si ya está guardado allí.
4. Asegúrate de que los tres archivos CSV estén disponibles en el entorno de Colab.
5. Si los archivos están en Google Drive, monta Drive con:
   from google.colab import drive
   drive.mount('/content/drive')
6. Ajusta las rutas de pd.read_csv() para que apunten a la ubicación real de los archivos. Por ejemplo:
   plans = pd.read_csv('/content/drive/MyDrive/ruta-a-los-datos/plans.csv')
   users = pd.read_csv('/content/drive/MyDrive/ruta-a-los-datos/users_latam.csv')
   usage = pd.read_csv('/content/drive/MyDrive/ruta-a-los-datos/usage.csv')
   Sustituye ruta-a-los-datos por la carpeta donde guardaste los CSV. Si utilizas otra ubicación, actualiza las rutas de acuerdo con ella.
7. Ejecuta las celdas en orden desde Entorno de ejecución → Ejecutar todas. Si una celda produce un error, revisa primero que las dependencias estén instaladas y que las rutas y nombres de los archivos sean correctos.
Las librerías utilizadas pueden instalarse, si hiciera falta, con:
!pip install pandas numpy matplotlib seaborn

## 🔁 6. Guía breve para reproducir el análisis
Para reproducir los resultados:
1. Utiliza las versiones disponibles de los tres archivos de datos y conserva sus nombres o actualiza las rutas en el notebook.
2. Ejecuta todas las celdas en orden, desde la carga de datos hasta las conclusiones.
3. Revisa las salidas de las etapas de calidad de datos para verificar los valores nulos, sentinelas, fechas y duplicados.
4. Comprueba los resúmenes agregados por user_id y las columnas de segmentación creadas.
5. Revisa los gráficos y las conclusiones generadas por el notebook.
6. Si modificas reglas de limpieza o segmentación, vuelve a ejecutar las celdas posteriores para que las tablas y visualizaciones reflejen los cambios.
🔁 Nota de reproducibilidad: el notebook utiliza rutas de entrada bajo /datasets/. Google Colab no dispone automáticamente de esa carpeta, por lo que es necesario cargar los CSV y actualizar las rutas. Los resultados pueden variar si cambian los datos de origen o las decisiones de limpieza.
