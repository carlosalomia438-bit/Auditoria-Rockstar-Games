# Taller 2: Análisis de riesgos de TI — Rockstar Games

**Asignatura:** Auditoría de Sistemas (ET0114)  
**Docente:** Juan Duque  
**Integrante:** Carlos Andrés Alomía Palacios  
**Organización analizada:** Rockstar Games

## 1. Contexto del caso

Rockstar Games desarrolla videojuegos y mantiene servicios digitales para sus jugadores, por lo que necesita proteger información de desarrollo, sistemas en la nube, cuentas y servicios en línea.  
El análisis toma como referencia dos incidentes reportados públicamente: el acceso no autorizado a información de Rockstar divulgado en abril de 2026 y la filtración de material de desarrollo reportada en septiembre de 2022.  
La matriz combina hechos públicos con riesgos posibles que deberían verificarse en una auditoría.  
No se afirma que las vulnerabilidades hipotéticas descritas estén presentes actualmente en la empresa.

## 2. Hechos públicos y alcance

- **Incidente reportado en abril de 2026:** Rockstar confirmó que una cantidad limitada de información corporativa no material fue accedida en una brecha relacionada con un tercero. En los reportes públicos, el grupo ShinyHunters afirmó haber accedido a información en la nube mediante un proveedor de analítica. Rockstar indicó que el incidente no tuvo impacto en la organización ni en los jugadores, según su declaración pública.
- **Antecedente de septiembre de 2022:** Take-Two Interactive informó que un tercero accedió ilegalmente a sistemas de Rockstar y descargó información confidencial, incluida material de desarrollo temprano de un videojuego.

Estos hechos hacen pertinente revisar el control de proveedores, los accesos a la nube, la protección de información confidencial y la respuesta a incidentes. **La información pública consultada no permite confirmar qué controles internos estaban activos ni determinar que se hayan expuesto datos personales de jugadores o código fuente de GTA VI en el incidente de 2026.**

## 3. Supuestos y método de valoración

Como no se cuenta con acceso a los sistemas, políticas ni registros internos de Rockstar Games, esta es una evaluación académica preliminar basada en información pública. Los controles existentes se marcan como **no verificables públicamente** cuando no hay evidencia suficiente.

La probabilidad y el impacto se califican de 1 a 5:

| Valor | Probabilidad | Impacto |
|---|---|---|
| 1 | Muy baja | Muy bajo |
| 2 | Baja | Bajo |
| 3 | Media | Moderado |
| 4 | Alta | Alto |
| 5 | Muy alta | Crítico |

**Nivel de riesgo = Probabilidad × Impacto.** Para este ejercicio se propone la siguiente clasificación: 1–5 bajo, 6–10 medio, 11–15 alto y 16–25 crítico. Las puntuaciones son estimaciones para priorizar la revisión, no resultados de una auditoría interna.

## 4. Activos y procesos considerados

1. Información confidencial del desarrollo de videojuegos: código, diseños, material audiovisual y versiones preliminares.
2. Plataformas de nube y conexiones con proveedores externos.
3. Cuentas privilegiadas, credenciales, claves y tokens de acceso.
4. Registros de seguridad, monitoreo y gestión de incidentes.
5. Servicios en línea y datos operativos que permiten jugar y mantener los servicios.
6. Copias de seguridad y procedimientos de recuperación.

## 5. Matriz de riesgos

### Riesgo 1. Acceso no autorizado a información a través de un tercero

- **Activo/proceso:** Plataformas de nube e información corporativa.
- **Amenaza:** Atacantes externos que aprovechan accesos o integraciones de proveedores.
- **Vulnerabilidad:** Posible debilidad en los permisos, credenciales o conexión de un tercero. El vector técnico exacto del incidente de 2026 debe verificarse; no se presenta como confirmado.
- **Riesgo y consecuencia:** Un acceso externo a través de un proveedor podría permitir consultar o extraer información confidencial y generar costos de investigación, extorsión o daño reputacional.
- **Probabilidad:** 4/5.
- **Impacto:** 4/5.
- **Nivel:** **16/25 — Crítico.**
- **Control actual/evidencia:** Se conoce el incidente comunicado públicamente en abril de 2026. Las medidas específicas de control de proveedores y accesos no se pueden confirmar con las fuentes públicas consultadas.
- **Control propuesto:** Aplicar mínimo privilegio a cada proveedor, limitar el alcance y duración de tokens, exigir autenticación multifactor cuando corresponda, revisar integraciones periódicamente, revocar accesos que ya no se necesiten y monitorear actividad anormal.
- **Justificación de prioridad:** Es la prioridad principal porque existe un incidente público reciente relacionado con acceso a información y terceros.

### Riesgo 2. Filtración de material confidencial de desarrollo

- **Activo/proceso:** Código, diseños, videos de prueba y versiones preliminares de videojuegos.
- **Amenaza:** Intrusos externos o personas que obtienen acceso no autorizado a los repositorios y sistemas internos.
- **Vulnerabilidad:** La exposición concreta actual no está confirmada. Se debe revisar la separación de ambientes, los permisos de repositorios y la protección de archivos confidenciales.
- **Riesgo y consecuencia:** La divulgación anticipada de material podría afectar lanzamientos, facilitar fraudes o suplantaciones, perjudicar la ventaja competitiva y afectar la reputación.
- **Probabilidad:** 4/5.
- **Impacto:** 5/5.
- **Nivel:** **20/25 — Crítico.**
- **Control actual/evidencia:** En 2022, Take-Two reportó el acceso no autorizado a sistemas de Rockstar y la descarga de información confidencial, incluido material temprano de desarrollo. No se dispone aquí de evidencia suficiente para verificar los controles actuales.
- **Control propuesto:** Restringir los repositorios por función y proyecto, exigir MFA, registrar descargas y cambios, proteger secretos, revisar permisos regularmente y usar alertas para exportaciones masivas o accesos inusuales.
- **Justificación de prioridad:** El antecedente público de 2022 demuestra que la confidencialidad del material de desarrollo merece una revisión específica.

### Riesgo 3. Uso indebido de cuentas privilegiadas, claves o tokens

- **Activo/proceso:** Cuentas administrativas, identidades de servicio y credenciales de nube.
- **Amenaza:** Robo de credenciales, phishing o uso indebido de una cuenta con permisos elevados.
- **Vulnerabilidad:** Posible exceso de privilegios, credenciales de larga duración o falta de rotación; estos puntos deben comprobarse mediante entrevistas y revisión de configuración.
- **Riesgo y consecuencia:** Una cuenta comprometida podría ampliar el acceso del atacante, facilitar la extracción de información o permitir cambios no autorizados.
- **Probabilidad:** 3/5.
- **Impacto:** 5/5.
- **Nivel:** **15/25 — Alto.**
- **Control actual/evidencia:** No se encontraron evidencias públicas suficientes para determinar la configuración actual de las cuentas privilegiadas.
- **Control propuesto:** Usar MFA resistente al phishing para accesos administrativos cuando sea posible, privilegios temporales, bóveda de secretos, rotación de claves, revisión de permisos y alertas de inicio de sesión anómalo.
- **Justificación de prioridad:** El impacto potencial es alto porque estas cuentas pueden dar acceso a múltiples sistemas y datos.

### Riesgo 4. Detección tardía y respuesta insuficiente ante un incidente

- **Activo/proceso:** Registros de seguridad, monitoreo, equipo de respuesta y comunicación del incidente.
- **Amenaza:** Ataques que pasan inadvertidos o se atienden tarde.
- **Vulnerabilidad:** No hay evidencia pública suficiente para afirmar que Rockstar tenga deficiencias de monitoreo. Se debe verificar cobertura de registros, tiempos de detección y pruebas del plan de respuesta.
- **Riesgo y consecuencia:** Una detección tardía puede aumentar el tiempo de permanencia del atacante, la cantidad de información expuesta y el costo de recuperación.
- **Probabilidad:** 3/5.
- **Impacto:** 4/5.
- **Nivel:** **12/25 — Alto.**
- **Control actual/evidencia:** La existencia de incidentes públicos no permite concluir por sí sola que la detección haya sido tardía ni evaluar la calidad de la respuesta. Los registros y procedimientos internos no son públicos.
- **Control propuesto:** Definir un plan de respuesta con responsables y escalamiento, centralizar registros, generar alertas para accesos de terceros y descargas inusuales, hacer simulacros y documentar las lecciones aprendidas.
- **Justificación de prioridad:** Una respuesta preparada puede limitar las consecuencias de los riesgos de acceso y filtración descritos anteriormente.

### Riesgo 5. Interrupción de servicios en línea

- **Activo/proceso:** Infraestructura de los servicios en línea y operaciones de soporte.
- **Amenaza:** Ataques de denegación de servicio, errores de configuración, fallas de infraestructura o cambios defectuosos.
- **Vulnerabilidad:** No se afirma que exista una falla actual. Deben evaluarse redundancia, monitoreo, gestión de cambios y capacidad de recuperación.
- **Riesgo y consecuencia:** Los jugadores podrían no poder iniciar sesión o utilizar funciones en línea, lo que ocasionaría quejas, trabajo adicional de soporte y afectación reputacional.
- **Probabilidad:** 3/5.
- **Impacto:** 4/5.
- **Nivel:** **12/25 — Alto.**
- **Control actual/evidencia:** No se dispone de métricas internas verificables sobre disponibilidad, incidentes o acuerdos de nivel de servicio.
- **Control propuesto:** Monitorear disponibilidad y rendimiento, probar medidas de protección contra tráfico malicioso, establecer procedimientos de escalamiento y validar planes de continuidad y recuperación.
- **Justificación de prioridad:** La disponibilidad es importante para los servicios digitales de una empresa de videojuegos, aunque la puntuación debe validarse con métricas reales.

### Riesgo 6. Pérdida de información o recuperación incompleta

- **Activo/proceso:** Copias de seguridad, repositorios y procedimientos de recuperación.
- **Amenaza:** Borrado accidental, ransomware, corrupción de datos o falla de almacenamiento.
- **Vulnerabilidad:** No se conocen públicamente la frecuencia, aislamiento ni resultados de las pruebas de recuperación. Son aspectos por verificar, no fallas confirmadas.
- **Riesgo y consecuencia:** La empresa podría perder avances de desarrollo o tardar en restablecer sistemas y servicios.
- **Probabilidad:** 2/5.
- **Impacto:** 5/5.
- **Nivel:** **10/25 — Medio.**
- **Control actual/evidencia:** No se cuenta con evidencia pública suficiente para evaluar las copias de seguridad y las pruebas de restauración.
- **Control propuesto:** Mantener copias cifradas y aisladas, limitar quién puede borrarlas, probar restauraciones periódicamente y definir objetivos de recuperación (RTO/RPO) para los sistemas críticos.
- **Justificación de prioridad:** Aunque la probabilidad estimada es menor, el impacto de perder información de desarrollo puede ser muy alto.

## 6. Orden recomendado de atención

1. **Riesgo 2 — Filtración de material de desarrollo (20/25):** revisar permisos y registros de repositorios y activos confidenciales.
2. **Riesgo 1 — Acceso a través de terceros (16/25):** evaluar inmediatamente los accesos e integraciones de proveedores.
3. **Riesgo 3 — Cuentas privilegiadas (15/25):** comprobar MFA, privilegios y gestión de claves.
4. **Riesgo 4 — Detección y respuesta (12/25):** validar monitoreo, escalamiento y ejercicios de respuesta.
5. **Riesgo 5 — Disponibilidad de servicios (12/25):** revisar continuidad operativa y protección de servicios.
6. **Riesgo 6 — Copias y recuperación (10/25):** comprobar respaldos y pruebas de restauración.

Este orden es una propuesta académica basada en los puntajes estimados. Una auditoría real podría cambiarlo al conocer los controles existentes, el impacto para el negocio y la evidencia técnica.

## 7. Relación con los marcos de auditoría

- **ISO/IEC 27001:** sirve como referencia principal para revisar gestión de riesgos de seguridad de la información, control de acceso, proveedores, protección de información y respuesta a incidentes.
- **ITIL:** ayuda a evaluar la gestión de incidentes, cambios, disponibilidad, continuidad y recuperación de los servicios digitales.
- **COBIT:** permite revisar responsabilidades, seguimiento de riesgos, supervisión de controles y alineación de la tecnología con los objetivos de la organización.

Se mantiene el orden propuesto en el primer taller: **ISO/IEC 27001 → ITIL → COBIT**. Primero se revisa la protección de la información, luego la operación de los servicios y finalmente la gestión y el control general de TI.

## 8. Conclusión

Los incidentes públicos de 2022 y 2026 hacen razonable priorizar la protección de la información confidencial y la revisión de accesos de terceros. También conviene evaluar las cuentas privilegiadas, la respuesta a incidentes, la disponibilidad y las copias de seguridad. Sin acceso a la evidencia interna, no se puede afirmar que Rockstar tenga las vulnerabilidades hipotéticas descritas ni que los controles propuestos estén ausentes. El siguiente paso de una auditoría real sería solicitar políticas, registros, configuraciones y resultados de pruebas para confirmar o ajustar la matriz.

## 9. Fuentes consultadas

1. [The Record — Rockstar y el incidente de acceso a información a través de un tercero (abril de 2026)](https://therecord.media/rockstar-hackers-cyberattack-cloud)
2. [TechCrunch — Incidente de Anodot y extorsión a empresas afectadas (abril de 2026)](https://techcrunch.com/2026/04/13/hack-at-anodot-leaves-over-a-dozen-breached-companies-facing-extortion/)
3. [The Register — Reporte sobre la brecha divulgada en abril de 2026](https://www.theregister.com/2026/04/13/shinyhunters_rockstar_breach/)
4. [SEC — Presentación de Take-Two Interactive que describe el incidente de 2022](https://www.sec.gov/Archives/edgar/data/946581/000162828025026694/ttwo-20250331.htm)

**Nota:** Las puntuaciones son estimaciones del ejercicio académico. Antes de presentar el trabajo, conviene revisar que la rúbrica del docente no exija una escala o formato específico distinto.
