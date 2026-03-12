# Estrategia de búsqueda exhaustiva en PubMed

Fuente: McKeever L, et al. "Demystifying the Search Button: A Comprehensive PubMed Search Strategy for Performing an Exhaustive Literature Review." JPEN. 2015;39(6). PMC4513072. CC BY-NC 3.0.

---

## Concepto clave

Las estrategias basadas en MEDLINE son robustas pero solo capturan el 89% de las citas disponibles en PubMed. El 11% restante son artículos recientes que aún no tienen indexación MeSH. Una búsqueda exhaustiva debe cubrir ambas partes.

---

## Estructura de la "Master Search Strategy"

```
(Estrategia MeSH en MEDLINE)
OR
((Estrategia texto libre en No-MEDLINE) NOT medline[sb])
```

Esto combina:
1. Una búsqueda precisa con vocabulario controlado (MeSH) para el 89% indexado
2. Una búsqueda por texto libre para el 11% aún no indexado

---

## Parte 1: Búsqueda en MEDLINE con MeSH

### Cómo encontrar términos MeSH

**Método 1 — Base de datos MeSH:**
1. Seleccionar "MeSH" en el desplegable de PubMed
2. Buscar el término en inglés
3. Explorar la jerarquía (16 categorías temáticas, hasta 12 niveles)
4. Revisar los subheadings disponibles (hasta 83 opciones: adverse effects, economics, etc.)
5. Usar "Add to Search Builder" para acumular términos

**Método 2 — Análisis de artículos conocidos:**
1. Localizar artículos relevantes ya conocidos
2. Examinar los "MeSH Terms" asignados a cada artículo
3. Los términos con asterisco (*) indican el tema principal del artículo
4. Incorporar esos descriptores a la estrategia

### Construcción de la estrategia MeSH

Estructura modular por bloques PICO:
```
(Bloque Población: MeSH1 OR MeSH2 OR texto libre)
AND
(Bloque Intervención: MeSH3 OR MeSH4 OR texto libre)
AND
(Bloque Outcome: MeSH5 OR texto libre)
```

- Dentro de cada bloque: sinónimos unidos con OR
- Entre bloques: unidos con AND

---

## Parte 2: Búsqueda en No-MEDLINE (texto libre)

Para los artículos que aún no tienen MeSH:

- Usar sinónimos unidos con OR
- Incluir variantes ortográficas: `(color OR colour)`
- Incluir plurales y formas alternativas
- Incluir acrónimos con y sin puntos
- Usar truncamiento: `microbiolog*`
- Encerrar frases entre comillas: `"alternate day fasting"`
- Añadir `NOT medline[sb]` para aislar solo las citas no indexadas

---

## Ejemplo práctico: Ayuno en días alternos

**Parte MEDLINE (17 resultados):**
```
(("Fasting"[MeSH] OR "Obesity/diet therapy"[MeSH]
OR "Weight Loss/physiology"[MeSH]) AND "Humans"[MeSH])
AND ("alternate day fasting" OR "fasting on alternating days"
OR "alternate-day fasting")
```

**Parte No-MEDLINE (12 resultados):**
```
("Alternate Day Fasting" OR "fasting on alternating days"
OR "alternate-day fasting") NOT medline[sb]
```

**Combinada (29 resultados):**
Unir ambas partes con OR.

---

## Uso de filtros: precaución

Los filtros del panel izquierdo de PubMed (Article Type, Species, Sex, Age) usan codificación MeSH, por lo que al activarlos se pierden automáticamente los resultados No-MEDLINE.

**Solución:** aplicar los filtros manualmente con AND solo dentro de la parte MEDLINE de la estrategia.

Subsets útiles:
| Filtro | Función |
|--------|---------|
| `medline[sb]` | Solo MEDLINE |
| `publisher[sb]` | Enviados por editores |
| `inprocess[sb]` | En proceso de indexación |
| `free full text[sb]` | Texto completo gratuito |

---

## Operador NOT: usar con precaución

NOT es un operador arriesgado. Elimina TODOS los artículos que contengan el término excluido, aunque el artículo sea relevante y solo mencione el término de forma secundaria.

**Uso seguro de NOT:**
Combinar con AND para aislar resultados nuevos al ampliar una búsqueda:
```
(Búsqueda ampliada) NOT (Búsqueda original)
```
Esto muestra solo los artículos nuevos que la ampliación ha capturado.

---

## Verificación: Search Details

Siempre revisar el cuadro "Search Details" (esquina inferior derecha de la página de resultados) para comprobar cómo PubMed ha interpretado la búsqueda. Esto revela si se ha aplicado el ATM, qué campos se han buscado y si hay errores de sintaxis.

---

## Alertas automáticas con MyNCBI

1. Crear cuenta gratuita en MyNCBI
2. Guardar la estrategia finalizada
3. Configurar alerta (diaria, semanal o mensual)
4. Recibir por correo las nuevas citas que coincidan

---

## Resumen del flujo de trabajo

1. Identificar los conceptos de búsqueda (PICO)
2. Construir la parte MEDLINE con MeSH (usar MeSH Database + artículos conocidos)
3. Añadir texto libre con OR dentro de cada bloque MeSH
4. Conectar bloques con AND
5. Ejecutar la búsqueda MEDLINE
6. Construir la parte No-MEDLINE con sinónimos en texto libre
7. Añadir `NOT medline[sb]`
8. Combinar ambas partes con OR
9. Revisar Search Details
10. Guardar en MyNCBI y configurar alerta

---

## Sobre reproducibilidad

Los artículos recuperados de la parte No-MEDLINE pueden convertirse en artículos MEDLINE con el tiempo (al ser indexados). Para revisiones sistemáticas, documentar qué artículos provienen de cada parte para garantizar la reproducibilidad.
