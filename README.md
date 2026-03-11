# telecomx1
primera parte reto telecom x
# Telecom X – Análisis de Evasión de Clientes (Churn)

## Propósito del Proyecto

Este proyecto tiene como objetivo analizar la **evasión de clientes (Churn)** en la empresa ficticia **Telecom X**.
El análisis busca identificar patrones y factores que influyen en la cancelación del servicio por parte de los clientes.

El trabajo se desarrolló aplicando el proceso **ETL (Extract, Transform, Load)** utilizando Python, con el fin de preparar los datos y generar insights que ayuden al equipo de ciencia de datos a desarrollar modelos predictivos de abandono de clientes.

---

#  Objetivos del Análisis

* Extraer datos desde un archivo **JSON** con información de clientes.
* Limpiar y transformar los datos para su análisis.
* Explorar patrones asociados al **Churn**.
* Analizar variables como:

  * cargos mensuales
  * cargos totales
  * tipo de servicio
  * características del cliente
* Generar visualizaciones que permitan comprender mejor el comportamiento de los clientes.

---

# Tecnologías Utilizadas

* **Python**
* **Pandas**
* **Matplotlib**
* **Seaborn**
* **Google Colab**
* **GitHub**

---

# Proceso de Análisis

## Extracción de datos (Extract)

Los datos fueron cargados desde un archivo JSON utilizando la librería **Pandas**.

```python
df = pd.read_json('TelecomX_Data.json')
```

El dataset contiene información sobre:

* características del cliente
* servicios contratados
* tipo de contrato
* método de pago
* cargos mensuales y totales
* estado de churn

---

## Transformación de datos (Transform)

El archivo JSON contenía **estructuras anidadas**, por lo que fue necesario aplanar estas columnas para facilitar su análisis.

Se transformaron las siguientes columnas:

* `customer`
* `phone`
* `internet`
* `account`

Estas columnas fueron convertidas en múltiples variables individuales utilizando `pd.json_normalize()`.

También se realizaron las siguientes tareas de limpieza:

* Conversión de **account_Charges.Total** a valor numérico
* Reemplazo de valores inválidos por `NaN`
* Eliminación de registros con valore
  Carga y Exploración de Datos (Load + EDA)

Una vez limpios los datos se realizó un análisis exploratorio (EDA) para entender el comportamiento de los clientes.

Se analizaron:

distribución de clientes con y sin churn

relación entre churn y cargos mensuales

relación entre churn y cargos totales

Ejemplo de visualización utilizada:

sns.countplot(x='Churn', data=df)

También se utilizaron gráficos boxplot para observar la relación entre costos y cancelación del servicio.

Principales Insights

Del análisis exploratorio se identificaron algunos patrones relevantes:

Aproximadamente 26.5% de los clientes abandonan el servicio.

Los clientes que abandonan presentan cargos mensuales más altos en promedio.

Sin embargo, los clientes que permanecen en la empresa tienen mayores cargos totales, lo que sugiere que llevan más tiempo como clientes.

Esto puede indicar que el churn ocurre principalmente en clientes más nuevos.

Estos hallazgos pueden ayudar al equipo de ciencia de datos a desarrollar modelos predictivos de churn y estrategias de retención.

Estructura del Proyecto
telecomX-churn-analysis
│
├── TelecomX.ipynb
├── TelecomX_Data.json
└── README.md
Cómo Ejecutar el Proyecto

Clonar el repositorio:

git clone https://github.com/tu-usuario/telecomX-churn-analysis.git

Abrir el notebook en Google Colab o Jupyter Notebook.

 Ejecutar las celdas para reproducir el proceso ETL y el análisis exploratorio.

Resultados del Proyecto

El análisis permitió comprender mejor el comportamiento de los clientes y detectar posibles factores asociados a la evasión.

Este trabajo sirve como base para:

futuros modelos de machine learning

estrategias de retención de clientes

mejoras en los servicios ofrecidos por Telecom X.

 Autora

Proyecto realizado por Ornella Mazzoni como parte del programa Oracle Next Education – Alura Latam.
