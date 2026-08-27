# BIBLIOGRAPHY_AUDIT

## Estado actual de `referencias.bib`

| Clave | Tipo | Usada en | Notas |
|---|---|---|---|
| `Kaplan2009` | `@article` — Kaplan, Hadad, Doorn, "Ingenieria de requisitos", Journal of Software Engineering, 2009 | **No citada en ningún capítulo** | Entrada huérfana. O se usa (hay contenido de "análisis de requerimientos" en Capitulo2.tex que podría citarla) o se elimina. |
| `MulticomSobreMulticomServicios` | `@misc` — página web `multicomcomercio.com/nosotros.html`, "Accedido: 14-May-2026" | Capitulo1.tex (2 veces), Capitulo2.tex (Servicios) | Fuente primaria de la empresa, válida como fuente institucional, pero es una sola página web genérica para sustentar varias afirmaciones distintas. |
| `MulticomMisionVision` | `@misc` — página web `multicomcomercio.com/`, "Accedido: 14-May-2026" | Capitulo1.tex (Misión, Visión) | Igual que la anterior. |

**Total: 3 entradas, 2 citas reales, ambas apuntando al mismo sitio web de Multicom.** Cero fuentes
académicas o técnicas.

## Lo que pidió el profesor (PF-015, ver PROFESSOR_FEEDBACK.md)

> "Hace falta más bibliografía, por ejemplo de la tecnología referenciada"

Esto es un señalamiento directo y sin resolver.

## Afirmaciones en el documento que probablemente necesiten fuente (diagnóstico, NO se inventó ninguna referencia)

Clasificación según la categoría C del prompt de Xavier ("información externa" que normalmente
necesita fuente):

1. **Capitulo1.tex** — "La organización cuenta con una plataforma robusta y estable" → ya
   señalado explícitamente por el profesor como afirmación sin sustento (PF-001).
2. **Capitulo1.tex / Capitulo2.tex** — Descripciones conceptuales de patrones/tecnologías
   mencionadas como si fueran hechos generales y no solo experiencia propia:
   - Patrón **MVC** (Modelo-Vista-Controlador) — se usa como concepto técnico general, no solo
     como "lo que yo hice". Candidata a fuente técnica (ej. libro de ingeniería de software o
     documentación oficial de Java EE/Jakarta EE).
   - **Arquitectura Limpia (Clean Architecture)** — mencionada varias veces como principio de
     diseño general. Robert C. Martin es el autor de referencia habitual para esto; no se agregó
     ninguna cita porque **no se debe inventar una referencia sin que Xavier confirme que
     efectivamente se basó en esa fuente** (o en documentación equivalente).
   - **APIs REST** — mencionado como concepto/estándar, no solo como práctica propia.
   - **Microservicios** como patrón arquitectónico general.
3. **Capitulo2.tex** — Kaplan2009 ("Ingeniería de requisitos") está en el `.bib` pero no citada;
   probablemente estaba pensada para la sección "Análisis de requerimientos y diseño inicial de
   base de datos" y se quedó sin conectar.

## Regla seguida en este diagnóstico

No se propuso, buscó ni redactó ninguna referencia bibliográfica nueva, ni se inventó ningún DOI,
autor o libro. Esto es solo un mapa de "dónde probablemente hace falta una fuente" para que,
cuando se entre a la fase de edición, Xavier decida qué fuentes reales usar (libros de su carrera,
documentación oficial de Microsoft/.NET, el propio "Clean Architecture" de Robert C. Martin si
aplica, etc.) y se agreguen citando correctamente en formato IEEE (que es el estilo ya configurado:
`\bibliographystyle{ieeetr}`).

## Formato

Las 2 entradas `@misc` usan `howpublished = {\url{...}}` y `note = {Accedido: ...}` — formato
razonable para fuentes web en estilo IEEE. Sin duplicados. Sin problemas de formato evidentes en
las 3 entradas existentes.
