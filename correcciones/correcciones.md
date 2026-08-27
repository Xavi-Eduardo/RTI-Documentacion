# Correcciones del asesor

Actualizado: sesión del 2026-08-27 (tercera pasada — integradas las respuestas de Xavier a las 8
preguntas pendientes, más investigación bibliográfica/técnica verificada en fuentes oficiales para
C-011, C-012 y C-015).

Este documento reemplaza y actualiza la versión anterior. No se perdió nada del análisis previo.

**Ningún `.tex`/`.bib` fue modificado. Ningún commit ni push se realizó.**

## Resumen

```text
Comentarios encontrados: 16
Listos para aplicar: 13   (C-001, C-002, C-003, C-004, C-005, C-006, C-008, C-009, C-010, C-011, C-012, C-014, C-016)
Parcialmente pendientes: 1   (C-007 — pendiente del diagrama que Xavier está elaborando)
Diferidos a fase posterior (decisión de Xavier): 1   (C-013 — AE/OE)
Listo para revisión de fuentes (no aplicado a texto/bib todavía): 1   (C-015 — bibliografía técnica)
```

## Tabla resumen

| ID | Sección | Comentario resumido | Estado |
|---|---|---|---|
| C-001 | Resumen | "Palabras claves"→"clave", "aplicacion"→"aplicación" | LISTO PARA APLICAR |
| C-002 | Introducción | Quitar frase "Con el fin de mantener un orden lógico..." | LISTO PARA APLICAR |
| C-003 | Introducción | Encabezado de página "Índice de figuras" desactualizado | LISTO PARA APLICAR |
| C-004 | Introducción | Quitar frase redundante sobre agradecimientos/dedicatoria | LISTO PARA APLICAR |
| C-005 | 1.1 Multicom Comercio | "¿En qué te basas...? Se necesitan evidencias" | LISTO PARA APLICAR |
| C-006 | 1.6 Área de sistemas | "una organización"→"la organización" | LISTO PARA APLICAR |
| C-007 | Cap. 2 (inicio) | Sugerencia de gráfico/diagrama actividades-herramientas | PENDIENTE DE DIAGRAMA |
| C-008 | 2.2.1 | "¿Cómo se implementó" la asignación automática de responsables? | LISTO PARA APLICAR (verificado en código) |
| C-009 | 2.2.4 | JSON/AJAX/jQuery sin justificar | LISTO PARA APLICAR (verificado en código) |
| C-010 | 2.4 Segundo proyecto | Falta ejemplo concreto | LISTO PARA APLICAR |
| C-011 | 2.4.6 Migración .NET | Por qué .NET 10, ¿estable? | LISTO PARA APLICAR / FUENTE VERIFICADA |
| C-012 | 2.4.7 AWS Lambda | Misma pregunta + falta evidencia de que ocurrió | LISTO PARA APLICAR / VERSIÓN VERIFICADA |
| C-013 | 3 (intro capítulo) | Explicar AE/OE | PENDIENTE PARA FASE POSTERIOR |
| C-014 | 3.2 Conclusiones | Mayúsculas/acento "Ingeniería en Sistemas Computacionales" | LISTO PARA APLICAR |
| C-015 | Bibliografía | Falta bibliografía técnica | LISTO PARA REVISIÓN DE FUENTES |
| C-016 | `tesis.cls` (carta institucional) | Incluir título M. en C. del director | LISTO PARA APLICAR |

---

## C-001 — Resumen: "Palabras clave" y acentuación

### Comentario del asesor
No hay comentario de texto — el asesor corrigió directamente con marcas de control de cambios.

### Texto actual relacionado
```latex
\textbf{Palabras clave\deleted[id=TUT]{s}}: memoria profesional, desarrollo de software, \replaced[id=TUT]{aplicación}{aplicacion} web, auditorias, APIs REST, microservicios, pruebas unitarias, AWS
```
Ubicación: `Resumen.tex`, línea 17.

### Qué está solicitando el asesor
Corregir "Palabras claves" → "Palabras clave" (singular correcto) y "aplicacion" → "aplicación"
(acento faltante).

### Solución
Aceptar las dos marcas de cambio y limpiar el texto. De paso corrijo "auditorias" → "auditorías"
(mismo tipo de error, en la misma línea, no señalado explícitamente por el asesor pero evidente).

### Texto sugerido en LaTeX
```latex
\textbf{Palabras clave}: memoria profesional, desarrollo de software, aplicación web, auditorías, APIs REST, microservicios, pruebas unitarias, AWS
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-002 — Introducción: quitar frase sobre organización en capítulos

### Comentario del asesor
```latex
\comment[id=TUT]{ Yo quitaría el texto porque no aporta información adicional}
```
(sobre el fragmento marcado `\deleted` inmediatamente antes)

### Texto actual relacionado
```latex
\deleted[id=TUT]{Con el fin de mantener un orden lógico, el documento se organiza en capítulos.} \comment[id=TUT]{ Yo quitaría el texto porque no aporta información adicional} En el Capítulo 1 se presenta el entorno laboral, ofreciendo el contexto general de las organizaciones
  involucradas, así como información de referencia institucional y una descripción del área de trabajo y su dinámica.
```
Ubicación: `Introduccion.tex`, línea 18.

### Qué está solicitando el asesor
Eliminar la frase de relleno antes de entrar directo a describir el contenido de cada capítulo.

### Solución
Aceptar la eliminación ya marcada por el asesor.

### Texto sugerido en LaTeX
```latex
En el Capítulo 1 se presenta el entorno laboral, ofreciendo el contexto general de las organizaciones
  involucradas, así como información de referencia institucional y una descripción del área de trabajo y su dinámica.
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-003 — Introducción: encabezado de página desactualizado

### Comentario del asesor
```latex
\comment[id=TUT]{Ya no estás en ÍNDICE DE FIGURAS, así que hay que cambiarlo por introducción.}
```

### Texto actual relacionado
No es un problema de prosa — es el encabezado de página (running head) que no se actualiza.
`Introduccion.tex` usa `\chapter*{Introducción}` (capítulo sin numerar), y `\chapter*` no llama a
`\@mkboth`, por lo que el encabezado sigue mostrando el último título que sí lo actualizó
(`\listoffigures`).

### Qué está solicitando el asesor
Que el encabezado de las páginas de la Introducción diga "Introducción" y no "Índice de figuras".

### Solución
Agregar manualmente la actualización de marca justo después del inicio del capítulo.

### Texto sugerido en LaTeX
```latex
\chapter*{Introducción}\label{introduccion}
\markboth{}{Introducción}
```
(agregar la segunda línea inmediatamente después de la primera, que ya existe en `Introduccion.tex` línea 2)

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-004 — Introducción: quitar frase redundante sobre agradecimientos/dedicatoria

### Comentario del asesor
Sin comentario de texto adicional — marca `\deleted` directa.

### Texto actual relacionado
```latex
De manera complementaria, \deleted[id=TUT]{se incluyen apartados de agradecimientos y dedicatoria, en los que se reconoce el apoyo brindado por personas e instituciones que contribuyeron al desarrollo
  del presente trabajo.} Finalmente, se anexan las cartas laborales como evidencia documental que valida el periodo de colaboración y las funciones desempeñadas, respaldando la
  información expuesta en la memoria.
```
Ubicación: `Introduccion.tex`, línea 24.

### Qué está solicitando el asesor
Quitar información redundante (el lector ya vio agradecimientos y dedicatoria antes de la
introducción).

### Solución
Aceptar la eliminación y ajustar el conector para que la oración fluya bien sin la frase quitada.

### Texto sugerido en LaTeX
```latex
De manera complementaria, finalmente se anexan las cartas laborales como evidencia documental que valida el periodo de colaboración y las funciones desempeñadas, respaldando la
  información expuesta en la memoria.
```

### Referencia necesaria
No.

### Respuesta del autor
Confirmado: ajuste de texto (no el resultado literal del `\deleted` a secas). Se conserva la
propuesta tal como estaba.

### Estado
**LISTO PARA APLICAR.**

---

## C-005 — Capítulo 1: afirmación sin sustento sobre Multicom

### Comentario del asesor
```latex
\comment[id=TUT]{En que te basas para dar esa afirmación, se necesitan evidencias}
```

### Texto actual relacionado
```latex
La organización cuenta con una plataforma robusta y estable,\comment[id=TUT]{En que te basas para dar esa afirmación, se necesitan evidencias} orientada a la venta de productos de prepago, tiempo aire electrónico, pago de servicios y compra de pines electrónicos.
Esta plataforma ha sido desarrollada y fortalecida a lo largo de los años, permitiendo a la empresa adaptarse a las necesidades de un mercado cambiante y ofrecer soluciones
tecnológicas confiables a sus clientes.\cite{MulticomSobreMulticomServicios}
```
Ubicación: `Capitulo1.tex`, línea 28. No aplica código de `tqaAuditorias` (es sobre Multicom, no
BeGlobal); tampoco hay repositorio de Multicom/Wali Fintech disponible para verificar en código.

### Qué está solicitando el asesor
Que la afirmación "robusta y estable" tenga respaldo — ya existe una cita en el documento, pero
respalda la oración siguiente, no esta afirmación específica.

### Respuesta del autor
Confirmado: "robusta y estable" era una apreciación personal, sin dato concreto que la sustente.
Instrucción: eliminar/suavizar ese tipo de afirmaciones en vez de presentarlas como hecho
institucional.

### Solución
Se elimina el adjetivo subjetivo "robusta y estable" (no se reemplaza por ninguna otra
caracterización sin sustento, como pidió Xavier). Queda solo la descripción factual de lo que hace
la plataforma, respaldada por la cita institucional que ya existía.

### Texto sugerido en LaTeX
```latex
La organización cuenta con una plataforma orientada a la venta de productos de prepago, tiempo aire electrónico, pago de servicios y compra de pines electrónicos.\cite{MulticomSobreMulticomServicios}
Esta plataforma ha sido desarrollada y fortalecida a lo largo de los años, permitiendo a la empresa adaptarse a las necesidades de un mercado cambiante y ofrecer soluciones
tecnológicas confiables a sus clientes.\cite{MulticomSobreMulticomServicios}
```
(la única diferencia respecto al texto actual es la eliminación de "robusta y estable," y se
agrega la cita también a la primera oración, ya que ambas describen lo mismo respaldado por la
misma fuente)

### Referencia necesaria
No se agrega ninguna nueva — se reutiliza `MulticomSobreMulticomServicios`, ya existente.

### Estado
**LISTO PARA APLICAR.**

---

## C-006 — Capítulo 1: "una organización" → "la organización"

### Comentario del asesor
Sin comentario de texto — marca `\replaced` directa.

### Texto actual relacionado
```latex
tiene como propósito crear, mantener y mejorar soluciones tecnológicas que apoyen los procesos internos o externos de \replaced[id=TUT]{la organización}{una organización}. En este contexto, el trabajo realizado no se
```
Ubicación: `Capitulo1.tex`, línea 102.

### Qué está solicitando el asesor
Corrección gramatical: referencia específica ("la organización"), no genérica ("una organización").

### Solución
Aceptar el reemplazo ya marcado.

### Texto sugerido en LaTeX
```latex
tiene como propósito crear, mantener y mejorar soluciones tecnológicas que apoyen los procesos internos o externos de la organización. En este contexto, el trabajo realizado no se
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-007 — Capítulo 2: sugerencia de gráfico/diagrama

### Comentario del asesor
```latex
\added[id=TUT]{Yo te sugiero incluir algún tipo de gráfico o diagrama que muestre la relación entre las actividades realizadas, las herramientas utilizadas y los aprendizajes adquiridos. Esto puede ayudar a visualizar mejor la experiencia laboral y su impacto en tu formación profesional.}
```
**Atención:** está marcado como `\added` (texto agregado) — si se acepta el cambio sin más, el
propio texto de la sugerencia del asesor quedaría impreso como si fuera prosa tuya. Hay que
**eliminar** este bloque una vez atendida la sugerencia, no aceptarlo como contenido.

### Texto actual relacionado
Ubicación: `Capitulo2.tex`, línea 12 (antes de `\section{Contexto laboral}`).

### Qué está solicitando el asesor
Un elemento visual (tabla, diagrama o línea de tiempo) que resuma la relación entre actividades,
herramientas y aprendizajes de ambas etapas.

### Respuesta del autor
Xavier está elaborando un diagrama que se incorporará como imagen en este apartado. Por lo tanto:
este comentario se deja **parcialmente resuelto** — no se marca como completamente atendido hasta
que la imagen exista y se incorpore al `.tex`. No se inventa el contenido del diagrama.

### Solución
Mientras se genera la imagen, se puede dejar preparado el texto que la introduce y el que la
comenta después (esto sí se puede redactar ya, sin conocer el contenido exacto del diagrama), y un
`\begin{figure}` de marcador de posición con la inclusión de la imagen comentada, para que quede
listo para activar en cuanto Xavier entregue el archivo.

### Texto sugerido en LaTeX
Sustituye el bloque `\added[id=TUT]{...}` completo por:
```latex
Con el fin de visualizar de manera más clara la relación entre las actividades realizadas, las herramientas utilizadas y los aprendizajes adquiridos en ambas etapas, se presenta a continuación un diagrama resumen (Figura~\ref{fig:resumen-actividades}).

\begin{figure}[H]
    \centering
    % TODO(C-007): agregar \includegraphics una vez que exista el archivo del diagrama
    \caption{Relación entre actividades, herramientas y aprendizajes adquiridos.}
    \label{fig:resumen-actividades}
\end{figure}

Como se observa en la figura anterior, cada actividad estuvo asociada a herramientas específicas que, en conjunto, permitieron consolidar los aprendizajes descritos a lo largo de este capítulo.
```
El `\caption` y el texto introductorio/posterior son una propuesta editable — ajústalos cuando
tengas el diagrama definitivo si el enfoque real del diagrama termina siendo distinto.

### Referencia necesaria
No.

### Estado
**PENDIENTE DE DIAGRAMA** (texto de acompañamiento listo; falta la imagen para completar y para
poder marcar el comentario como atendido).

---

## C-008 — Capítulo 2: cómo se implementó la asignación automática de responsables

### Comentario del asesor
```latex
\comment[id=TUT]{¿Cómo se implementó esta funcionalidad?}
```

### Texto actual relacionado
```latex
Adicionalmente, se buscó incorporar una mejora orientada a la eficiencia operativa: que el sistema pudiera apoyar en la asignación automática de responsables \comment[id=TUT]{¿Cómo se implementó esta funcionalidad?} para realizar auditorías,
  con el objetivo de distribuir la actividad de forma más organizada y reducir la coordinación manual.
```
Ubicación: `Capitulo2.tex`, línea 49.

### Qué está solicitando el asesor
El mecanismo real de la asignación automática: ¿qué criterio usa el sistema para decidir a quién
asignar?

### Verificación en código (`tqaAuditorias`)
Se revisó directamente el código fuente del proyecto. Hallazgos concretos:

- **Sí se diseñó e implementó** una función de asignación automática por departamento:
  `AuditAssigment.setUsersToAudit(departmentId, auditId, createUserId)` en
  `src/main/java/tqa/models/AuditAssigment.java` (líneas 167-196). Consulta todos los usuarios de
  un departamento (`User.getUsersByDepartmentId(departmentId)`) y crea automáticamente un registro
  de asignación (`audit_assigment`) por cada uno.
- **Pero su invocación quedó sin activar.** Los dos únicos puntos donde se llamaría a esa función
  —justo al crear una auditoría— están comentados:
  - `src/main/java/tqa/servlets/Audits.java`, línea 98:
    `//AuditAssigment.setUsersToAudit(departmentId, audit.getAuditId(), user.getUserId() );`
  - `src/main/java/tqa/servlets/AuditDepartments.java`, línea 70 (dentro de un bloque `case "add"`
    mayormente comentado también).
- **Lo que sí funcionaba y se usaba en producción** era la asignación manual: el servlet
  `AuditAssigments.java` (acción `checkBox` en `doPost`) permite marcar/desmarcar usuarios
  individuales como responsables de una auditoría, uno por uno, desde una lista de checkboxes
  (`src/main/webapp/js/addAudits.js`, función `selectUser()`, líneas 508-522 — hace
  `$.ajax POST` a `AuditAssigments` con `actionUser: "checkBox"` por cada clic).

Es decir: existió diseño, modelo de datos y una función completa para automatizar la asignación
por departamento, pero nunca se integró al flujo real; la asignación de responsables durante el
periodo de participación se hacía manualmente, usuario por usuario.

### Solución
Corregir el texto para reflejar exactamente esto: se planteó y se llegó a programar el mecanismo
automático, pero no se integró al flujo de creación de auditorías, por lo que operativamente la
asignación fue manual.

### Texto sugerido en LaTeX
```latex
Adicionalmente, se diseñó una mejora orientada a la eficiencia operativa: que el sistema pudiera asignar automáticamente a los usuarios de un departamento como responsables de una auditoría al momento de crearla, con el objetivo de distribuir la actividad de forma más organizada y reducir la coordinación manual. Esta lógica se implementó a nivel de modelo, mediante un método que consulta a los usuarios pertenecientes al departamento seleccionado y genera un registro de asignación por cada uno; sin embargo, su invocación no llegó a integrarse en el flujo de creación de auditorías durante el periodo descrito en esta memoria, por lo que la asignación de responsables se realizaba de forma manual, mediante una interfaz que permitía marcar individualmente a cada usuario como responsable de una auditoría específica.
```

### Referencia necesaria
No — es experiencia propia, verificada directamente en el código del proyecto.

### Impacto en otras secciones
Capítulo 3 (Resultados) dice "el planteamiento de una asignación automatizada de responsables
aportó una base para distribuir actividades..." — conviene revisar esa frase para que sea
consistente con "se planteó y se diseñó, pero no se integró al flujo" en vez de sugerir que quedó
operando.

### Estado
**LISTO PARA APLICAR** (verificado en código, no requiere información adicional del autor).

---

## C-009 — Capítulo 2: justificar JSON, AJAX y jQuery

### Comentario del asesor
```latex
\comment[id=TUT]{Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron}
```

### Texto actual relacionado
```latex
En la práctica, se trabajó con operaciones tipo CRUD para administrar información base del sistema (catálogos y configuraciones).
  Para la interacción con la interfaz se utilizaron JSP apoyadas por JavaScript y librerías como jQuery, permitiendo enviar solicitudes asíncronas (AJAX) y actualizar la
  experiencia de usuario sin recargar páginas completas en cada acción. Cuando fue necesario, las respuestas se entregaban en formato JSON para facilitar su consumo desde el frontend,
  manteniendo consistencia en la comunicación entre capas. \comment[id=TUT]{Se menciona JSON, AJAX y jQuery pero no explica porque se seleccionaron}
```
Ubicación: `Capitulo2.tex`, línea 92 (subsección "Implementación de reglas de negocio y módulos
principales", dentro de 2.2.4).

### Qué está solicitando el asesor
Por qué se eligió jQuery (en vez de JavaScript puro), por qué AJAX (en vez de recarga completa) y
por qué JSON (en vez de otro formato).

### Verificación en código (`tqaAuditorias`)
Confirmado con evidencia directa:

- **jQuery venía integrado en el template de dashboard adoptado**, no fue una elección aislada:
  bajo `src/main/webapp/assets/lib/` está el conjunto completo de plugins basados en jQuery del
  template (`select2`, `parsley`, `summernote`, `sweetalert2`, `datatables`, `jquery.fullcalendar`,
  etc.) — coincide con lo que el propio Capítulo 2 ya dice sobre integrar "un template base con
  estilo tipo dashboard" (sección 2.2.3).
- **AJAX se usó sistemáticamente para no recargar la página** en operaciones de captura/consulta:
  patrón `$.ajax({type: "GET"/"POST", url: "<Servlet>", data: {...}, success: function(data){...}})`
  repetido en `src/main/webapp/js/addAudits.js` (altas/bajas de preguntas, usuarios, departamentos,
  áreas y asignaciones — ej. líneas 82-91, 251-282, 318-348, 483-521) y en otros JS del proyecto
  (`responseAudits.js`, `users.js`).
- **JSON se usó como formato de intercambio en ambos sentidos**: jQuery serializa automáticamente
  los objetos JS (`jsonGetAudit`, `jsonPostAuditAssigmentByUser`, etc.) al enviar la solicitud, y
  el backend responde en JSON explícitamente vía `super.writeJson(...)` (visible en
  `AuditAssigments.java`, líneas 46, 49, 53, 98) — un helper de la clase base `BssServlet`.

### Solución
Agregar una explicación breve, ligada a la necesidad real (evitar recargar la página en formularios
de captura de auditorías/preguntas/asignaciones) y al origen de jQuery (ya integrado en el template
adoptado), sin entrar a nivel de código.

### Texto sugerido en LaTeX
```latex
Para la interacción con la interfaz se utilizaron JSP apoyadas por JavaScript y librerías como jQuery —ya integradas en el template de dashboard adoptado—, lo que permitió enviar solicitudes asíncronas (AJAX) hacia los Servlets sin recargar la página completa en cada acción de captura o consulta (por ejemplo, al agregar preguntas, usuarios o asignaciones a una auditoría). Cuando fue necesario, las respuestas se entregaban en formato JSON, por ser un formato ligero y de fácil consumo desde JavaScript, manteniendo consistencia en la comunicación entre capas.
```

### Referencia necesaria
Opcional. La mayor parte del párrafo describe decisiones verificadas dentro del propio proyecto
(no requiere fuente). Si se quisiera respaldar la caracterización general de JSON como "formato
ligero", cabría una fuente técnica (ej. documentación oficial de JSON, `json.org`, o MDN) — no es
indispensable porque es una caracterización ampliamente aceptada y no controvertida, no una
afirmación institucional que necesite evidencia externa.

### Estado
**LISTO PARA APLICAR** (verificado en código, no requiere información adicional del autor).

---

## C-010 — Capítulo 2: ejemplo concreto en "Segundo proyecto"

### Comentario del asesor
```latex
\comment[id=TUT]{Valdría la pena poner un ejemplo concreto}
```

### Texto actual relacionado
```latex
El segundo proyecto corresponde al desarrollo y mantenimiento de una plataforma orientada a servicios digitales, construida bajo una arquitectura de microservicios.\comment[id=TUT]{Valdría la pena poner un ejemplo concreto} En este entorno se
  trabajaba con APIs REST, reglas de negocio distribuidas por servicio y persistencia de datos, por lo que era indispensable mantener consistencia en contratos, validaciones y manejo de
  errores para asegurar un funcionamiento estable.
```
Ubicación: `Capitulo2.tex`, línea 124. No aplica `tqaAuditorias` (es del proyecto de Multicom, sin
repositorio de código disponible para esta sesión).

### Qué está solicitando el asesor
Un ejemplo concreto de qué hace la plataforma o qué tipo de microservicio, en vez de la descripción
abstracta actual.

### Respuesta del autor
Confirmado: **no debe aparecer el nombre "Wali Fintech"** (confidencial). Sí se pueden mencionar
conceptos técnicos generales (arquitectura de microservicios, C#, .NET, Clean Architecture, APIs
REST, servicios backend, etc.), usando expresiones como "la plataforma", "el sistema", "la
solución backend", "los microservicios del proyecto" — sin identificadores internos.

### Solución
Se da un ejemplo concreto usando descripciones funcionales genéricas (qué hace un microservicio,
no cómo se llama), suficientes para mostrar profundidad técnica sin revelar el nombre del proyecto
ni identificadores internos (evito términos como "Wallet", "Auth", "Access", "Clients" tal cual
aparecen en el código/evidencia, y los reemplazo por su función).

### Texto sugerido en LaTeX
```latex
El segundo proyecto corresponde al desarrollo y mantenimiento de la solución backend de una plataforma orientada a servicios financieros, construida bajo una arquitectura de microservicios desarrollados en C\# y .NET, siguiendo principios de Arquitectura Limpia. Entre los microservicios del proyecto se encontraban componentes responsables, por ejemplo, de la gestión de clientes y del manejo de saldos y transacciones de los usuarios.\comment[id=XAV]{Verificar que esta descripción funcional no revele información confidencial adicional antes de aceptar.} En este entorno se
  trabajaba con APIs REST, reglas de negocio distribuidas por servicio y persistencia de datos, por lo que era indispensable mantener consistencia en contratos, validaciones y manejo de
  errores para asegurar un funcionamiento estable.
```
Dejé un `\comment[id=XAV]{...}` de precaución dentro del texto sugerido — bórralo si al leerlo
confirmas que no hay ningún detalle adicional que prefieras ocultar; lo incluyo porque la decisión
de qué tan específico ser es tuya, no mía, y prefiero que lo veas explícitamente antes de aceptar.

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR** (revisar el `\comment[id=XAV]` de precaución antes de aceptar definitivamente).

---

## C-011 — Capítulo 2: justificar la versión .NET 10

### Comentario del asesor
```latex
\comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}
```

### Texto actual relacionado
```latex
Dentro de las actividades del proyecto se participó en tareas de actualización tecnológica, enfocadas en migrar servicios desarrollados en .NET 6 hacia versiones más recientes
  como .NET 10. \comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}Esta actualización requirió identificar incompatibilidades, reemplazar funciones obsoletas y ajustar dependencias para mantener la correcta compilación y ejecución de
  los servicios.
```
Ubicación: `Capitulo2.tex`, línea 213-214. Proyecto de Multicom, sin repositorio de código
disponible.

### Qué está solicitando el asesor
Justificar por qué se migró específicamente hasta .NET 10 y no una versión LTS anterior, y si ya
es estable / si había una funcionalidad indispensable que la requiriera.

### Respuesta del autor
Xavier explicó que el pipeline usa GitHub Actions para compilar/validar antes de desplegar hacia
AWS App Runner, y que la migración se debió a que el entorno usado para proyectos .NET 6 llegó a
su fin de soporte/compatibilidad. Pidió verificar técnicamente antes de redactar, sin afirmar que
"GitHub Actions dejó de compilar .NET 6" si eso es impreciso.

### Verificación técnica (fuentes oficiales)
Se investigó y se confirma lo siguiente, con precisión sobre qué corresponde a cada causa:

1. **.NET 6 alcanzó su fin de soporte oficial el 12 de noviembre de 2024** (Microsoft, ciclo LTS de
   36 meses) — a partir de esa fecha ya no recibe parches de seguridad ni soporte técnico.
2. **No es GitHub Actions quien deja de "compilar" .NET 6** — `actions/setup-dotnet` puede instalar
   cualquier SDK, incluidos los ya sin soporte; esa no es la causa técnica real y no debe afirmarse
   así.
3. **La causa concreta ligada a AWS App Runner (donde se ejecutan los microservicios) sí es real y
   más específica de lo que Xavier recordaba:** App Runner únicamente ofreció **.NET 6** como
   runtime administrado (managed runtime) para despliegue desde código fuente, y AWS anunció el
   **fin de soporte de ese runtime administrado de .NET 6 a partir del 1 de diciembre de 2025**,
   sin planes de agregar versiones más recientes de .NET como runtime administrado. Es decir: el
   camino de despliegue basado en código fuente de App Runner queda limitado a .NET 6 y en vías de
   retirarse — la causa de fondo no es un límite de GitHub Actions, sino del propio servicio de
   despliegue en AWS combinado con el fin de soporte de Microsoft sobre .NET 6.
4. **.NET 10 es la versión LTS vigente más reciente** al momento de esta migración (lanzada
   noviembre de 2025, con soporte hasta noviembre de 2028) — es la elección lógica para no repetir
   pronto el mismo problema de fin de soporte.

### Solución
Reescribir el párrafo con la causa técnica verificada (fin de soporte de .NET 6 + límite del
runtime administrado de App Runner), no con una atribución imprecisa a GitHub Actions.

### Texto sugerido en LaTeX
```latex
Dentro de las actividades del proyecto se participó en tareas de actualización tecnológica, enfocadas en migrar servicios desarrollados en .NET 6 hacia .NET 10. Esta migración fue necesaria porque .NET 6 alcanzó su fin de soporte oficial en noviembre de 2024\cite{dotnet_support_policy}, dejando de recibir actualizaciones de seguridad, y porque AWS App Runner —el servicio donde se ejecutan los microservicios del proyecto— únicamente ofrecía a .NET 6 como runtime administrado, anunciando además el fin de soporte de dicho runtime sin planes de incorporar versiones más recientes de .NET\cite{aws_apprunner_dotnet_eos}. Por ello se optó por migrar directamente a .NET 10, la versión de soporte a largo plazo (LTS) más reciente disponible al momento de la actualización, aprovechando el flujo de integración continua configurado en GitHub Actions, que compila y valida la solución antes de continuar con el proceso de despliegue. Esta actualización requirió identificar incompatibilidades, reemplazar funciones obsoletas y ajustar dependencias para mantener la correcta compilación y ejecución de
  los servicios. También fue necesario revisar referencias a librerías y actualizar configuraciones para que el código se alineara con los cambios de la nueva versión.
```

### Referencia necesaria
Sí — ya verificadas, no inventadas. Ver entradas `.bib` propuestas en la sección de C-015 al final
de este documento (`dotnet_support_policy`, `aws_apprunner_dotnet_eos`).

### Estado
**LISTO PARA APLICAR / FUENTE VERIFICADA.**

---

## C-012 — Capítulo 2: AWS Lambda Node.js 20.x → 24.x (justificar y verificar evidencia)

### Comentario del asesor
```latex
\comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?}
```

### Texto actual relacionado
```latex
Como parte de actividades de mantenimiento y actualización tecnológica, se realizó la migración de funciones serverless desplegadas en AWS Lambda, actualizando el runtime de Node.js
  de la versión 20.x a la 24.x. \comment[id=TUT]{Porque hasta esta versión. ¿ya es estable?¿funcionalidad indispensable?} Esta tarea tuvo como objetivo mantener compatibilidad con versiones soportadas...
```
Ubicación: `Capitulo2.tex`, línea 223-224. Proyecto de Multicom, sin repositorio de código
disponible para verificar.

### Qué está solicitando el asesor
Misma pregunta que C-011, aplicada a esta migración de runtime.

### Respuesta del autor
Confirmado: sí ocurrió. Xavier no recordaba con certeza la versión inicial exacta (mencionó
"aproximadamente Node.js 19.x o 20.x") y pidió verificar antes de afirmar una versión concreta.

### Verificación técnica (fuentes oficiales de AWS)
1. **Node.js 19.x nunca fue un runtime de AWS Lambda.** Lambda solo ofrece runtimes administrados
   para versiones LTS de Node.js (18, 20, 22, 24...); la versión 19 fue una release de corta
   duración (STS) que nunca llegó a LTS y nunca estuvo disponible como runtime de Lambda. Por lo
   tanto, **la versión inicial que ya estaba en el documento (20.x) es la técnicamente correcta**,
   no hace falta cambiarla — el recuerdo de "19.x" no es consistente con lo que AWS Lambda ofrece.
2. **Node.js 20.x en AWS Lambda tiene fin de soporte programado**, en fases: deja de recibir
   parches de seguridad el 30 de abril de 2026; ya no se podrán crear funciones nuevas con ese
   runtime desde el 1 de junio de 2026; ya no se podrán actualizar funciones existentes desde el 1
   de julio de 2026.
3. **Node.js 24.x sí es un runtime real y vigente de AWS Lambda**, disponible desde noviembre de
   2025, con soporte de seguridad hasta abril de 2028 — es, además, el runtime de Node.js más
   reciente disponible en Lambda al momento de esta migración.

**Conclusión: "de la versión 20.x a la 24.x", como ya decía el documento original, es correcto y
no requiere cambio de números de versión** — solo hacía falta la justificación, que ahora sí está
verificada.

### Solución
Agregar la justificación verificada sin alterar los números de versión ya correctos.

### Texto sugerido en LaTeX
```latex
Como parte de actividades de mantenimiento y actualización tecnológica, se realizó la migración de funciones serverless desplegadas en AWS Lambda, actualizando el runtime de Node.js
  de la versión 20.x a la 24.x. Esta actualización se realizó en anticipación al fin de soporte del runtime de Node.js 20.x en AWS Lambda, a partir del cual dicho runtime deja de recibir parches de seguridad\cite{aws_lambda_runtimes}, optando por migrar directamente a la versión 24.x, el runtime de Node.js más reciente disponible en AWS Lambda al momento de la actualización\cite{aws_lambda_nodejs24}. Esta tarea tuvo como objetivo mantener compatibilidad con versiones soportadas, reducir riesgos por obsolescencia y asegurar continuidad operativa en los
  componentes que dependen de estas funciones.
```

### Referencia necesaria
Sí — ya verificadas. Ver entradas `.bib` propuestas en C-015 (`aws_lambda_runtimes`,
`aws_lambda_nodejs24`).

### Estado
**LISTO PARA APLICAR / VERSIÓN VERIFICADA.**

---

## C-013 — Capítulo 3: explicar Atributos de Egreso (AE) y Objetivos Educacionales (OE)

### Comentario del asesor
```latex
\comment[id=TUT]{Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación.}
```

### Texto actual relacionado
```latex
Finalmente, se establece la relación entre la formación académica recibida
  y su aplicación en problemas reales del ámbito laboral, vinculando estos elementos con los Atributos de Egreso (AE) y los Objetivos Educacionales (OE) del programa.\comment[id=TUT]{Explica brevemente qué son los Atributos de Egreso y Objetivos Educacionales, para que el lector entienda la relación.}
```
Ubicación: `Capitulo3.tex`, línea 7.

### Qué está solicitando el asesor
Definir brevemente AE y OE antes de usarlos.

### Solución
Se revisó `Capitulo4.tex`/`Capitulo5.tex` (huérfanos, no incluidos en `tesis.tex`) buscando una
definición reutilizable. **No existe texto de definición real** — solo un párrafo genérico de
"perfil de egreso" y dos enlaces a videos de YouTube ("Ver vídeo"), sin contenido textual propio.
No hay ninguna fuente en el repositorio con el listado real de AE/OE.

### Texto sugerido en LaTeX
No propongo texto — inventar la definición de AE/OE violaría la regla de no inventar información
institucional.

### Referencia necesaria
Sí — documento oficial del programa (institucional, no bibliografía externa).

### Respuesta del autor
"Este comentario lo atenderemos después." No se resuelve en esta sesión.

### Estado
**PENDIENTE PARA FASE POSTERIOR.**

---

## C-014 — Capítulo 3: mayúsculas y acento en "Ingeniería en Sistemas Computacionales"

### Comentario del asesor
```latex
\comment[id=TUT]{En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones.}
```

### Texto actual relacionado
```latex
En conjunto, se concluye que la experiencia profesional descrita aportó un impacto significativo en el desarrollo técnico y profesional, fortaleciendo la preparación para integrarse
  de manera competente al entorno laboral de la ingenieria en sistemas computacionales.\comment[id=TUT]{En este caso debe de ir la primer letra de cada palabra en mayúscula, excepto preposiciones y conjunciones.}
```
Ubicación: `Capitulo3.tex`, línea 58-59.

### Qué está solicitando el asesor
Formato de nombre propio: "Ingeniería en Sistemas Computacionales" (con acento y mayúsculas
iniciales).

### Solución
Corrección ortográfica directa.

### Texto sugerido en LaTeX
```latex
En conjunto, se concluye que la experiencia profesional descrita aportó un impacto significativo en el desarrollo técnico y profesional, fortaleciendo la preparación para integrarse
  de manera competente al entorno laboral de la Ingeniería en Sistemas Computacionales.
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

## C-015 — Bibliografía: falta más bibliografía técnica

### Comentario del asesor
```latex
\comment[id=TUT]{Hace falta más bibliografía, por ejemplo de la tecnología referenciada}
```

### Texto actual relacionado
```latex
\bibliography{referencias} \comment[id=TUT]{Hace falta más bibliografía, por ejemplo de la tecnología referenciada}
```
Ubicación: `tesis.tex`, línea 142.

### Qué está solicitando el asesor
`referencias.bib` solo tiene 2 citas activas, ambas al mismo sitio web de Multicom. No hay fuentes
técnicas sobre Arquitectura Limpia, MVC, REST, microservicios, etc.

### Respuesta del autor
Las secciones se redactaron originalmente desde experiencia propia, sin fuentes específicas.
Xavier pidió investigar fuentes confiables (priorizando libros/documentación oficial sobre blogs),
evaluó como material complementario `https://milanjovanovic.tech/pragmatic-clean-architecture`
pero pidió explícitamente no depender solo de un blog, y autorizó investigar en internet para esta
tarea.

### Investigación realizada (fuentes verificadas, con motivo de por qué sí/no hace falta cada una)

| Concepto | ¿Necesita referencia? | Fragmento que la necesita | Motivo |
|---|---|---|---|
| Arquitectura Limpia | Opcional / recomendable | Menciones en Capitulo1.tex ("siguiendo principios de Arquitectura Limpia") y Capitulo2.tex — se usa como principio general de diseño, no solo como experiencia propia | Es una afirmación técnica general (qué es y qué implica el patrón), no una descripción de una tarea personal — se beneficia de fuente |
| MVC | Opcional | Capitulo1.tex/Capitulo2.tex mencionan MVC como patrón usado, sin definirlo | El documento ya explica en prosa propia cómo se aplicó (vistas/JSP, controladores/Servlets, modelo/MySQL) — la experiencia está bien descrita; una fuente es un respaldo académico adicional, no indispensable |
| REST | Opcional | Menciones de "APIs REST" en varios capítulos, sin definir el estilo arquitectónico | Se usa como término técnico estándar, ampliamente conocido — no es una afirmación institucional ni controvertida, pero para un documento académico formal es una fuente barata de agregar con alto valor (el propio Fielding) |
| Microservicios | Opcional | Menciones de "arquitectura de microservicios" en varios capítulos | Igual que REST: término técnico estándar, se beneficia de una fuente académica reconocida si se quiere formalizar |

**No se recomienda agregar una referencia después de cada mención de estas tecnologías** — como
pidió Xavier, las descripciones de lo que él hizo personalmente no necesitan cita. Las referencias
abajo se proponen para las oraciones puntuales donde el documento hace una afirmación general sobre
qué es o para qué sirve el patrón/estilo, no para cada aparición del término.

### Tabla de fuentes recomendadas

| Concepto | Fuente recomendada | Tipo | ¿La recomiendo? |
|---|---|---|---|
| Clean Architecture | Robert C. Martin, *Clean Architecture: A Craftsman's Guide to Software Structure and Design*, Pearson, 2017, ISBN 978-0-13-449416-6 | Libro | Sí |
| MVC | G. E. Krasner, S. T. Pope, "A cookbook for using the model–view–controller user interface paradigm in Smalltalk-80", *Journal of Object-Oriented Programming*, vol. 1, no. 3, pp. 26–49, 1988 | Artículo (fuente académica original del patrón) | Sí |
| REST | R. T. Fielding, *Architectural Styles and the Design of Network-based Software Architectures*, Tesis doctoral, University of California, Irvine, 2000 | Tesis doctoral (fuente primaria, la más citada en la literatura sobre REST) | Sí |
| Microservicios | Sam Newman, *Building Microservices: Designing Fine-Grained Systems*, 2.ª ed., O'Reilly Media, 2021, ISBN 978-1-492-03402-5 | Libro | Sí |

El blog sugerido por Xavier (`milanjovanovic.tech/pragmatic-clean-architecture`) no se usa como
fuente citable — es contenido práctico útil para consulta personal, pero para el documento
académico se prioriza la fuente primaria (Martin, autor original del término y del libro de
referencia).

### Texto sugerido por concepto

#### Arquitectura Limpia

**Texto actual** (`Capitulo1.tex`, dentro de "Área de sistemas y desarrollo de software"):
```latex
Se participó en la
creación, mantenimiento y mejora de APIs REST desarrolladas con C\# y .NET, siguiendo principios de Arquitectura Limpia para separar responsabilidades entre las distintas capas del
sistema.
```

**Problema:** se nombra el patrón pero no qué principio general lo sustenta.

**Texto sugerido:**
```latex
Se participó en la
creación, mantenimiento y mejora de APIs REST desarrolladas con C\# y .NET, siguiendo principios de Arquitectura Limpia\cite{martin2017cleanarchitecture} para separar responsabilidades entre las distintas capas del
sistema, manteniendo las reglas de negocio independientes de detalles técnicos como la base de datos o el framework utilizado.
```

**Referencia:** `\cite{martin2017cleanarchitecture}`

#### MVC

**Texto actual** (`Capitulo2.tex`, sección 2.2): ya está bien explicado en prosa propia
(vistas=JSP, controlador=Servlets, modelo=acceso a datos en MySQL) — **no se propone agregar una
cita aquí**, porque la explicación ya es específica de lo que Xavier implementó, no una definición
genérica del patrón. Si Xavier prefiere reforzarlo académicamente de todos modos, se puede agregar
la cita a Krasner & Pope en la primera mención de MVC (`Capitulo2.tex`, línea 28: "implementando
una organización basada en MVC (Modelo--Vista--Controlador)"):
```latex
implementando una organización basada en MVC (Modelo--Vista--Controlador)\cite{krasner1988mvc}.
```

**Referencia:** `\cite{krasner1988mvc}` (opcional, no indispensable).

#### REST

**Texto actual** (primera mención, `Capitulo1.tex`): "creación, mantenimiento y mejora de APIs
REST desarrolladas con C\# y .NET..."

**Texto sugerido** (agregar la cita en la primera mención del documento, no en cada aparición):
```latex
Se participó en la
creación, mantenimiento y mejora de APIs REST\cite{fielding2000rest} desarrolladas con C\# y .NET, siguiendo principios de Arquitectura Limpia...
```

**Referencia:** `\cite{fielding2000rest}`

#### Microservicios

**Texto actual** (`Capitulo2.tex`, sección 2.4): "construida bajo una arquitectura de
microservicios."

**Texto sugerido** (primera mención):
```latex
El segundo proyecto corresponde al desarrollo y mantenimiento de la solución backend de una plataforma orientada a servicios financieros, construida bajo una arquitectura de microservicios\cite{newman2021microservices} desarrollados en C\# y .NET...
```

**Referencia:** `\cite{newman2021microservices}`

### Entradas `.bib` propuestas (para `referencias.bib`)

```bibtex
@book{martin2017cleanarchitecture,
  author    = {Martin, Robert C.},
  title     = {Clean Architecture: A Craftsman's Guide to Software Structure and Design},
  publisher = {Pearson},
  year      = {2017},
  isbn      = {978-0-13-449416-6}
}

@article{krasner1988mvc,
  author  = {Krasner, Glenn E. and Pope, Stephen T.},
  title   = {A Cookbook for Using the Model-View-Controller User Interface Paradigm in Smalltalk-80},
  journal = {Journal of Object-Oriented Programming},
  volume  = {1},
  number  = {3},
  pages   = {26--49},
  year    = {1988}
}

@phdthesis{fielding2000rest,
  author = {Fielding, Roy Thomas},
  title  = {Architectural Styles and the Design of Network-based Software Architectures},
  school = {University of California, Irvine},
  year   = {2000},
  url    = {https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm}
}

@book{newman2021microservices,
  author    = {Newman, Sam},
  title     = {Building Microservices: Designing Fine-Grained Systems},
  edition   = {2},
  publisher = {O'Reilly Media},
  year      = {2021},
  isbn      = {978-1-492-03402-5}
}

@online{dotnet_support_policy,
  author  = {{Microsoft}},
  title   = {.NET and .NET Core Official Support Policy},
  url     = {https://dotnet.microsoft.com/en-us/platform/support/policy/dotnet-core},
  urldate = {2026-08-27}
}

@online{aws_apprunner_dotnet_eos,
  author  = {{Amazon Web Services}},
  title   = {Announcement: App Runner Sets End of Support for Specific Runtime Versions in December 2025},
  url     = {https://docs.aws.amazon.com/apprunner/latest/relnotes/release-2025-08-28-runtime-eos-update.html},
  urldate = {2026-08-27}
}

@online{aws_lambda_runtimes,
  author  = {{Amazon Web Services}},
  title   = {Lambda Runtimes},
  url     = {https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html},
  urldate = {2026-08-27}
}

@online{aws_lambda_nodejs24,
  author  = {{Amazon Web Services}},
  title   = {AWS Lambda Adds Support for Node.js 24},
  url     = {https://aws.amazon.com/about-aws/whats-new/2025/11/aws-lambda-nodejs-24},
  urldate = {2026-08-27}
}
```

Todos los campos (autor, título, año, editorial/institución, URL, fecha de consulta) fueron
verificados contra las fuentes oficiales antes de proponerse — ninguno fue inventado.

### Sobre `Kaplan2009` (entrada existente, sin usar)
Pendiente de tu respuesta — no la tenías, por lo que queda para una próxima ronda: ¿se conecta con
"Análisis de requerimientos y diseño inicial de base de datos" del Capítulo 2, o se elimina?

### Estado
**LISTO PARA REVISIÓN DE FUENTES** (no aplicado a `referencias.bib` ni a los `.tex` todavía — falta
tu aprobación de las 4 fuentes y de dónde insertar cada cita).

---

## C-016 — Anexo institucional: incluir título del director en la firma

### Comentario del asesor
```latex
\comment[id=TUT]{Incluir mi título M. en C.}
```

### Texto actual relacionado
```latex
\begin{center}
Atentamente:
\par\vspace{4\@line}
\comment[id=TUT]{Incluir mi título M. en C.}
\begin{tabular}{ccc} 
\@director	\\
Profesor Investigador \\
\end{tabular}
\end{center}
```
Ubicación: `tesis.cls`, línea 480 (macro `\approvalpage`, carta "Liberación de Asesoría").

### Qué está solicitando el asesor
Que su título "M. en C." aparezca junto a su nombre en esta firma — ya aparece en la portada
(`\maketitle` usa `\@directortitle\ \@director`), pero aquí solo se imprime `\@director`.

### Solución
Usar `\@directortitle` igual que en `\maketitle`.

### Texto sugerido en LaTeX
```latex
\begin{center}
Atentamente:
\par\vspace{4\@line}
\begin{tabular}{ccc}
\@directortitle\ \@director	\\
Profesor Investigador \\
\end{tabular}
\end{center}
```

### Referencia necesaria
No.

### Estado
**LISTO PARA APLICAR.**

---

# Preguntas que necesito responder

Todas las preguntas de la ronda anterior fueron respondidas. Quedan solo estas, nuevas o
derivadas de las respuestas:

- **C-007:** ninguna pregunta nueva — solo falta que envíes el archivo del diagrama cuando esté listo.
- **C-010:** revisa el `\comment[id=XAV]` de precaución que dejé en el texto sugerido — confirma que
  la descripción funcional genérica (gestión de clientes, saldos y transacciones) no revela nada
  que prefieras mantener oculto.
- **C-015:** ¿apruebas las 4 fuentes propuestas (Martin, Krasner & Pope, Fielding, Newman) para
  agregarlas a `referencias.bib`? ¿`Kaplan2009` (ya existente, sin usar) se conecta con la sección
  de requerimientos del Capítulo 2 o se elimina?
- **C-013:** diferido — sin preguntas por ahora, se retoma cuando tú lo indiques.

# Ruta del documento

`C:\Proyects\RTI-Docs\RTI-Documentacion\correcciones\correcciones.md`
