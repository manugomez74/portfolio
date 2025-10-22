# 📊 Proyecto 1: Análisis de Ventas y Rentabilidad

## 🎯 Objetivo
Generar y limpiar un dataset simulado de ventas con el propósito de practicar un flujo completo de análisis de datos: desde la generación y validación de datos hasta su preparación para visualización o modelado.

---

## 🧱 Estructura del proyecto

project_1_analysis/
│
├── data/

│ ├── raw/ → Datos originales o generados
│ └── processed/ → Datos limpios y listos para análisis
│
├── notebooks/
│ └── 01_generate_dataset.ipynb
│
├── dashboard/ → (pendiente) visualización final en Power BI o Python
└── README.md


---

## 🧮 Proceso de trabajo

1. **Generación de datos sintéticos** con Python y `pandas`.  
   Se simularon 2000 registros de ventas con columnas como:
   - Fecha, cliente, producto, región, canal, precios y beneficio.

2. **Exploración inicial y limpieza básica**
   - Se detectaron y eliminaron valores atípicos en el beneficio.
   - Se ajustaron tipos de datos (ej. `fecha` → datetime, `categoría` → string).
   - No se encontraron valores nulos.

3. **Corrección de incoherencias**
   - Se detectaron 98 registros con `ingreso` y 641 con `beneficio` incorrectos.  
   - Se recalcularon los campos derivados:
     ```python
     ingreso = precio_unitario * cantidad
     beneficio = (precio_unitario - coste_unitario) * cantidad
     ```
   - Resultado final: coherencia total (0 registros inconsistentes).

4. **Versionado de dataset**
   - `ventas_limpias.csv` → versión inicial.  
   - `ventas_limpias_v2.csv` → versión validada y corregida.

---

## 📦 Archivos resultantes
- `data/processed/ventas_limpias_v2.csv`: Dataset final limpio y coherente.
- `notebooks/01_generate_dataset.ipynb`: Notebook con todo el proceso reproducible.

---

## 🔜 Próximos pasos
- Crear notebook `02_exploratory_analysis.ipynb` para análisis exploratorio (EDA).
- Visualizar relaciones entre variables clave: región, canal, rentabilidad, etc.
- Desarrollar dashboard interactivo con Power BI o Plotly.
