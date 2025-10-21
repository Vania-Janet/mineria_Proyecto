# Predicción de Quiebra Bancaria - Análisis de Supervivencia

## Descripción del Proyecto

Este proyecto implementa un modelo de minería de datos para análisis de supervivencia y predicción de quiebras bancarias en Estados Unidos. El objetivo es desarrollar un clasificador binario o sistema de puntuación de fragilidad para identificar instituciones financieras en riesgo de insolvencia.

## Autores

- Vania Janet Raya Rios
- Imanol Mendoza Saenz de Buruaga
- Mauricio Acosta

## Fuentes de Datos

### FDIC (Federal Deposit Insurance Corporation)
- Lista de bancos quebrados con datos históricos de cierre
- Fuente: https://www.fdic.gov/resources/resolutions/bank-failures/failed-bank-list/

### FFIEC (Federal Financial Institutions Examination Council)
- Reportes de Call Reports con estados financieros detallados
- Datos financieros trimestrales de todas las instituciones aseguradas por FDIC
- Fuente: FFIEC Central Data Repository (CDR)

## Metodología

### Integración de Datos
Ambos conjuntos de datos se unen mediante el CERT (Número de Certificado) como clave primaria, creando un dataset unificado con:
- Indicadores de quiebra bancaria (variable objetivo)
- Métricas financieras exhaustivas
- Datos históricos de desempeño

### Ingeniería de Características
Ratios financieros clave calculados:
- **Ratios de Capital**: Equity a Activos, Deuda a Equity
- **Ratios de Liquidez**: Ratio Préstamos a Depósitos
- **Calidad de Activos**: Ratio Reservas a Préstamos
- **Concentración de Depósitos**: Ratio Depósitos a Activos

### Enfoque Analítico
1. Análisis Exploratorio de Datos (EDA)
2. Selección e ingeniería de características
3. Balanceo de clases (SMOTE, undersampling)
4. Entrenamiento y validación de modelos
5. Análisis de supervivencia (Kaplan-Meier, Cox Proportional Hazards)

## Estructura del Proyecto

```
mineria_Proyecto/
├── exploratory_analysis.ipynb    # Notebook principal de EDA
├── requirements.txt               # Dependencias de Python
├── download-data.csv              # Datos de bancos quebrados FDIC
├── FFIEC CDR Call Bulk All Schedules 03312001/  # Datos financieros FFIEC
└── README.md
```

## Instalación

```bash
# Crear entorno virtual
python -m venv .venv
source .venv/bin/activate  # En Windows: .venv\Scripts\activate

# Instalar dependencias
pip install -r requirements.txt
```

## Uso

Ejecutar el notebook de Jupyter para análisis exploratorio:

```bash
jupyter notebook exploratory_analysis.ipynb
```

El notebook incluye:
- Carga y preprocesamiento de datos
- Análisis temporal y geográfico de quiebras bancarias
- Cálculo de ratios financieros
- Análisis comparativo (bancos quebrados vs. solventes)
- Análisis de correlación
- Evaluación de calidad de datos
- Preparación de dataset para modelado

## Hallazgos Clave

- Las quiebras bancarias históricas muestran patrones temporales alineados con crisis económicas
- Concentración geográfica de quiebras en estados específicos
- Diferencias significativas en ratios financieros entre instituciones quebradas y solventes
- Los ratios de capital, liquidez y calidad de activos son discriminadores fuertes

## Trabajo Futuro

1. Ingeniería avanzada de características (tendencias temporales, interacciones)
2. Desarrollo de modelos (Regresión Logística, Random Forest, XGBoost, Redes Neuronales)
3. Implementación de análisis de supervivencia
4. Transfer learning para aplicación al sector bancario mexicano
5. Dashboard de monitoreo en tiempo real

## Requisitos

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- lifelines (for survival analysis)
- xgboost / lightgbm
- imbalanced-learn

## License

This project is developed for academic purposes.

## Contact

For questions or collaborations, please contact the project authors through the repository.
