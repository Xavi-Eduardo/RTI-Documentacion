# CLAUDE.md — Reglas permanentes del proyecto RTI

Este archivo define cómo trabajar en el proyecto del Reporte Técnico de Investigación (RTI) de
Xavier Eduardo Antonio Sánchez, en cualquier sesión futura. Léelo primero, siempre.

## Los dos repositorios

### Repositorio académico — fuente de verdad

`C:\Proyects\ReporteTecnicoDeInvestigacion\rti.seminario.experiencia\RTIExperienciaProfesional2026`

Contiene el documento académico real: `.tex`, `.bib`, imágenes, anexos, cartas, configuración
LaTeX, PDF generado. **Es la única fuente de verdad sobre el contenido actual del documento.**
Cualquier tarea de revisar, corregir, analizar un capítulo, atender comentarios del asesor,
revisar bibliografía/resultados/conclusiones, o modificar contenido académico, trabaja sobre este
repositorio.

### Repositorio documental — contexto y memoria del proyecto

`C:\Proyects\RTI-Docs\RTI-Documentacion`

Contiene todo el análisis, diagnóstico, correcciones propuestas, decisiones, seguimiento y
documentación auxiliar generada durante el trabajo con el RTI. **No es el documento académico —
informa el trabajo, pero nunca se copia automáticamente al RTI sin verificación y autorización.**

## Estructura de `RTI-Documentacion`

```text
RTI-Documentacion/
├── CLAUDE.md                          ← este archivo
├── README.md                          ← índice rápido
├── contexto/
│   ├── PROJECT_CONTEXT.md             ← qué es el proyecto, empresas, evidencia, reglas
│   ├── DOCUMENT_STRUCTURE.md          ← árbol real del proyecto LaTeX
│   ├── PENDING_WORK.md                ← plan de fases completo
│   └── CURRENT_STATUS.md              ← estado actual, léelo primero en cada sesión nueva
├── correcciones/
│   ├── PROFESSOR_FEEDBACK.md          ← los 16 comentarios del asesor, origen y hallazgo en git
│   └── correcciones.md                ← guía detallada de corrección por comentario (C-001..C-016)
├── analisis/
│   ├── ACADEMIC_DIAGNOSIS.md          ← diagnóstico académico completo (P0-P3)
│   └── LATEX_DIAGNOSIS.md             ← estado de compilación LaTeX
├── bibliografia/
│   └── BIBLIOGRAPHY_AUDIT.md          ← estado de referencias.bib
└── seguimiento/
    └── CHANGELOG.md                   ← bitácora sesión por sesión (antes SESSION_LOG.md)
```

No crear carpetas nuevas para un solo archivo. Si en el futuro se acumulan decisiones formales que
lo justifiquen, se puede crear `decisiones/` — no se creó todavía porque estaría vacía.

## Flujo de trabajo obligatorio

```text
Contexto → Fuente → Análisis → Propuesta → Aprobación → Cambio → Validación → Documentación
```

- **Contexto:** `RTI-Documentacion` (empezar aquí siempre, sobre todo `contexto/CURRENT_STATUS.md`).
- **Fuente:** `RTIExperienciaProfesional2026` (consultar solo lo necesario para la tarea actual).
- **Análisis/seguimiento:** se registra en `RTI-Documentacion`.
- **Cambios académicos:** se aplican en `RTIExperienciaProfesional2026`, nunca en `RTI-Documentacion`.

### Orden de lectura eficiente (evitar reanalizar todo en cada sesión)

```text
1. Consultar RTI-Documentacion (empezar por contexto/CURRENT_STATUS.md)
2. Recuperar contexto existente (correcciones/, analisis/, etc. según la tarea)
3. Identificar qué necesita la tarea actual
4. Consultar únicamente los archivos/secciones necesarias de RTIExperienciaProfesional2026
5. Realizar análisis o trabajo
6. Actualizar RTI-Documentacion
```

Solo repetir una auditoría completa del documento académico cuando el usuario lo pida
explícitamente o exista una razón técnica clara (ej. sospecha fundada de que el contexto está
desactualizado).

### Si hay contradicción entre `RTI-Documentacion` y el repositorio académico

El repositorio académico manda siempre. Si algo no cuadra:
1. Verificar el archivo fuente actual en `RTIExperienciaProfesional2026`.
2. Determinar qué cambió desde el último análisis.
3. Actualizar el documento de contexto correspondiente en `RTI-Documentacion`.
4. No conservar información obsoleta como si siguiera vigente.

### Flujo específico para aplicar una corrección de LaTeX

```text
1. Recuperar contexto de RTI-Documentacion (correcciones/correcciones.md, estado del ítem)
2. Revisar la sección específica del .tex afectada (no todo el documento)
3. Aplicar el cambio (con autorización explícita del usuario)
4. Compilar LaTeX
5. Verificar errores/warnings relevantes
6. Revisar git diff en RTIExperienciaProfesional2026
7. Confirmar que el comentario del asesor quedó atendido
8. Actualizar el estado de esa corrección en RTI-Documentacion (correcciones.md + CURRENT_STATUS.md)
```

## Estados de corrección (usar siempre estos, consistentes)

- Pendiente
- En análisis
- Requiere información del autor
- Requiere fuente
- Requiere decisión del autor
- Lista para aplicar
- Aplicada
- Verificada (solo después de comprobar que el cambio quedó correctamente reflejado y compilado)

## Git — reglas para ambos repositorios

- Son repositorios independientes. Nunca mezclar commits entre el documento académico y la
  documentación auxiliar.
- Comandos de solo lectura (`status`, `log`, `diff`, `show`, `branch`, `ls-files`, `grep`) se
  pueden usar libremente para entender contexto.
- **Nunca** ejecutar `commit`, `push`, `reset`, `rebase`, `clean` ni ningún comando que altere
  historial o estado, sin que el usuario lo pida explícitamente en ese momento.
- `git.exe` no está en el PATH de este entorno; usar la ruta absoluta:
  `C:\Users\zemog\AppData\Local\GitHubDesktop\app-3.6.4\resources\app\git\cmd\git.exe`.

## Reglas académicas (no negociables)

- No inventar actividades, responsabilidades, resultados, métricas, tecnologías, fechas,
  comentarios del asesor ni bibliografía.
- No atribuir trabajo de equipo como trabajo individual.
- Ante falta de información, preguntar al usuario — nunca completar por suposición.
- Toda propuesta de texto debe: mantener el estilo académico actual, ser coherente con el resto
  del documento, usar solo información respaldada, evitar exageraciones.
- No copiar contenido de `RTI-Documentacion` al RTI académico automáticamente — siempre verificar
  que sea correcto y que el usuario haya autorizado esa corrección específica primero.
- No cambiar el formato institucional (`tesis.cls`) sin justificar que es decisión del autor y no
  requisito de la plantilla.

## Referencia rápida de compilación LaTeX

- Motor: XeLaTeX vía MiKTeX (`C:\Users\zemog\AppData\Local\Programs\MiKTeX\miktex\bin\x64\`).
- Recipe: `xelatex → bibtex → xelatex → xelatex`, configurado en
  `RTIExperienciaProfesional2026\.vscode\settings.json` (o el `.vscode` del workspace que se use
  para abrir esa carpeta) con rutas absolutas y `rootFile.path` fijo.
- Si el instalador automático de paquetes de MiKTeX falla con "Timeout was reached", instalar
  manualmente con: `mpm.exe --repository="https://mirrors.rit.edu/CTAN/systems/win32/miktex/tm/packages/" --install=<paquete>`.
- Detalle completo: `analisis/LATEX_DIAGNOSIS.md`.
