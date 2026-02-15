# Instacart Market Basket Analysis

> Análisis exploratorio de hábitos de compra en plataforma de entrega de comestibles usando dataset real de Instacart

![Python](https://img.shields.io/badge/Python-3.9-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.x-green)
![NumPy](https://img.shields.io/badge/NumPy-1.x-013243)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange)
![Status](https://img.shields.io/badge/Status-Reviewed%20&%20Approved-success)

##  Descripción

Análisis exploratorio de datos (EDA) del comportamiento de compra de clientes de **Instacart**, una plataforma de entrega de comestibles similar a Uber Eats. 

Este proyecto utiliza un **dataset real** publicado por Instacart en 2017 para una competición de Kaggle, modificado para incluir desafíos adicionales de limpieza de datos (valores ausentes, duplicados).

### Contexto de negocio
Instacart necesita entender:
- Patrones de compra de clientes
- Productos más reordenados
- Horarios pico de pedidos
- Comportamiento por día de la semana
- Relaciones entre departamentos y productos

##  Objetivos del proyecto

1. **Limpieza de datos** - Manejar valores ausentes y duplicados en 5 tablas relacionadas
2. **Preprocesamiento** - Fusionar tablas y preparar datos para análisis
3. **Análisis exploratorio** - Responder preguntas clave sobre comportamiento de clientes
4. **Visualización** - Comunicar hallazgos mediante gráficos claros y etiquetados
5. **Informe ejecutivo** - Documentar insights accionables

## 📁 Estructura de datos

El dataset consta de **5 tablas relacionadas:**

### 1. `instacart_orders.csv` - Pedidos
| Columna | Descripción |
|---------|-------------|
| `order_id` | ID único del pedido |
| `user_id` | ID único del cliente |
| `order_number` | Número de pedido del cliente |
| `order_dow` | Día de la semana (0 = Domingo) |
| `order_hour_of_day` | Hora del pedido (0-23) |
| `days_since_prior_order` | Días desde último pedido |

### 2. `products.csv` - Productos
| Columna | Descripción |
|---------|-------------|
| `product_id` | ID único del producto |
| `product_name` | Nombre del producto |
| `aisle_id` | ID del pasillo |
| `department_id` | ID del departamento |

### 3. `order_products.csv` - Items por pedido
| Columna | Descripción |
|---------|-------------|
| `order_id` | ID del pedido |
| `product_id` | ID del producto |
| `add_to_cart_order` | Orden de adición al carrito |
| `reordered` | 0 = primera vez, 1 = reorden |

### 4. `aisles.csv` - Pasillos
| Columna | Descripción |
|---------|-------------|
| `aisle_id` | ID del pasillo |
| `aisle` | Nombre del pasillo |

### 5. `departments.csv` - Departamentos
| Columna | Descripción |
|---------|-------------|
| `department_id` | ID del departamento |
| `department` | Nombre del departamento |

##  Tecnologías utilizadas

- **Python 3.x** - Lenguaje de programación
- **Pandas** - Manipulación de DataFrames y fusión de tablas
- **NumPy** - Operaciones numéricas y cálculos estadísticos
- **Matplotlib** - Visualización de datos
- **Jupyter Notebook** - Ambiente de desarrollo y documentación

##  Proceso de análisis

### Etapa 1: Preprocesamiento
```python
# Carga de múltiples tablas
orders = pd.read_csv('instacart_orders.csv')
products = pd.read_csv('products.csv')
order_products = pd.read_csv('order_products.csv')
aisles = pd.read_csv('aisles.csv')
departments = pd.read_csv('departments.csv')

# Limpieza y validación
- Detección de duplicados
- Manejo de valores ausentes
- Validación de tipos de datos
```

### Etapa 2: Fusión de datos
```python
# Relacionar tablas mediante merge
df_merged = order_products.merge(products, on='product_id')
                          .merge(orders, on='order_id')
                          .merge(aisles, on='aisle_id')
                          .merge(departments, on='department_id')
```

### Etapa 3: Análisis exploratorio
- Distribución de pedidos por hora del día
- Patrones de compra por día de la semana
- Productos más reordenados
- Departamentos más populares
- Análisis de frecuencia de recompra

### Etapa 4: Visualización
- Gráficos de barras para ranking de productos
- Histogramas de distribución temporal
- Análisis de tendencias de reorden

##  Preguntas de negocio respondidas

1. **¿Cuándo hacen pedidos los clientes?**
   - Análisis por hora y día de la semana
   
2. **¿Cuánto tiempo esperan antes de reordenar?**
   - Distribución de `days_since_prior_order`
   
3. **¿Qué productos se reordenan con más frecuencia?**
   - Top productos por tasa de reorden
   
4. **¿Cuáles son los departamentos más populares?**
   - Ranking de departamentos por volumen

5. **¿Cuántos productos compran por pedido?**
   - Distribución de tamaño de carrito

##  Aprendizajes clave

- **Manejo de datasets relacionales** - Fusión de múltiples tablas (merge/join)
- **Limpieza de datos a escala** - Procesamiento de datasets grandes
- **NumPy para cálculos** - Operaciones estadísticas eficientes
- **Visualización efectiva** - Gráficos claros con títulos, ejes y leyendas
- **Ciclo de revisión profesional** - Iterar basado en feedback
- **Documentación técnica** - Explicar hallazgos en Markdown




##  Habilidades demostradas

- **Pandas avanzado** - merge(), groupby(), pivot_table()
- **NumPy** - Cálculos estadísticos y agregaciones
- **Data cleaning** - Manejo de inconsistencias en datos reales
- **EDA** - Exploración sistemática de datasets complejos
- **Storytelling con datos** - Comunicar insights con visualizaciones
- **Iteración profesional** - Incorporar feedback de revisores

##  Logros del proyecto

-  **Dataset real de industria** (Instacart/Kaggle)
-  **Aprobado tras ciclos de revisión** profesional
-  **Múltiples tablas relacionadas** manejadas correctamente
-  **Visualizaciones claras** y bien etiquetadas
-  **Insights accionables** documentados

##  Notas

Cuarto proyecto del bootcamp de Data Analysis. Primer proyecto con **múltiples tablas relacionadas**, **NumPy**, y **visualizaciones profesionales**. Sometido a **ciclos de revisión** por equipo técnico con feedback implementado.

**Fuente de datos:** [Instacart Market Basket Analysis - Kaggle](https://www.kaggle.com/c/instacart-market-basket-analysis)

---

**Proyecto:** Bootcamp Data Analysis - Análisis Exploratorio de Datos  
**Autor:** Marcos - [@NachtD69](https://github.com/NachtD69)  
**Fecha:** 2026  
**Dataset:** Instacart (Kaggle Competition 2017)  
**Status:**  Revisado y Aprobado
