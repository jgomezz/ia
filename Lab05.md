# LABORATORIO: Análisis de datos con NotebookLM

Este laboratorio está diseñado para transformar a **NotebookLM** en un analista de datos avanzado, utilizando archivos de criminalidad y diccionarios técnicos como fuente de verdad.

## Datos

- Datos: Delitos denunciados en Perú (Enero-Noviembre 2025)
- Archivo: <a href="dataset/BD-delitos-denunciados-2025-11.csv" >[MPFN] Delitos Denunciados 2025</a>
- Diccionario: <a href="dataset/Diccionario de datos- Delitos Penales.csv" >Diccionario de datos - Delitos Denunciados</a>

Referencia https://www.datosabiertos.gob.pe/dataset/mpfn-delitos-denunciados

---


## EJERCICIO 1: Configuracion de NotebookLM

### PASO 1 - Configuración del Entorno y Fuentes

A diferencia de los Gems de Gemini, NotebookLM basa su potencia en el análisis de documentos específicos cargados en un "Cuaderno".

1.  **Acceso:** Ingresa a [NotebookLM](https://notebooklm.google.com/).
2.  **Creación:** Haz clic en **"Nuevo Cuaderno"** y asígnale el nombre: `Proyecto de Análisis de Datos`.
3.  **Carga de Conocimiento:** En el panel de "Fuentes", sube los siguientes archivos:
    * `BD-delitos-denunciados-2025-11.csv` (Dataset).
    * `Diccionario de datos- Delitos Penales.csv` (Diccionario de datos).

<img src="images/notebookLM_create.png" />

---

### PASO 2: Definición del Rol (Instrucciones Personalizadas)

Para que NotebookLM actúe con el rigor de un analista, se procedera a configura el chat, ingresar a la siguiente opción

<img src="images/notebookLM_select_set_chat.png" />


**Prompt de Configuración:**
```
Role: Actúa como mi Analista de Datos Senior especializado en Seguridad Pública.

Instrucciones:

 1. Siempre cruza la información del CSV con las definiciones del 'Diccionario de Datos'.
 2. Al responder sobre códigos técnicos, tradúcelos automáticamente a nombres legibles (Formato Tipo Oración).
 3. Si detectas inconsistencias entre el CSV y las reglas del PDF, repórtalo de inmediato.
 4. Genera siempre un resumen ejecutivo apto para exportar a Google Docs.

```
<img src="images/notebookLM_set_chat.png" />


---


## PASO 3: Análisis de Integridad y Contexto

Vamos a verificar si NotebookLM puede razonar sobre ambos archivos simultáneamente sin necesidad de recordarle qué archivos tiene.

**Prompt de Análisis:**

```text
Basado estrictamente en las fuentes cargadas:
1. Valida si las columnas del CSV coinciden con lo estipulado en el Diccionario de Datos. Reporta errores de formato si existen.
2. Identifica los 3 distritos con menor cantidad de denuncias registradas.
3. Presenta una tabla con el distrito y la cifra exacta de registros encontrados en el documento.
```


## PASO 4: Storytelling y Síntesis Regional

NotebookLM destaca creando "Notas guardadas" que puedes usar para tu reporte final.

**Prompt de Análisis:**

```text
Role: 
   Experto en Comunicación de Datos.

Action: 
   Analiza la situación en el departamento de AMAZONAS. 

Expectation:
   1. Describe la distribución de delitos por el campo 'generico' en dicha región.
   2. Identifica cuál es el delito dominante y busca en el diccionario de datos el artículo legal asociado.
   3. Escribe un párrafo narrativo para una presentación que explique el impacto social de este dato en Amazonas.

```

## PASO 5: Reporte Final y Exportación

NotebookLM permite consolidar notas para crear documentos estructurados.

**Prompt de Análisis:**

```text
Role: Consultor Senior para el Ministerio Público.

Action: 
   Elabora el "Informe Anual de Tendencias de Criminalidad 2025" consolidando la inteligencia del CSV y el Diccionario de Datos.

Expectation:
   1. Resumen Ejecutivo: Un párrafo de alto impacto con el hallazgo más crítico.
   2. Análisis de Integridad: Confirmación de cumplimiento técnico según el PDF.
   3. Diagnóstico Regional: Ranking de los 3 Distritos Fiscales más afectados.
   4. Foco Legal: Análisis de la incidencia de la Ley Nº 30096 (Ciberdelincuencia).
   5. Recomendaciones: 3 acciones concretas para 2026.

Formato: 
   Usa encabezados (H1, H2) y negritas para KPIs. Confírmame cuando esté listo para ser copiado a Google Docs.

```