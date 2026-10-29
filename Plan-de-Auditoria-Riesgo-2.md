# Taller: del riesgo priorizado al plan de auditoría

**Asignatura:** Auditoría de Sistemas (ET0114)  
**Docente:** Juan Duque  
**Integrante:** Carlos Andrés Alomía Palacios  
**Organización:** Rockstar Games  
**Caso:** Revisión de controles de acceso a información confidencial de desarrollo

## 1. Contexto y continuidad con los trabajos anteriores

Rockstar Games desarrolla videojuegos y utiliza repositorios, archivos digitales y servicios tecnológicos para almacenar código, diseños, material audiovisual y versiones preliminares de sus productos. Esta información es importante para el desarrollo y la propiedad intelectual de la empresa.

En el taller anterior se identificaron riesgos relacionados con el acceso no autorizado a información corporativa y de desarrollo. Como antecedente, en septiembre de 2022 Take-Two Interactive informó que un tercero había accedido a sistemas de Rockstar y descargado información confidencial, incluido material de desarrollo temprano. Este hecho justifica revisar cómo se restringe y supervisa el acceso a los activos de desarrollo.

Este plan es una propuesta académica. No se tiene acceso a los sistemas ni a los controles internos de Rockstar, por lo que no se afirma que exista actualmente una vulnerabilidad ni que un control esté ausente.

## 2. Riesgo seleccionado y justificación

Se selecciona el **riesgo 2 de la matriz de riesgos del taller anterior: filtración de material de desarrollo de videojuegos**.

| Elemento | Referencia de la matriz |
|---|---|
| Identificador | Riesgo 2 |
| Activo o proceso | Código, diseños, videos de prueba y versiones preliminares de videojuegos |
| Amenaza | Intrusos externos o personas que obtienen acceso no autorizado |
| Vulnerabilidad o condición por verificar | Posibles permisos excesivos, controles insuficientes en repositorios o falta de monitoreo de accesos y descargas. Son condiciones por comprobar, no fallas confirmadas. |
| Consecuencia posible | Divulgación anticipada de información, afectación de la ventaja competitiva, fraudes y daño reputacional |
| Probabilidad | 4 — Alta |
| Impacto | 5 — Crítico |
| Nivel | **20/25 — Crítico** |
| Control propuesto en la matriz | Restringir repositorios según función y proyecto, exigir autenticación multifactor, registrar accesos y cambios, proteger secretos y alertar sobre exportaciones masivas o accesos inusuales. |

Se elige porque obtuvo el puntaje más alto de la matriz y porque existe un antecedente público relacionado con la descarga no autorizada de material de desarrollo. Además, es posible plantear pruebas concretas sobre permisos, cuentas y registros. La auditoría permitiría evaluar si los controles diseñados para proteger esos activos están definidos y funcionan de acuerdo con los criterios establecidos.

**Referencia:** Taller anterior, sección 5, matriz de riesgos, fila 2. [Consultar matriz completa](Taller-2-Matriz-de-Riesgos.md).

## 3. Objetivo de auditoría

**Determinar si los controles de acceso a los repositorios y espacios de almacenamiento que contienen información confidencial de desarrollo están definidos, asignados de acuerdo con las funciones de los usuarios y supervisados mediante registros de actividad durante el periodo comprendido entre el 1 de mayo y el 31 de octubre de 2026.**

El objetivo se puede comprobar mediante la revisión de políticas, listados de permisos, cuentas autorizadas y registros de acceso o descarga. El periodo propuesto corresponde a seis meses y permite revisar tanto la configuración de los accesos como su operación durante un intervalo definido.

## 4. Alcance funcional

- **Proceso:** administración, aprobación, modificación y revocación de permisos de acceso a información confidencial de desarrollo.
- **Sistema o componente:** repositorios de código y espacios de almacenamiento utilizados para guardar diseños, material audiovisual y versiones preliminares de videojuegos. No se presupone una plataforma o producto específico.
- **Población:** cuentas de usuario y privilegiadas con acceso a esos repositorios, solicitudes de alta o modificación de permisos, bajas de usuarios y registros de acceso, cambios y descargas disponibles durante el periodo.
- **Periodo:** del 1 de mayo al 31 de octubre de 2026.
- **Áreas o responsables:** responsables de desarrollo, administradores de repositorios o infraestructura, equipo de seguridad de la información y gestión de identidades o recursos humanos, según la estructura que la organización confirme.
- **Inclusiones:** permisos de lectura y escritura, cuentas privilegiadas, autenticación, aprobación de accesos, revocación de permisos y trazabilidad de actividad.
- **Exclusiones:** revisión del código fuente en cuanto a calidad, pruebas funcionales del videojuego, seguridad de los datos de jugadores y auditoría completa de todos los sistemas corporativos. Se excluyen porque no son necesarios para responder el objetivo planteado.

El alcance depende de que la organización identifique los repositorios y espacios de almacenamiento que contienen material confidencial y permita consultar sus configuraciones y registros. Si no se entrega esa información, la conclusión deberá limitarse a los documentos y componentes efectivamente disponibles.

## 5. Criterios de evaluación

El marco principal será **ISO/IEC 27001:2022**, seleccionado en el primer taller. Se utilizará como referencia para orientar la evaluación de controles de acceso y protección de la información. La aplicación concreta de cada criterio dependerá de confirmar las políticas y controles que la organización tenga establecidos.

| Control o aspecto | Condición esperada para la auditoría | Fuente del criterio |
|---|---|---|
| Asignación de accesos | Los permisos deben estar autorizados y corresponder a las funciones y necesidades del usuario. | ISO/IEC 27001:2022, controles del Anexo A 5.15 (control de acceso) y 5.18 (derechos de acceso); política interna vigente por solicitar. |
| Accesos privilegiados | Las cuentas con privilegios elevados deben estar identificadas, autorizadas y sujetas a revisión. | ISO/IEC 27001:2022, control del Anexo A 8.2 (derechos de acceso privilegiado); procedimiento interno por confirmar. |
| Restricción de información | El acceso a archivos y repositorios debe limitarse según la clasificación y necesidad de uso. | ISO/IEC 27001:2022, control del Anexo A 8.3 (restricción de acceso a la información); reglas internas por solicitar. |
| Registro de actividad | Deben existir registros suficientes para identificar accesos y actividades relevantes sobre los activos incluidos. | ISO/IEC 27001:2022, control del Anexo A 8.15 (registro de eventos); configuración y política de registros por confirmar. |

Los controles citados se toman como referencias para orientar la auditoría; no se afirma que Rockstar esté certificada ni que aplique exactamente estas medidas. Antes de emitir una conclusión, el auditor debe solicitar las políticas y procedimientos vigentes. Si no existe un documento interno que defina la condición esperada, se dejará registrado como **criterio por confirmar** y no se supondrá su contenido.

## 6. Programa de trabajo

Se proponen dos procedimientos complementarios: primero revisar el diseño de los controles y después comprobar su operación.

### Procedimiento 1. Comprender y verificar el diseño del control

**Propósito:** establecer cómo se solicitan, aprueban, asignan, revisan y revocan los permisos de acceso a los activos de desarrollo.

**Actividades propuestas:**

1. Solicitar la política de control de acceso, el procedimiento de administración de usuarios y la clasificación de la información.
2. Identificar quién puede autorizar accesos y quién administra los repositorios y espacios de almacenamiento.
3. Solicitar un listado de repositorios incluidos, roles, grupos y cuentas con privilegios.
4. Comparar el procedimiento documentado con los criterios de acceso autorizado, mínimo privilegio y restricción de información.
5. Verificar mediante configuración o demostración controlada cómo se asignan los permisos y cómo se retiran.
6. Documentar si las responsabilidades están definidas, si existen aprobaciones y si los permisos pueden revisarse.

**Población o muestra:** políticas, procedimientos y configuraciones de los repositorios incluidos en el alcance. Se propone revisar todos los documentos aplicables y los componentes identificados por los responsables, si su número lo permite.

**Evidencia esperada:** políticas vigentes, procedimientos, matriz de roles y permisos, inventario de repositorios, configuraciones de acceso y evidencia de aprobación de permisos.

**Posibles excepciones:** ausencia de procedimiento vigente, permisos sin responsable o autorización identificable, cuentas privilegiadas no justificadas o imposibilidad de establecer qué usuarios pueden acceder a información confidencial.

### Procedimiento 2. Comprobar la operación de los controles

**Propósito:** verificar si los permisos y la supervisión de accesos se aplicaron durante el periodo definido.

**Actividades propuestas:**

1. Solicitar la población de altas, modificaciones y bajas de permisos realizadas entre el 1 de mayo y el 31 de octubre de 2026.
2. Solicitar los listados de cuentas activas y privilegiadas y los registros de acceso, cambios y descargas disponibles.
3. Seleccionar una muestra basada en riesgo: priorizar cuentas privilegiadas, accesos recientes, cambios de permisos y bajas de usuarios. El tamaño se definirá después de conocer la población real.
4. Para cada elemento seleccionado, comparar la solicitud y aprobación con el permiso asignado en la configuración.
5. Revisar si las bajas o cambios de función tuvieron como resultado la modificación o revocación del acceso correspondiente.
6. Examinar los registros disponibles para identificar accesos fuera de lo autorizado o actividades inusuales y comprobar si fueron revisados o atendidos.
7. Registrar cada excepción con el elemento revisado, el criterio relacionado y la evidencia que la sustenta.

**Población o muestra:** movimientos de permisos, cuentas activas y privilegiadas y registros de actividad del periodo. No se fija una cantidad de elementos porque se desconoce el volumen real; la muestra se definirá cuando la organización entregue la población.

**Evidencia esperada:** solicitudes de acceso, aprobaciones, listados de usuarios y roles, historial de cambios, registros de autenticación y actividad, constancias de revisión y tickets o reportes de atención de alertas.

**Posibles excepciones:** accesos sin aprobación, permisos superiores a los requeridos, cuentas que debieron ser desactivadas y continúan habilitadas, registros incompletos o actividades relevantes sin revisión documentada.

### Trazabilidad de los procedimientos

| Riesgo | Control a evaluar | Criterio y fuente | Procedimiento | Evidencia esperada |
|---|---|---|---|---|
| Riesgo 2 — Filtración de material de desarrollo | Autorización y restricción de permisos | ISO/IEC 27001:2022, Anexo A 5.15, 5.18 y 8.3; política interna por confirmar | Revisar el diseño, roles, responsables y configuración de permisos | Políticas, inventario, matriz de roles y configuración |
| Riesgo 2 — Filtración de material de desarrollo | Gestión de cuentas privilegiadas | ISO/IEC 27001:2022, Anexo A 8.2; procedimiento interno por confirmar | Comparar cuentas privilegiadas con autorizaciones y funciones | Listado de cuentas, aprobaciones e historial de cambios |
| Riesgo 2 — Filtración de material de desarrollo | Registro y supervisión de actividad | ISO/IEC 27001:2022, Anexo A 8.15; política de registros por confirmar | Examinar una muestra de registros y comprobar su revisión y atención | Logs, reportes de monitoreo y tickets de incidentes |

## 7. Organización de la ejecución propuesta

### Cronograma

| Fase | Actividades | Duración estimada |
|---|---|---:|
| 1. Preparación | Confirmar objetivo, alcance, responsables y solicitud inicial de información | 2 días |
| 2. Solicitud y comprensión | Recibir políticas, inventarios, permisos y explicación del proceso | 3 días |
| 3. Revisión del diseño | Analizar procedimientos, roles y configuraciones de acceso | 3 días |
| 4. Pruebas de operación | Seleccionar la muestra, comparar aprobaciones, permisos y registros | 4 días |
| 5. Cierre | Organizar excepciones, validar evidencias y preparar el informe de auditoría | 2 días |

La duración total estimada es de 14 días hábiles. Es una planificación propuesta y depende de la disponibilidad de los responsables y de la entrega oportuna de la información.

### Responsables del equipo

Como el repositorio del equipo registra un solo integrante, se plantea la siguiente distribución para el trabajo individual:

- **Carlos Andrés Alomía Palacios:** preparar el plan, definir el alcance y los criterios, organizar la solicitud de evidencias, documentar los procedimientos y consolidar los resultados si la auditoría pudiera ejecutarse.

En una auditoría real, los responsables de desarrollo, administración de repositorios y seguridad de la información serían los encargados de explicar el proceso y facilitar la evidencia correspondiente. No se les asignan tareas como integrantes del equipo auditor.

### Recursos y dependencias

- Acceso autorizado y de solo lectura a las configuraciones y registros que correspondan.
- Políticas y procedimientos vigentes de control de acceso.
- Inventario de repositorios y cuentas incluidas.
- Participación de los responsables del proceso.
- Hoja de trabajo para documentar muestras, criterios, evidencias y excepciones.

La ejecución depende de la autorización de Rockstar y de que entregue información suficiente. Sin ese acceso, el equipo puede presentar y defender el plan, pero no afirmar que realizó las pruebas técnicas.

## 8. Supuestos y limitaciones

**Hechos comprobados mediante fuentes públicas**

- Take-Two Interactive informó en una presentación ante la SEC que en septiembre de 2022 un tercero accedió sin autorización a sistemas de Rockstar y descargó información confidencial, incluido material de desarrollo temprano.
- La matriz anterior registra este antecedente como fundamento para priorizar la revisión de los activos de desarrollo.

**Supuestos del plan**

- Se supone que la organización utiliza repositorios y espacios de almacenamiento con distintos niveles de acceso para proteger los activos de desarrollo.
- Se supone que existen responsables encargados de autorizar y administrar esos accesos. Esto debe confirmarse durante la auditoría.
- Se propone el periodo del 1 de mayo al 31 de octubre de 2026 para delimitar las pruebas.

**Información por solicitar**

- Políticas y procedimientos vigentes de acceso.
- Inventario de repositorios y espacios de almacenamiento incluidos.
- Listados de cuentas, roles y permisos.
- Solicitudes y aprobaciones de acceso, modificación y retiro.
- Registros de autenticación, actividad, descargas y revisión de alertas.

**Propuestas del equipo**

- El objetivo, alcance, criterios, procedimientos, muestra y cronograma descritos en este documento son propuestas para una auditoría futura.

**Limitaciones**

No se cuenta con autorización ni acceso a los sistemas internos de Rockstar Games. Por ello, no se ejecutaron pruebas, no se obtuvieron registros internos y no se emiten hallazgos ni porcentajes de cumplimiento. La matriz contiene estimaciones académicas y condiciones por verificar. Cualquier conclusión sobre la eficacia de los controles requeriría ejecutar los procedimientos y evaluar evidencia auténtica.

## 9. Conclusión

El riesgo de filtración de material de desarrollo fue seleccionado por su nivel crítico en la matriz anterior y por el antecedente público de acceso no autorizado ocurrido en 2022. El plan propuesto concentra la auditoría en la autorización, restricción y supervisión de los accesos a repositorios y espacios de almacenamiento confidenciales.

Los dos procedimientos permiten revisar tanto el diseño de los controles como su operación, mediante políticas, configuraciones, aprobaciones y registros. Sin acceso a la información interna de Rockstar, este documento debe entenderse como una planificación académica y no como una auditoría ejecutada. Si la organización facilitara la evidencia solicitada, sería posible evaluar los controles y documentar las excepciones encontradas.

## 10. Fuentes y documentos relacionados

1. [SEC — Presentación de Take-Two Interactive con información sobre el incidente de septiembre de 2022](https://www.sec.gov/Archives/edgar/data/946581/000162828025026694/ttwo-20250331.htm).
2. [ISO — ISO/IEC 27001:2022, Information security management systems](https://www.iso.org/standard/27001).
3. [Taller 2 — Matriz de riesgos de Rockstar Games](Taller-2-Matriz-de-Riesgos.md), especialmente sección 5, fila 2.

---

**Nota de continuidad:** este plan conserva el caso Rockstar Games y desarrolla el riesgo 2 de la matriz del taller anterior. La matriz completa se mantiene en el archivo enlazado y no se reemplaza por este documento.
