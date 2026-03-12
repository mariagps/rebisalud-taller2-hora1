# PRESS 2015 — Checklist para revisión de estrategias de búsqueda

Fuente: McGowan J, et al. "PRESS Peer Review of Electronic Search Strategies: 2015 Guideline Statement." J Clin Epidemiol. 2016;75:40-46. Checklist completa: CADTH, 2016.

---

## Qué es PRESS

PRESS (Peer Review of Electronic Search Strategies) es una guía basada en evidencia para revisar estrategias de búsqueda electrónica. Se usa en revisiones sistemáticas, evaluaciones de tecnologías sanitarias y otras síntesis de evidencia.

La revisión por pares de la estrategia de búsqueda reduce errores y mejora la calidad de la recuperación de información.

---

## Los 6 elementos de la checklist

### 1. Traducción de la pregunta de investigación

- ¿La estrategia refleja adecuadamente la pregunta de investigación / el marco PICO?
- ¿Están todos los conceptos clave representados?
- ¿El alcance de la búsqueda es apropiado (ni demasiado amplio ni demasiado estrecho)?
- ¿El volumen de resultados es razonable para la pregunta?

**Errores frecuentes:**
- Omitir un concepto PICO
- Incluir conceptos innecesarios que restringen demasiado
- No adaptar la estrategia al tipo de revisión (exploratoria vs. exhaustiva)

---

### 2. Operadores booleanos y de proximidad

- ¿Se usan AND, OR y NOT correctamente?
- ¿Los paréntesis agrupan los conceptos de forma lógica (nesting)?
- ¿El uso de NOT podría excluir artículos relevantes de forma involuntaria?
- ¿Se podrían usar operadores de proximidad para mejorar la precisión?

**Errores frecuentes:**
- Usar AND donde debería ir OR (dentro de un mismo bloque de sinónimos)
- Usar OR donde debería ir AND (entre bloques conceptuales diferentes)
- Paréntesis mal colocados que cambian la lógica de la búsqueda
- NOT aplicado a términos ambiguos

**Ejemplo de error:**
```
Incorrecto: heart failure AND cardiac failure AND heart dysfunction
Correcto:   heart failure OR cardiac failure OR heart dysfunction
```
(Son sinónimos dentro del mismo bloque → deben ir con OR)

---

### 3. Vocabulario controlado (Subject Headings / MeSH)

- ¿Los descriptores MeSH seleccionados son relevantes para cada concepto?
- ¿Están completos o faltan descriptores importantes?
- ¿La amplitud es apropiada (término genérico vs. específico)?
- ¿La explosión (explosion) está bien configurada?
- ¿Se justifica el uso de Major Headings ([majr])?
- ¿Los subheadings aplicados son apropiados?
- ¿Se combina vocabulario controlado con texto libre?

**Errores frecuentes:**
- Usar un MeSH demasiado genérico sin texto libre complementario
- Usar un MeSH demasiado específico que deja fuera artículos relevantes
- No explotar un término cuando debería explotarse
- Aplicar subheadings que excluyen artículos relevantes
- Usar solo MeSH sin texto libre (pierde artículos no indexados)

---

### 4. Búsqueda por texto libre (Text Word)

- ¿Se incluyen variantes ortográficas (británica/americana)?
- ¿Se incluyen sinónimos suficientes?
- ¿El truncamiento es correcto y tiene la amplitud adecuada?
- ¿Se incluyen acrónimos y abreviaturas relevantes?
- ¿Los términos son suficientemente específicos?
- ¿Se han elegido los campos correctos ([tiab], [tw], [ti])?
- ¿Las cadenas de texto son manejables?

**Errores frecuentes:**
- Truncar demasiado corto: `card*` recupera cardiac, cardboard, cardinal...
- Truncar demasiado largo: `cardiovascular` sin truncar pierde "cardiovasculares"
- Olvidar variantes: buscar solo "tumor" sin "tumour"
- Olvidar acrónimos: buscar "chronic obstructive pulmonary disease" sin "COPD"
- Usar [ti] cuando debería usarse [tiab] (pierde términos en el abstract)

---

### 5. Ortografía, sintaxis y números de línea

- ¿Hay errores ortográficos en los términos de búsqueda?
- ¿La sintaxis es correcta para la base de datos utilizada?
- ¿Los símbolos de truncamiento son los correctos para esa base de datos?
- ¿Todas las líneas de búsqueda están correctamente referenciadas en la combinación final?

**Errores frecuentes:**
- Errores tipográficos en términos de búsqueda
- Usar sintaxis de una base de datos en otra (ej: sintaxis Ovid en PubMed)
- Olvidar incluir una línea de búsqueda en la combinación final
- Usar el símbolo de truncamiento equivocado ($ en vez de * o viceversa)

---

### 6. Límites y filtros

- ¿Los límites aplicados son apropiados para la pregunta?
- ¿Los filtros son relevantes y están validados?
- ¿Faltan filtros que deberían aplicarse?
- ¿Hay filtros excesivos que podrían excluir artículos relevantes?
- ¿Se documenta la fuente de los filtros utilizados?

**Errores frecuentes:**
- Limitar por idioma sin justificación
- Limitar por fecha sin justificación
- Usar filtros metodológicos no validados
- Aplicar filtros de tipo de publicación que excluyen estudios relevantes
- Usar filtros del panel lateral de PubMed sin ser consciente de que eliminan artículos no indexados

---

## Cómo usar esta checklist

1. **Antes de ejecutar**: revisar la estrategia punto por punto
2. **Después de ejecutar**: si los resultados son inesperados (demasiados, muy pocos, irrelevantes), volver a la checklist para identificar el problema
3. **En pares**: idealmente, una persona construye la estrategia y otra la revisa con esta checklist

---

## Resumen rápido para revisión

| Elemento | Pregunta clave |
|----------|---------------|
| Traducción PICO | ¿Refleja todos los conceptos de la pregunta? |
| Booleanos | ¿OR dentro de bloques, AND entre bloques? |
| MeSH | ¿Descriptores relevantes + explosión correcta? |
| Texto libre | ¿Sinónimos, variantes, truncamiento adecuado? |
| Sintaxis | ¿Sin errores tipográficos, sintaxis correcta? |
| Filtros | ¿Apropiados y no excesivamente restrictivos? |
