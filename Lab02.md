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
site:gob.pe "gresiones en contra de las mujeres" OR "artículo 205" delito 2024..2025
```
