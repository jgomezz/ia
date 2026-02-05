# LABORATORIO: Reporte Visual Completo desde CSV

## Datos

- Datos: Delitos denunciados en Perú (Enero-Noviembre 2025)
- Archivo: <a href="BD-delitos-denunciados-2025-11.csv" >[MPFN] Delitos Denunciados 2025</a>
- Diccionario: <a href="diccionario de datos - Delitos Penales_0.pdf" >Diccionario de datos - Delitos Denunciados</a>

Referencia https://www.datosabiertos.gob.pe/dataset/mpfn-delitos-denunciados

---


## EJERCICIO 1: Crear y configurar el Proyecto

- Paso 1: Reporte Visual Delitos - Generación Automática


Abre ChatGPT

Y en la Barra lateral seleccionar → "Projects" → "New Project"

Colocar este nombre : "Análisis Seguridad Ciudadana - Lima 2025"

<img src="images/chatgpt_create_project.png" width="800" />

- Paso 2: Configurar Instrucciones

Seleccionar el proyecto creado

<img src="images/chatgpt_select_project.png" width="800"  />

Hacer Click en "Add files".

<img src="images/chatgpt_add_files_project.png" width="800"  />

Pega estas instrucciones:

<img src="images/chatgpt_instructions_project.png" width="800"  />

```
IDENTIDAD:
Eres analista de datos y desarrollador de reportes visuales 
para seguridad ciudadana. Generas código Python para crear:
- Gráficos estadísticos (matplotlib, seaborn, plotly)
- Dashboards visuales
- Reportes PDF con visualizaciones integradas

CAPACIDADES DE GENERACIÓN:
1. Analizar CSV y proponer visualizaciones apropiadas
2. Generar código Python completo y ejecutable
3. Crear gráficos estáticos (PNG/JPG)
4. Generar gráficos interactivos (HTML con Plotly)
5. Integrar todo en PDF profesional

LIBRERÍAS DISPONIBLES:
- pandas: Manipulación de datos
- matplotlib: Gráficos estáticos básicos
- seaborn: Gráficos estadísticos avanzados
- plotly: Gráficos interactivos
- fpdf2 o reportlab: Generación de PDFs

ESTILO DE CÓDIGO:
- Siempre incluir imports completos
- Código comentado paso a paso
- Manejo de errores básico
- Rutas de archivo configurables
- Modular y reutilizable

PALETA DE COLORES ESTÁNDAR:
- Crítico/Alto: #E74C3C (rojo)
- Advertencia: #F39C12 (naranja)
- Moderado: #F1C40F (amarillo)
- Bajo: #2ECC71 (verde)
- Info: #3498DB (azul)

TIPOS DE GRÁFICOS PREFERIDOS:
- Barras horizontales: Top N elementos
- Barras verticales: Comparación temporal
- Líneas: Tendencias temporales
- Mapas de calor: Matrices de correlación
- Treemap: Proporciones jerárquicas
- Donut/Pie: Distribución porcentual (solo si <7 categorías)

FORMATO DE OUTPUT:
Al generar código, SIEMPRE incluye:
1. Explicación de qué hace el código
2. Librerías necesarias para instalar
3. El código completo
4. Nombre del archivo de salida
5. Instrucciones de ejecución
```


## EJERCICIO 1: Primera Visualización

- Crea chat: "Gráfico Top 10 Delitos"

Prompt RACE:

```
[ROLE] Desarrollador de visualizaciones de datos.

[ACTION] Genera código Python para crear gráfico de barras 
horizontales con los TOP 10 delitos más denunciados:

- Eje Y: Nombre del delito (des_articulo)
- Eje X: Cantidad de denuncias
- Colores: Gradiente según cantidad (más denuncias = más rojo)
- Título: "Top 10 Delitos Más Denunciados - Perú 2025"
- Etiquetas: Mostrar cantidad al final de cada barra
- Tamaño: 12x8 pulgadas
- Guardar como: top10_delitos.png

[CONTEXT] Gráfico para reporte ejecutivo mensual.

[EXPECTATION] 
- Código Python completo
- Que use el CSV cargado en el Project
- Comentarios explicando cada sección
- Gráfico profesional y legible
```

- Solicitar generación del gráfico

```
Genera el gráfico de salida
```

## EJERCICIO 2: Gráficos Estáticos Múltiples  

**Objetivo**

Generar suite completa de visualizaciones desde el CSV.

- Visualización 1: Mapa de Calor Departamental (10 min)

Crea chat: "Mapa de Calor Departamental"

Prompt RACE:

```
[ROLE] Analista de geografía criminal.

[ACTION] Genera código Python para mapa de calor (heatmap) 
que muestre:
- Filas: Top 15 departamentos (dpto_pjfs)
- Columnas: Top 5 categorías de delitos (generico)
- Valores: Cantidad de denuncias
- Colores: Escala de azul (bajo) a rojo (alto)
- Anotaciones: Mostrar números en cada celda
- Título: "Concentración de Delitos por Departamento y Tipo"
- Guardar como: heatmap_dpto_delitos.png

[CONTEXT] Identificar zonas y delitos críticos de un vistazo.

[EXPECTATION]
- Código usando seaborn o matplotlib
- Matriz legible (tamaño apropiado)
- Colores profesionales
```

- Visualización 2: Evolución Mensual

Crea chat: "Tendencia Mensual"

Prompt RACE:


```
[ROLE] Analista de tendencias temporales.

[ACTION] Genera código para gráfico de líneas múltiples:
- Eje X: Meses (periodo_denuncia)
- Eje Y: Cantidad de denuncias
- Líneas separadas para top 5 delitos más frecuentes
- Cada línea con color diferente y marcadores
- Leyenda clara
- Título: "Evolución Mensual - Top 5 Delitos"
- Grid para facilitar lectura
- Guardar como: tendencia_mensual.png

[CONTEXT] Identificar estacionalidad y tendencias.

[EXPECTATION]
- Código con pandas para agrupar por mes
- Gráfico claro con leyenda
- Líneas diferenciables
```

- Visualización 3: Distribución Porcentual (10 min)

Crea chat: "Gráfico Distribución"

Prompt RACE:

```
[ROLE] Diseñador de infografías estadísticas.

[ACTION] Genera código para gráfico donut (dona):
- Categorías: Tipos genéricos de delitos (generico)
- Solo mostrar las 6 categorías principales
- Resto agrupar en "Otros"
- Mostrar porcentajes dentro y fuera
- Colores según paleta del Project
- Título: "Distribución de Delitos por Categoría"
- Hueco en medio para destacar total
- Guardar como: distribucion_delitos.png

[CONTEXT] Gráfico para slide de presentación.

[EXPECTATION]
- Código matplotlib con gráfico donut
- Porcentajes claros
- Visualmente atractivo
```

## EJERCICIO 3: Dashboard Visual Complet

**Objetivo**
Crear dashboard estilo Power BI con múltiples visualizaciones en una imagen.

- Dashboard Integrado (30 min)

Crea chat: "Dashboard Ejecutivo"

Prompt RACE:

```
[ROLE] Diseñador de dashboards ejecutivos.

[ACTION] Genera código Python para crear UN SOLO archivo PNG 
con dashboard de 4 cuadrantes:

LAYOUT (2x2):
┌─────────────────┬─────────────────┐
│  CUADRANTE 1    │  CUADRANTE 2    │
│  Top 10 Delitos │  Mapa Calor     │
│  (Barras H)     │  Dpto x Tipo    │
├─────────────────┼─────────────────┤
│  CUADRANTE 3    │  CUADRANTE 4    │
│  Tendencia      │  KPIs Clave     │
│  Mensual        │  (Números)      │
└─────────────────┴─────────────────┘

CUADRANTE 4 debe mostrar:
- Total denuncias (número grande)
- Delito más frecuente
- Departamento más crítico
- Promedio denuncias/día

DISEÑO:
- Fondo blanco/gris claro
- Título general arriba: "Dashboard Delitos Denunciados - Perú 2025"
- Subtítulos por cuadrante
- Espacio entre gráficos
- Tamaño total: 16x12 pulgadas
- Guardar como: dashboard_ejecutivo.png

[CONTEXT] Dashboard para proyectar en reunión ejecutiva.

[EXPECTATION]
- Código usando plt.subplots(2,2)
- Todo en una imagen integrada
- Profesional y ejecutivo
- Cada cuadrante con su análisis

```


## EJERCICIO 4: PDF Reporte Completo

**Objetivo**

Generar PDF ejecutivo con todos los gráficos integrados.

- Fase 1: Estructura del Reporte (10 min)

Crea chat: "Diseño Reporte PDF"

Prompt:

```
Diseña estructura de reporte PDF ejecutivo (10 páginas):

ÍNDICE:
1. Portada
2. Resumen Ejecutivo (texto + KPIs)
3. Panorama General (gráfico top 10 delitos)
4. Análisis Geográfico (heatmap departamental)
5. Tendencias Temporales (gráfico evolución)
6. Distribución por Categoría (donut chart)
7. Dashboard Consolidado (página completa)
8. Top 5 Departamentos Críticos (tabla + mini gráfico)
9. Recomendaciones Operativas (texto estructurado)
10. Anexo: Metodología y fuentes

Para cada página indica:
- Título
- Contenido (gráfico/texto/tabla)
- Mensaje clave

```

- Fase 2: Código Generación PDF

Prompt RACE:

```
[ROLE] Desarrollador de reportes automatizados PDF.

[ACTION] Genera código Python COMPLETO para crear el PDF 
diseñado anteriormente:

REQUISITOS:
1. Usar fpdf2 o reportlab
2. Incluir TODOS los gráficos generados previamente
3. Texto generado desde análisis del CSV
4. Tablas con datos clave
5. Diseño profesional consistente

ESPECIFICACIONES:
- Tamaño: A4
- Márgenes: 2cm
- Fuente títulos: Arial Bold 16pt
- Fuente texto: Arial 11pt
- Numeración de páginas
- Encabezado: "Reporte Delitos Denunciados Perú 2025"
- Pie de página: Fecha generación + página

PORTADA DEBE INCLUIR:
- Título principal
- Subtítulo: "Análisis Enero-Noviembre 2025"
- Logo: [espacio reservado 200x200px]
- Fecha de generación
- Autor: "Unidad de Análisis Criminal"

[CONTEXT] PDF para distribución a fiscales y autoridades.

[EXPECTATION]
- Código modular (función por página)
- Comentarios extensos
- Manejo de rutas de imágenes
- PDF final profesional
- Nombre archivo: Reporte_Delitos_2025.pdf

```

- Fase 3: Testing y Ajustes (10 min)

Prompt:
```
El PDF generado necesita ajustes:
1. Las imágenes se ven muy grandes/pequeñas
2. El texto se corta entre páginas
3. Necesito más espacio entre secciones

Modifica el código para:
- Redimensionar imágenes automáticamente al ancho de página
- Agregar saltos de página apropiados
- Aumentar espacio entre elementos (1.5cm)
- Centrar todas las imágenes
```