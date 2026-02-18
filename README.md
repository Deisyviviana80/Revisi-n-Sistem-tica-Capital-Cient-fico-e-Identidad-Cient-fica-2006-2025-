# 📚 Revisión Sistemática de Literatura
## Capital Científico e Identidad Científica (2006–2025)

**Autora:** Deisy Viviana Hurtado Vega  
**Fecha:** Febrero 2026  
**Contexto:** Prueba técnica para convocatoria de Investigadora — Instituto UNNO, Parque Científico de Innovación Social, UNIMINUTO

---

## 🎯 Descripción del proyecto

Este proyecto implementa una **revisión sistemática de literatura** sobre Capital Científico (*Scientific Capital*) e Identidad Científica (*Scientific Identity*), abarcando publicaciones entre 2006 y 2025. El análisis combina técnicas bibliométricas con síntesis crítica cualitativa para mapear tendencias globales, identificar vacíos temáticos y detectar poblaciones subrepresentadas en la literatura académica.

La pregunta de investigación se formuló con el enfoque **PICo** y el análisis revela una concentración anglosajona del campo, una aceleración notable de publicaciones desde 2021, y una ausencia significativa de producción latinoamericana —especialmente colombiana— que representa una oportunidad estratégica para instituciones de innovación social.

---

## 📁 Estructura del repositorio

```
📦 repositorio
 ┣ 📓 analisis_openalex_completo.ipynb     # Notebook principal: limpieza, EDA y visualizaciones
 ┣ 📓 VISUALIZACIONES_COMPLEMENTO.ipynb   # Notebook complementario: distribución geográfica, 
 ┃                                         # niveles educativos y poblaciones subrepresentadas
 ┣ 📄 corpus_limpio.csv                    # Dataset depurado (115 artículos, 29 variables)
 ┣ 📄 corpus.csv                           # Dataset original exportado desde OpenAlex (118 registros)
 ┗ 📄 README.md                            # Este archivo
```

---

## 🔬 Metodología

### Fuente de datos
Los datos fueron recuperados mediante la **API de OpenAlex**, una infraestructura científica abierta que indexa más de 250 millones de trabajos académicos. Se eligió por su cobertura multilingüe, acceso libre y riqueza de metadatos (FWCI, afiliaciones, estado de acceso abierto).

### Ecuación de búsqueda
```
(("scientific capital" OR "capital científico") OR 
 ("scientific identity" OR "identidad científica")) 
AND ("education" OR "educación")
```
Filtros: artículos · 2006–2025 · inglés y español

### Corpus final
- **118 registros** recuperados → **3 duplicados eliminados** → **115 artículos** analizados
- Período: 2007–2025
- Formato: CSV con 29 variables (título, autores, año, fuente, resumen, citas, DOI, FWCI, acceso abierto, afiliaciones, tópicos)

---

## 🛠️ Herramientas y tecnologías

| Herramienta | Uso |
|---|---|
| `Python 3` | Lenguaje principal |
| `pandas` | Manipulación y limpieza de datos |
| `numpy` | Operaciones numéricas |
| `matplotlib` | Visualizaciones |
| `seaborn` | Visualizaciones estadísticas |
| `Jupyter Notebook` | Entorno de análisis reproducible |
| `OpenAlex API` | Fuente de datos bibliográficos |

---

## 📊 Contenido de los notebooks

### `analisis_openalex_completo.ipynb`
Notebook principal con el flujo completo de análisis:

1. **Carga de datos** — Inspección estructural del dataset (118 × 29)
2. **Limpieza y preparación**
   - Análisis de valores nulos por columna
   - Detección y eliminación de duplicados (n=3)
   - Corrección de tipos de datos
   - Imputación: columnas con >80% nulos eliminadas; texto → "No especificado"; numéricos → mediana
3. **Análisis exploratorio (EDA)**
   - Estadísticas descriptivas generales
   - Distribución temporal de publicaciones
   - Análisis de citaciones e impacto (FWCI promedio: 3.23)
   - Análisis de acceso abierto (diamond, gold, green, bronze, closed)
   - Top revistas y fuentes de publicación
   - Análisis de tópicos de investigación
4. **Visualizaciones** (5 gráficos interpretados)
   - Evolución temporal de publicaciones por año
   - Distribución de citaciones (histograma + boxplot)
   - Estado de acceso abierto
   - Relación año-citaciones (doble eje Y)
   - Top 12 tópicos de investigación
5. **Exportación** del corpus depurado como `corpus_limpio.csv`

### `VISUALIZACIONES_COMPLEMENTO.ipynb`
Notebook de verificación y análisis complementario que profundiza en los hallazgos críticos del informe:

- **Gráfico 1 — Distribución geográfica:** Concentración por país de afiliación y ausencia de Colombia (1 artículo: *"Democratizing STEM"*, 2025)
- **Gráfico 2 — Niveles educativos:** Vacío en primera infancia (solo 2 artículos mencionan *early childhood* o *preschool*)
- **Gráfico 3 — Poblaciones subrepresentadas:** Frecuencia de grupos como mujeres/género, minorías étnicas, docentes en formación, primera infancia y comunidades indígenas en los abstracts

---

## 📈 Hallazgos principales

| Hallazgo | Dato |
|---|---|
| Total artículos analizados | 115 |
| Período cubierto | 2007–2025 |
| FWCI promedio del corpus | 3.23 |
| País dominante | EE.UU. (66 afiliaciones) |
| Aceleración reciente | 52 artículos en 2021–2025 (45.2% del total) |
| Acceso abierto | 64.4% del corpus |
| Colombia en el corpus | 1 artículo (0.9%) |
| Artículos sobre primera infancia | 2 de 115 (1.7%) |

---

## ⚠️ Nota de precisión metodológica

Durante la revisión final se identificaron pequeñas discrepancias entre el informe narrativo y el CSV definitivo, originadas porque algunos cálculos se realizaron sobre la versión intermedia del dataset (118 registros, antes de eliminar los 3 duplicados). Los valores correctos corresponden al archivo `corpus_limpio.csv` (115 registros). Esta discrepancia fue documentada y reportada de forma transparente como parte del compromiso con el rigor y la reproducibilidad del proceso.

---

## 📝 Cómo reproducir el análisis

```bash
# 1. Clonar el repositorio
git clone https://github.com/Deisyviviana80/Revisi-n-Sistem-tica-Capital-Cient-fico-e-Identidad-Cient-fica-2006-2025-/tree/main
# 2. Instalar dependencias
pip install pandas numpy matplotlib seaborn jupyter

# 3. Ejecutar en orden
jupyter notebook analisis_openalex_completo.ipynb
jupyter notebook VISUALIZACIONES_COMPLEMENTO.ipynb
```

> ⚠️ Ejecutar primero `analisis_openalex_completo.ipynb` ya que genera el archivo `corpus_limpio.csv` que usa el segundo notebook.

---

## 📬 Contacto

**Deisy Viviana Hurtado Vega**  
[LinkedIn](https://www.linkedin.com/in/deisyhurtado-analistadedatos/)
