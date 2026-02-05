# LABORATORIO: Análisis de datos con Gemini

## Datos

- Datos: Delitos denunciados en Perú (Enero-Noviembre 2025)
- Archivo: <a href="BD-delitos-denunciados-2025-11.csv" >[MPFN] Delitos Denunciados 2025</a>
- Diccionario: <a href="diccionario de datos - Delitos Penales_0.pdf" >Diccionario de datos - Delitos Denunciados</a>

Referencia https://www.datosabiertos.gob.pe/dataset/mpfn-delitos-denunciados

---


## EJERCICIO 1: Entendiendo los datos


- **Paso 1 - Entendiendo los datos** 

**Objetivo**: Que la IA explique el archivo al analista para evitar errores de interpretación.

Subir los 2 archivos y ejecutar el siguiente prompt


```
Role: Actúa como un consultor de datos que explica conceptos.

Action: Lee el PDF del diccionario y analiza el CSV. Explícame en lenguaje sencillo de qué trata esta base de datos.

Context: Estoy empezando a usar IA y no quiero confundirme con nombres técnicos de las columnas.

Expectation: Una lista de las 5 columnas más importantes para hacer un reporte de seguridad y un aviso si encuentras algo que no coincida entre el diccionario y el CSV.

```

- **Paso 2 - Limpieza de Datos**

**Objetivo**: Aprender a corregir textos y formatos solo hablando con la IA.

Vamos a arreglar los nombres de los delitos que están en mayúsculas.

```
Role: Actúa como un editor de contenido experto.

Action: Ayúdame a limpiar la columna des_articulo y distrito_fiscal.

Context: Los nombres están en mayúsculas cerradas y se ven mal en un reporte.

Expectation: 
      1. Cambia los nombres a formato tipo oración (Ej: "FRAUDE INFORMÁTICO" a "Fraude informático"). 
      2. Muéstrame una tabla con el antes y después de 5 ejemplos.

```

- **Paso 3 - Extracción de Insight**

**Objetivo**: Encontrar dónde está el problema de la ciberdelincuencia.

Vamos a arreglar los nombres de los delitos que están en mayúsculas.

```
Role: Actúa como un detective de datos.

Action: Busca en el archivo todas las denuncias que tengan que ver con la "LEY DE DELITOS INFORMATICOS".

Context: Mi jefe necesita saber en qué regiones de Perú se están denunciando más estos casos.

Expectation: 
      1. Una tabla que sume la cantidad por distrito_fiscal solo de esos delitos. 
      2. Un gráfico sencillo (de barras) creado aquí mismo que muestre esta comparación. 
      3. Dime qué región es la más afectada según los números.

```

- **Paso 4 - Creación del Reporte y PDF Final**

**Objetivo**: Aprender el flujo de trabajo para presentar el trabajo.

Unificar todo en un informe profesional.

```
Role: Actúa como un redactor jefe de informes corporativos.

Action: Redacta un resumen ejecutivo de lo que hemos descubierto hoy sobre las denuncias de noviembre 2025.

Context: El reporte debe ser breve, para alguien que tiene poco tiempo de leer.

Expectation: 
      1. Un título impactante. 
      2. Tres puntos clave (insights). 
      3. Una conclusión sobre el impacto de la ciberdelincuencia. 
      4. Organiza todo con negritas y viñetas para que se vea bien al exportarlo a un documento.

```

Para exportar el documento realizarlo en esta opción

<img src="images/gemini_exportar.png" />