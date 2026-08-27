# PROJECT_CONTEXT — Reporte Técnico de Investigación (Memoria de Experiencia Profesional)

## Qué es

Documento de titulación de **Xavier Eduardo Antonio Sánchez**, matrícula 185280, para obtener el
título de **Ingeniero en Sistemas Computacionales** en la **Universidad Autónoma de Ciudad Juárez
(UACJ), Instituto de Ingeniería y Tecnología**. Modalidad: memoria de experiencia profesional
(no tesis de investigación tradicional) — Seminario de Titulación de Sistemas Computacionales II.

- Director de tesis: M. en C. Jose Fernando Estrada Saldaña (GitHub: `estradafernando`, correo
  institucional `festrada@uacj.mx`, cargo "Profesor-Investigador IIT").
- Titular de Seminario de Titulación II: M.S.I. Cynthia Vanessa Esquivel Rivera.
- Sinodales A/B/C: aún son placeholders genéricos ("Nombre del Sinodal A/B/C", "Dr.") en `tesis.tex` — no se han definido los sinodales reales todavía.

## Repositorio

`C:\Proyects\ReporteTecnicoDeInvestigacion\rti.seminario.experiencia` — repo git con remoto en
GitHub: `https://github.com/Xavi-Eduardo/rti.seminario.experiencia.git`.

**IMPORTANTE — revisar visibilidad del repo en GitHub.** Ver ACADEMIC_DIAGNOSIS.md, sección de
privacidad: hay datos personales (teléfono, correo personal, domicilio del alumno, correos/teléfonos
de referencias laborales) subidos y "pusheados" a `origin` dentro de `_analisis_texto/`.

Rama actual de trabajo: `Correccion-redaccion-cap-1-y-2` (igual a `Development` y a `origin/HEAD`
en este momento). Rama `main` existe pero está desactualizada. Ver DOCUMENT_STRUCTURE.md para el
árbol de archivos y PROFESSOR_FEEDBACK.md para la rama `origin/Observaciones-06-03`, que contiene
retroalimentación real del director **nunca fusionada**.

## Las dos experiencias profesionales documentadas

### 1. BeGlobal Technology — enero 2024 a enero 2025
- Empresa de desarrollo web para micro/pequeñas/medianas empresas y negocios locales en Cd. Juárez.
- Rol: Desarrollador Jr. Desarrollo de una aplicación web desde cero para digitalizar auditorías
  internas industriales (antes en papel/manual).
- Stack: HTML/CSS/JavaScript (frontend, incluyendo adaptación de un template tipo dashboard),
  Java + NetBeans + patrón MVC + JSP + Servlets (backend), MySQL + MySQL Workbench (datos),
  Apache + Tomcat (despliegue).
- Referencia/jefe: Ing. Alejandro Sariñana, Senior Software Engineer.
- Evidencia disponible: carta laboral, carta de experiencia profesional (escrita por el propio
  Xavier), informe de actividades (escrito por Alejandro Sariñana), CV — todo transcrito en
  `_analisis_texto/`.

### 2. Multicom Comercio / proyecto "Wali Fintech" — enero 2025 a la fecha
- Multicom Comercio es la empresa; "Red Total Pago Sin Límite" aparece en el CV como una marca/
  producto de Multicom ("Multicom | Red Total Pago sin Limite"), **no como una empresa aparte**.
  El texto actual del RTI la trata como si fueran dos entidades en colaboración — revisar
  framing (ver ACADEMIC_DIAGNOSIS.md).
- El proyecto real se llama **"Wali Fintech"** (cuentas de crédito/débito, transacciones) — este
  nombre **no aparece en ningún capítulo del documento actual**. Puede ser una omisión válida por
  confidencialidad, o un descuido — hay que preguntarle a Xavier.
- Rol: Desarrollador Jr., equipo de Backend, bajo arquitectura de microservicios (Clients, Wallet,
  Auth, Access) con Arquitectura Limpia.
- Stack evidenciado (mucho más amplio que lo que hoy aparece en el documento): C#, .NET
  (6 → 10), Entity Framework, LINQ, Dapper, AWS RDS (MySQL Aurora), xUnit, Postman, Swagger,
  Git/GitHub/GitHub Desktop, Pull Requests, JIRA (asignación de tareas), SonarAnalyzer/StyleCop
  (calidad de código), Serilog, **Docker y Docker Compose**, **MongoDB Atlas / MongoDB Compass**
  (microservicio Access), **AWS CDK, API Gateway, Route53, AppRunner, Cognito** (infraestructura).
- Referencia/jefe: Ing. Esteban Sosa Mendoza (Multicom) / Esteban Sosa (CV, como "Senior Cloud
  Engineer").
- Nota de inconsistencia en la evidencia misma (no es culpa del documento, pero conviene saberlo):
  los correos de las referencias difieren entre la carta y el CV
  (`alejandro.sarinana@beglobaltechnology.com` vs `alejandro.sarinana@bsscomputing.com`;
  `esosa@m3rcurio.com` vs `esteban.sosa@gainwelltechnologies.com`). Podría deberse a cambios de
  empleador de las referencias con el tiempo — no necesariamente un error del alumno.

## Cómo se compila

XeLaTeX vía VS Code + LaTeX Workshop, con MiKTeX instalado en
`C:\Users\zemog\AppData\Local\Programs\MiKTeX\`. Configuración fijada en
`.vscode/settings.json` (rutas absolutas a los ejecutables + `rootFile.path` fijo a
`RTIExperienciaProfesional2026/tesis.tex`) — ver sesión anterior / LATEX_DIAGNOSIS.md. **Compila
correctamente hoy** (36 páginas, sin errores fatales).

## Estado general (resumen de una línea por elemento)

- **Compilación LaTeX:** funcional, sin errores. Ver LATEX_DIAGNOSIS.md.
- **Retroalimentación del profesor:** existe, es concreta (16 puntos), y está 100% sin resolver
  porque quedó en una rama huérfana. Ver PROFESSOR_FEEDBACK.md.
- **Contenido académico:** Introducción + Capítulos 1-3 completos y coherentes en tono; Capítulos
  4 y 5 (plantillas originales de "Resultados" y "Conclusiones") existen como archivos huérfanos,
  no incluidos, con texto de plantilla sin rellenar. Ver DOCUMENT_STRUCTURE.md y ACADEMIC_DIAGNOSIS.md.
- **Bibliografía:** insuficiente (2 fuentes web usadas), señalado explícitamente por el profesor.
  Ver BIBLIOGRAPHY_AUDIT.md.
- **Evidencia:** existe y es rica (cartas, informes, CV) en `_analisis_texto/`, pero el documento
  actual la subutiliza — hay tecnologías bien documentadas (Docker, MongoDB, AWS CDK/Cognito/
  Route53/AppRunner, JIRA, SonarAnalyzer) que no aparecen en el texto. Ver ACADEMIC_DIAGNOSIS.md.
- **Privacidad:** datos personales sensibles ya están en el repo remoto de GitHub. Revisar
  visibilidad del repo con prioridad alta.

## Reglas de redacción / restricciones ya decididas (por el propio Xavier, en su prompt de la sesión 2)

- No modificar archivos académicos sin aprobación explícita previa.
- No inventar tecnologías, métricas, responsabilidades, resultados, bibliografía ni comentarios
  del profesor. Ante falta de evidencia, escribir explícitamente "no existe evidencia suficiente".
- Voz académica, formal, clara, natural — evitar relleno "generado por IA" (genérico, repetitivo,
  sobre-formal, vago).
- Git es el mecanismo de control de cambios: cambios pequeños, compilar, revisar PDF, revisar
  `git diff`, y Xavier decide cuándo hacer commit/push. Nunca commitear/pushear automáticamente.
- No cambiar el formato institucional (`tesis.cls`) sin justificar que es una decisión del autor y
  no un requisito de la plantilla.

## Próximos pasos sugeridos

Ver PENDING_WORK.md para el plan de fases.
