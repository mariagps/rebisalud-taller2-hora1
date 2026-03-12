# Referencia de sintaxis de PubMed

Fuente: PubMed Help (NLM) — https://pubmed.ncbi.nlm.nih.gov/help/

---

## Operadores booleanos

Los operadores deben escribirse en MAYÚSCULAS.

| Operador | Función | Ejemplo |
|----------|---------|---------|
| AND | Recupera resultados que contengan TODOS los términos | `heart disease AND prevention` |
| OR | Recupera resultados que contengan AL MENOS UNO de los términos | `heart disease OR cardiac disease` |
| NOT | Excluye resultados que contengan el término | `cancer NOT lung` |

- PubMed procesa de izquierda a derecha
- Usar paréntesis para agrupar conceptos: `(heart disease OR cardiac disease) AND prevention`
- NOT es un operador arriesgado: puede eliminar artículos relevantes que mencionan el término excluido de forma secundaria

---

## Etiquetas de campo (field tags)

Se colocan entre corchetes después del término. Desactivan el Automatic Term Mapping.

| Etiqueta | Campo | Ejemplo |
|----------|-------|---------|
| [ti] | Título | `cancer[ti]` |
| [tiab] | Título y abstract | `vaccine[tiab]` |
| [tw] | Text Words (título, abstract, MeSH, otros) | `diabetes[tw]` |
| [mh] | MeSH Terms | `"Kidney Diseases"[mh]` |
| [majr] | MeSH Major Topic | `"Hypertension"[majr]` |
| [au] | Autor | `smith ja[au]` |
| [1au] | Primer autor | `smith ja[1au]` |
| [lastau] | Último autor | `jones b[lastau]` |
| [ta] | Revista (journal) | `gene therapy[ta]` |
| [pt] | Tipo de publicación | `review[pt]` |
| [dp] | Fecha de publicación | `2024[dp]` |
| [ad] | Afiliación | `harvard[ad]` |
| [la] | Idioma | `english[la]` |
| [sb] | Subset | `medline[sb]` |

Nota: si se buscan varios términos en el mismo campo, cada uno necesita su propia etiqueta: `cancer[ti] AND vaccine[ti]`

---

## Búsqueda por frase

Las comillas dobles preservan el orden de las palabras y desactivan el ATM:
- `"kidney allograft"` busca la frase exacta
- Si la frase no existe en el índice, PubMed muestra un aviso

---

## Truncamiento (wildcards)

El asterisco (*) sustituye 0 o más caracteres. Se necesitan al menos 4 caracteres antes del primer asterisco.

| Ejemplo | Recupera |
|---------|----------|
| `vaccin*` | vaccine, vaccination, vaccines, vaccinated... |
| `"breast feed*"` | breast feeding, breast feeds... |
| `organi*ation*` | organization, organisations, organizational... |

El truncamiento desactiva el ATM y la expansión jerárquica de MeSH.

---

## Búsqueda por proximidad

Formato: `"término1 término2"[campo:~N]`

Campos válidos: [ti], [tiab], [ad] (o sus formas largas [Title], [Title/Abstract], [Affiliation])

N = número máximo de palabras entre los términos (en cualquier orden):
- N=0: términos adyacentes
- N mayor: búsqueda más amplia

Ejemplos:
- `"rationing healthcare"[tiab:~2]` — encuentra "rationing" y "healthcare" separados por un máximo de 2 palabras
- `"cell therapy"[ti:~0]` — adyacentes en el título

---

## Búsqueda por fecha

Fecha única: `YYYY/MM/DD[dp]` (mes y día opcionales)
- `cancer AND 2024[dp]`

Rango: `YYYY/MM/DD:YYYY/MM/DD[dp]`
- `heart disease AND 2019/01/01:2019/06/30[dp]`

Campos de fecha disponibles:
- [dp] = Publication Date
- [edat] = Entry Date (fecha de entrada en PubMed)
- [mhda] = MeSH Date
- [crdt] = Create Date

---

## Filtros y subsets

| Filtro | Función |
|--------|---------|
| `medline[sb]` | Solo artículos indexados en MEDLINE |
| `free full text[sb]` | Solo texto completo gratuito |
| `hasabstract` | Solo citas con abstract |
| `NOT preprint[pt]` | Excluir preprints |
| `publisher[sb]` | Artículos enviados por editores (aún no indexados) |
| `inprocess[sb]` | En proceso de indexación |

---

## Automatic Term Mapping (ATM)

Cuando se introduce un término sin etiqueta de campo, PubMed automáticamente:
1. Busca en la tabla de traducción MeSH y sus entry terms
2. Incluye términos MeSH jerárquicamente más específicos
3. Gestiona variantes ortográficas (británicas/americanas)
4. Procesa sinónimos

Para **desactivar el ATM**: usar etiquetas de campo, comillas, truncamiento o el Search Builder.

---

## Historial de búsqueda (Search History)

- Las búsquedas se numeran cronológicamente: #1, #2, #3...
- Se pueden reutilizar: `#1 OR #2` combina búsquedas anteriores
- Límite: 100 búsquedas; caduca tras 8 horas de inactividad
- La columna "Details" muestra cómo PubMed tradujo cada consulta

---

## Búsqueda de autores

- Formato estándar: `apellido iniciales` → `smith ja`
- Nombre completo: `john a smith`
- Con etiqueta: `brody[au]` (solo busca apellido)
- Comillas para coincidencia exacta: `"smith j"[au]`

---

## Búsqueda de revistas

- Nombre completo: `molecular biology of the cell`
- Abreviatura: `mol biol cell`
- ISSN: `1059-1524`
- Con etiqueta: `gene therapy[ta]`

---

## Palabras vacías (stopwords)

Palabras comunes como "by", "of", "the" son ignoradas salvo que se usen con etiqueta de campo.

---

## Caracteres especiales

Los guiones pueden requerir comillas o eliminación. PubMed convierte algunos caracteres especiales automáticamente.
