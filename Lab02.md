# LABORATORIO: Análisis de Datos con ChatGPT

## RACE Prompt Engineering + Google Dorks (2 horas)

- Archivo: BD-delitos-denunciados-2025-11.csv
- Datos: Delitos denunciados en Perú (Enero-Noviembre 2025)

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


