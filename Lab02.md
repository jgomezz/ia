# LABORATORIO: Análisis de Datos con ChatGPT

## RACE Prompt Engineering + Google Dorks (2 horas)

- Datos: Delitos denunciados en Perú (Enero-Noviembre 2025)
- Archivo: <a href="BD-delitos-denunciados-2025-11.csv" >[MPFN] Delitos Denunciados 2025</a>
- Diccionario: <a href="diccionario de datos - Delitos Penales_0.pdf" >Diccionario de datos - Delitos Denunciados</a>

Referencia https://www.datosabiertos.gob.pe/dataset/mpfn-delitos-denunciados

---


## EJERCICIO 1: Análisis Básico con RACE
- Paso 1: Sube el archivo CSV a ChatGPT
- Paso 2: Prompt sin RACE (método malo)

```
Analiza los datos de delitos
```

- Observa: Respuesta genérica, poco útil

- Paso 3: Prompt con RACE (método correcto)

```
[ROLE] Eres un analista de seguridad ciudadana del Ministerio Público de Perú.

[ACTION] Analiza el archivo CSV de delitos denunciados e identifica:
1. Los 5 departamentos con más denuncias totales
2. Los 3 tipos de delitos más frecuentes a nivel nacional
3. El departamento con mayor tasa de delitos contra el patrimonio

[CONTEXT] Los datos corresponden a enero-noviembre 2025. 
Enfócate en delitos que afectan directamente a ciudadanos.

[EXPECTATION] Presenta resultados en tabla. Incluye cifras exactas 
y porcentajes. Finaliza con 2 conclusiones clave.
```

- Compara resultados

|Aspecto | Sin RACE| Con RACE |
|-|-|-|
|Claridad |||
|Utilidad |||
|Formato |||

Para completarla, puedes usar: ALTO, MEDIO, BAJO

## EJERCICIO 2: Análisis Comparativo 

- Prompt RACE para comparación regional

```
[ROLE] Eres consultor en política criminal para el gobierno regional.

[ACTION] Compara los delitos entre Lima, Arequipa y Cusco:
- Estafas (artículos 196 y 196-A)
- Extorsión (artículo 200)
- Robo agravado (artículo 189)

[CONTEXT] Necesito decidir dónde priorizar recursos policiales 
en el último trimestre del año.

[EXPECTATION] 
1. Tabla comparativa con cantidades
2. Identifica cuál región tiene más de cada delito
3. Recomienda 1 región prioritaria con justificación
```

- Variación: Análisis temporal

```
[ROLE] Eres analista de tendencias criminales.

[ACTION] Identifica patrones preocupantes en delitos contra 
la administración pública (colusión, peculado, cohecho).

[CONTEXT] Datos de 11 meses de 2025. Busca departamentos 
con cifras anormalmente altas.

[EXPECTATION] 
- Top 5 departamentos
- Tipo de delito administrativo predominante en cada uno
- 1 hipótesis del por qué (basada en datos)
```

## EJERCICIO 3: Google Dorks + ChatGPT

**¿Qué son Google Dorks?**

Comandos avanzados para búsquedas precisas en Google.

### Dorks útiles para este caso
1. Buscar reportes oficiales:

```
site:gob.pe "delitos denunciados" filetype:pdf
```
2. Buscar estadísticas complementarias:
```
site:inei.gob.pe "seguridad ciudadana" 2024..2025
```
3. Buscar noticias sobre extorsión:
```
"extorsión" site:pe inurl:noticias 2025
```
4. Buscar estudios académicos:
```
site:edu.pe "criminalidad" OR "delincuencia" filetype:pdf
```


## EJERCICIO 4: Combinación

- Paso 1: Identifica el delito más frecuente con ChatGPT

```
[ROLE] Analista de datos.
[ACTION] ¿Cuál es el delito específico (des_articulo) con más denuncias?
[CONTEXT] Archivo CSV completo.
[EXPECTATION] Dame el nombre del delito y cantidad exacta.
```

- Paso 2: Busca contexto con Google Dorks

Supongamos que ChatGPT respondió: "Agresiones en contra de las mujeres o integrantes del grupo familiar
Cantidad exacta: 233,971 denuncias"
Usa este dork:

```
site:gob.pe "Agresiones en contra de las mujeres" OR "artículo 205" delito 2024..2025
```

- Paso 3: Enriquece análisis con ChatGPT
```
[ROLE] Analista criminológico.
[ACTION] Basándote en estos datos del CSV y la información 
web que encontré [pega resumen de búsqueda], explica:
- ¿Por qué "Agresiones en contra de las mujeres" es tan frecuente?
- ¿Qué tipo de casos incluye típicamente?
- ¿Es delito grave o leve?

[CONTEXT] Necesito explicarlo a ciudadanos sin conocimiento legal.
[EXPECTATION] Respuesta clara, máximo 150 palabras.
```
## EJERCICIO 5: Caso de Uso Real

Escenario
Eres analista en ONG de seguridad ciudadana. Te piden:
"Identificar qué departamentos necesitan urgentemente
programas de prevención de violencia contra mujeres"
- Paso 1: Prompt RACE para ChatGPT
```
[ROLE] Analista de género y seguridad para ONG.

[ACTION] Del CSV, identifica departamentos con mayor incidencia de:
- Lesiones (artículos relacionados si existen)
- Violencia familiar (si está categorizada)
- Delitos sexuales (si están en los datos)

Si no encuentras categorías específicas de género, identifica 
delitos que típicamente afectan más a mujeres.

[CONTEXT] Datos enero-noviembre 2025. Necesito priorizar 
3 departamentos para intervención.

[EXPECTATION] 
1. Tabla con Top 5 departamentos
2. Tipos de delitos más frecuentes en cada uno
3. Recomendación de 3 regiones prioritarias con justificación
```
- Paso 2: Complementa con Google Dorks

Busca estadísticas oficiales:
```
site:inei.gob.pe "violencia contra la mujer" estadísticas 2025
```
Busca programas existentes:
```
site:gob.pe "programa prevención violencia" departamento filetype:pdf
```
- Paso 3: Genera reporte ejecutivo

```
[ROLE] Redactor de informes ejecutivos para ONG.

[ACTION] Redacta un brief ejecutivo (1 página) que incluya:
- Hallazgos principales del análisis de datos
- Top 3 departamentos prioritarios
- Justificación basada en cifras
- 2 recomendaciones de acción

[CONTEXT] Audiencia: Directora ejecutiva de ONG (no técnica).
Datos: CSV de delitos + info web encontrada.

[EXPECTATION] Máximo 300 palabras, lenguaje claro, 
incluye cifras concretas. Formato: título, hallazgos, 
recomendaciones.
```
## EJERCICIO 6: Detección de Anomalías

- Prompt RACE avanzado

```
[ROLE] Científico de datos especializado en criminología.

[ACTION] Identifica 3 anomalías o patrones inusuales en los datos:
- Delitos con cifras sospechosamente altas en un solo distrito
- Tipos de delito que aparecen en zonas inesperadas
- Distribuciones geográficas anormales

[CONTEXT] Busco entender si hay outliers que requieren investigación 
adicional o posibles errores en datos.

[EXPECTATION] Para cada anomalía indica:
- Qué es
- Dónde ocurre (departamento/distrito)
- Por qué es inusual
- Hipótesis de causa
```

## PLANTILLAS RACE

- Template 1: Análisis exploratorio
```
[ROLE] Analista de datos del sector [X]
[ACTION] Explora el dataset e identifica [Y patrones/métricas]
[CONTEXT] Datos de [período] sobre [tema]. Enfoque en [aspecto]
[EXPECTATION] [Formato específico], [cantidad de insights], [audiencia]
```

- Template 2: Comparación
```

[ROLE] Consultor estratégico
[ACTION] Compara [A] vs [B] en términos de [criterios]
[CONTEXT] Necesito [decisión] basada en [factores]
[EXPECTATION] Tabla comparativa + recomendación justificada
```

- Template 3: Reporte ejecutivo

```
[ROLE] Redactor de informes para [nivel directivo]
[ACTION] Genera reporte de [tema] destacando [aspectos clave]
[CONTEXT] Audiencia [perfil]. Datos disponibles: [fuentes]
[EXPECTATION] [Extensión], [secciones específicas], lenguaje [tipo]
```

## GOOGLE DORKS ESENCIALES

|Dork | Uso |
|-|-|
|site:dominio.com | Buscar solo en ese sitio|
|filetype:pdf|Solo archivos PDF|
|"frase exacta"| Coincidencia exacta|
|2024..2025| Rango de años
|OR| Una u otra palabra|
|intitle:palabra|Palabra en el título|
|inurl:palabra|Palabra en la URL|
|-palabra|Excluir término|


- Ejemplos para análisis de seguridad
```
site:gob.pe "estadística criminal" filetype:xlsx
```
```
"delitos contra el patrimonio" site:pe 2025 -pdf
```
```
site:mpfn.gob.pe OR site:pj.gob.pe "robo agravado"
```
```
intitle:"reporte delitos" site:edu.pe filetype:pdf 2024..2025
```

FIN