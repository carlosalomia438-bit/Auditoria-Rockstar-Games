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

La siguiente tabla reúne los campos solicitados. Las puntuaciones son estimaciones académicas y las vulnerabilidades hipotéticas deben comprobarse durante una auditoría; no se presentan como fallas confirmadas.

| # | Activo o proceso | Amenaza | Vulnerabilidad o condición por verificar | Riesgo y consecuencia | Prob. (1–5) | Impacto (1–5) | Nivel | Control actual / evidencia pública | Control propuesto | Justificación de prioridad |
|---|---|---|---|---|---:|---:|---|---|---|---|
| 1 | Plataformas de nube e información corporativa | Atacantes externos que aprovechan accesos o integraciones de proveedores | Posible debilidad en permisos, credenciales o conexión de un tercero. El vector técnico exacto del incidente de 2026 debe verificarse. | Acceso o extracción de información confidencial, con posibles costos de investigación, extorsión o daño reputacional. | 4 | 4 | **16 — Crítico** | Rockstar confirmó en abril de 2026 que se accedió a una cantidad limitada de información corporativa no material en un incidente relacionado con un tercero. Los controles específicos no son verificables públicamente. | Aplicar mínimo privilegio a proveedores, limitar alcance y duración de tokens, usar MFA cuando corresponda, revisar integraciones, revocar accesos innecesarios y monitorear actividad anormal. | Prioridad alta porque existe un incidente público reciente relacionado con terceros y acceso a información. |
| 2 | Código, diseños, videos de prueba y versiones preliminares de videojuegos | Intrusos externos o personas que obtienen acceso no autorizado | La exposición actual no está confirmada. Revisar permisos de repositorios, separación de ambientes y protección de archivos confidenciales. | Divulgación anticipada que podría afectar lanzamientos, facilitar fraudes, perjudicar la ventaja competitiva y dañar la reputación. | 4 | 5 | **20 — Crítico** | En 2022, Take-Two informó que un tercero accedió a sistemas de Rockstar y descargó información confidencial, incluido material temprano de desarrollo. No se verifican aquí los controles actuales. | Restringir repositorios por función y proyecto, exigir MFA, registrar descargas y cambios, proteger secretos y alertar sobre exportaciones masivas o accesos inusuales. | Es el puntaje más alto y existe un antecedente público relacionado con material de desarrollo. |
| 3 | Cuentas administrativas, identidades de servicio y credenciales de nube | Robo de credenciales, phishing o uso indebido de cuentas privilegiadas | Posible exceso de privilegios, credenciales de larga duración o falta de rotación; debe comprobarse mediante revisión de configuración. | Una cuenta comprometida podría ampliar el acceso del atacante, facilitar la extracción de información o permitir cambios no autorizados. | 3 | 5 | **15 — Alto** | No se encontró evidencia pública suficiente para determinar la configuración actual de cuentas privilegiadas. | Usar MFA resistente al phishing cuando sea posible, privilegios temporales, bóveda de secretos, rotación de claves, revisión de permisos y alertas de inicio de sesión anómalo. | El impacto potencial es alto porque estas cuentas pueden dar acceso a varios sistemas y datos. |
| 4 | Registros de seguridad, monitoreo y respuesta a incidentes | Ataques que pasan inadvertidos o se atienden tarde | No hay evidencia pública suficiente para afirmar que exista una deficiencia. Verificar cobertura de registros, tiempos de detección y pruebas del plan de respuesta. | La detección tardía podría aumentar el tiempo de permanencia del atacante, la información expuesta y el costo de recuperación. | 3 | 4 | **12 — Alto** | Los incidentes públicos no permiten concluir por sí solos que la detección haya sido tardía ni evaluar la respuesta. Los registros internos no son públicos. | Definir responsables y escalamiento, centralizar registros, alertar sobre accesos de terceros y descargas inusuales, hacer simulacros y documentar lecciones aprendidas. | Una respuesta preparada puede limitar las consecuencias de los riesgos de acceso y filtración. |
| 5 | Infraestructura de servicios en línea y soporte | Denegación de servicio, errores de configuración, fallas de infraestructura o cambios defectuosos | No se afirma que exista una falla actual. Evaluar redundancia, monitoreo, gestión de cambios y recuperación. | Los jugadores podrían no iniciar sesión o usar funciones en línea, causando quejas, más trabajo de soporte y daño reputacional. | 3 | 4 | **12 — Alto** | No se dispone de métricas internas verificables sobre disponibilidad, incidentes o acuerdos de nivel de servicio. | Monitorear disponibilidad y rendimiento, probar protección contra tráfico malicioso, definir escalamiento y validar planes de continuidad y recuperación. | La disponibilidad es importante para los servicios digitales, pero el puntaje debe validarse con métricas reales. |
| 6 | Copias de seguridad, repositorios y recuperación | Borrado accidental, ransomware, corrupción de datos o falla de almacenamiento | No se conocen públicamente la frecuencia, aislamiento ni resultados de las pruebas de recuperación; son aspectos por verificar, no fallas confirmadas. | Pérdida de avances de desarrollo o demora en restablecer sistemas y servicios. | 2 | 5 | **10 — Medio** | No hay evidencia pública suficiente para evaluar copias de seguridad y pruebas de restauración. | Mantener copias cifradas y aisladas, limitar quién puede borrarlas, probar restauraciones y definir objetivos de recuperación (RTO/RPO) para sistemas críticos. | La probabilidad estimada es menor, pero perder información de desarrollo tendría un impacto alto. |

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
