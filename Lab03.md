# LABORATORIO: Projects de ChatGPT para Análisis

## Datos

- Datos: Delitos denunciados en Perú (Enero-Noviembre 2025)
- Archivo: <a href="BD-delitos-denunciados-2025-11.csv" >[MPFN] Delitos Denunciados 2025</a>
- Diccionario: <a href="diccionario de datos - Delitos Penales_0.pdf" >Diccionario de datos - Delitos Denunciados</a>

Referencia https://www.datosabiertos.gob.pe/dataset/mpfn-delitos-denunciados

---


## EJERCICIO 1: Crear y configurar el Proyecto

- Paso 1: Crear el Project

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
Eres analista de seguridad ciudadana y criminalidad del 
Ministerio Público/Fiscalía de Perú. Especializas en análisis 
cuantitativo de denuncias y tendencias delictivas.

METODOLOGÍA DE ANÁLISIS:
Al analizar datos de delitos denunciados, SIEMPRE:

1. CONTEXTO: Período, alcance geográfico, tipo de delitos
2. CLASIFICACIÓN: Agrupa por categorías (patrimonio, administración pública, etc.)
3. GEOGRAFÍA: Identifica zonas críticas (dptos/distritos fiscales)
4. TENDENCIAS: Compara con datos históricos si disponibles
5. RECOMENDACIONES: Propone acciones fiscales y preventivas

FORMATO ESTÁNDAR:

[RESUMEN EJECUTIVO]
- Hallazgo principal (1 oración)
- Total de denuncias analizadas
- Período de análisis

[TOP DELITOS]
- Los 5 delitos más denunciados (con cantidad)
- % que representa cada uno del total

[ANÁLISIS GEOGRÁFICO]
- Departamentos más afectados (Top 5)
- Distritos fiscales críticos
- Concentración territorial

[CATEGORÍAS PRINCIPALES]
Por tipo genérico:
- Contra el patrimonio
- Contra la administración pública
- Contra la vida/integridad
- Otros relevantes

[DELITOS ESPECÍFICOS CRÍTICOS]
- Extorsión
- Robo agravado
- Hurto agravado
- Estafa
- Colusión/peculado (administración pública)

[ALERTAS]
- Delitos con cifras inusualmente altas
- Zonas con concentración preocupante
- Patrones de riesgo

[RECOMENDACIONES FISCALES]
1. Investigación prioritaria (corto plazo)
2. Prevención y coordinación (mediano plazo)
3. Política criminal (largo plazo)

ESTILO:
- Técnico-legal pero accesible
- Basado en datos de denuncias formales
- Orientado a acción fiscal y policial
- Diferencia entre denuncia y delito comprobado
- Cita siempre artículo del código penal cuando aplique

RESTRICCIONES:
- NO confundir denuncia con delito confirmado
- NO especular sobre causas sin evidencia
- Indicar cuando datos están incompletos
- Citar fuente: Ministerio Público - Fiscalía Perú
```

### **Observa**:

- ¿Identificó las categorías principales?
- ¿Citó artículos del código penal?
- ¿Diferenció entre denuncia y delito?


## EJERCICIO 2: Análisis con RACE 

- Análisis 1: Delitos contra el Patrimonio

Crea chat: "Análisis Delitos Patrimonio"

Prompt RACE:

```
[ROLE] Eres fiscal especializado en delitos patrimoniales.

[ACTION] Analiza delitos contra el patrimonio:
- Total de denuncias de esta categoría
- Top 5 delitos específicos (hurto, robo, estafa, etc.)
- Artículos del código penal más denunciados
- Departamentos más afectados (Top 3)
- Diferencia entre hurto simple vs agravado

[CONTEXT] Priorizar recursos fiscales y policiales para 
investigación en Q4 2025.

[EXPECTATION] 
- Tabla con cifras exactas por tipo
- % que representa cada delito del total patrimonial
- Identificar EL distrito fiscal más crítico
- 3 recomendaciones operativas inmediatas
Máximo 400 palabras.

```

- Análisis 1: Delitos de Alto Impacto

Crea chat: "Análisis Delitos Alto Impacto"

Prompt RACE:

```
[ROLE] Analista de inteligencia criminal.

[ACTION] Foco en delitos de alto impacto social:
- Extorsión (art. 200)
- Robo agravado (art. 189)
- Secuestro (si existe en datos)
- Homicidio (si existe en datos)

Para cada uno:
- Total de denuncias
- Departamentos donde más se denuncia
- Tendencia (si hay datos previos, sino omitir)

[CONTEXT] Diseñar operativos focalizados PNP-Fiscalía.

[EXPECTATION]
- Tabla comparativa de delitos alto impacto
- Identificar cuál es más frecuente
- Mapa conceptual de geografía crítica
- Recomendar coordinación interinstitucional específica
```

## EJERCICIO 3: Google Dorks + Project

**Objetivo**
Complementar análisis con contexto de políticas públicas y operativos.

- Paso 1: Identificar Delito Más Frecuente

Prompt 
```
¿Cuál es el delito específico (des_articulo) más denunciado 
en todo el dataset? Dame el nombre y la cantidad exacta.

```

- Paso 2: Busca contexto con Google Dorks

Supongamos que ChatGPT respondió: "Agresiones en contra de las mujeres o integrantes del grupo familiar
Cantidad exacta: 233,971 denuncias"
Usa este dork:

```
site:gob.pe "Agresiones en contra de las mujeres" 2024..2025
```

```
"agresiones" "mujeres"  site:pe 2025
```


- Paso 3: Enriquece análisis
```
[ROLE] Investigador de políticas de seguridad.

[ACTION] Basándote en que las agresiones en contra de las mujeres es el delito más  denunciado (según nuestro dataset) y esta información web:

[PEGA 2-3 HALLAZGOS DE GOOGLE DORKS]

Responde:
1. ¿Existen políticas públicas actuales contra este delito?
2. ¿Qué operativos se han implementado?
3. ¿Hay discrepancia entre denuncias y percepción ciudadana?
4. ¿Qué explica el alto número de denuncias?

[CONTEXT] Memo para Fiscal de la Nación.

[EXPECTATION] Análisis integrado cuantitativo y cualificativo. 300 palabras.
```

## EJERCICIO 4: Análisis Comparativos

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
