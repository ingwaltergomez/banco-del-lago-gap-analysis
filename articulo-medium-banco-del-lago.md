# Cómo apliqué un Gap Analysis de ciberseguridad a un banco ficticio guatemalteco (y qué aprendí del ejercicio)

*Un ejercicio de aplicación del NIST CSF 2.0 e ISO/IEC 27001:2022 a un caso de estudio construido con datos reales del mercado. No es un diagnóstico de la banca guatemalteca. Es una demostración de metodología.*

---

## Aclaración importante antes de empezar

**Banco del Lago, S.A. es una institución ficticia.** No existe. No es un banco real. No representa a ningún banco real.

El perfil institucional se construyó tomando como base datos públicos de Banco Promerica de Guatemala (informes financieros y de mercado 2025–2026) y aplicando un ajuste explícito del +15%, con el único fin de tener un caso de estudio con dimensiones realistas.

**Los resultados de este análisis (madurez 1.7 sobre 5.0, 40 hallazgos, Q1,330,000 de inversión) corresponden exclusivamente al caso de estudio ficticio.** No son un diagnóstico del estado real de la banca guatemalteca, ni de ningún banco en particular. No se puede extrapolar.

Este artículo documenta **un ejercicio de aplicación de metodología**: cómo se estructura un Gap Analysis contra NIST CSF 2.0, cómo se evalúa la madurez, y cómo se traduce en un plan de remediación. El valor está en el método, no en los números.

---

## Por qué hice este ejercicio

Soy especialista en infraestructura y seguridad, con más de 20 años en Linux y Red Hat. Tengo la certificación ISO 27001 Lead Implementer. Pero una cosa es tener la certificación y otra cosa es demostrar que sabes aplicarla.

Este ejercicio nació de una pregunta concreta: **¿cómo se ve un Gap Analysis de ciberseguridad en una institución financiera, desde adentro?**

No quería escribir teoría. Quería construir un caso completo: perfil institucional, marco regulatorio aplicable, evaluación de madurez, hallazgos, plan de remediación, presentación ejecutiva. Todo trazable. Todo con supuestos explícitos.

El resultado es un caso de estudio de ~20 páginas que aplica el método a una institución ficticia pero construida con datos reales del mercado guatemalteco.

---

## El contexto del caso de estudio

**Banco del Lago, S.A.** (ficticio) tiene las siguientes características, todas etiquetadas según su origen:

| Dato | Valor | Origen |
|------|-------|--------|
| Empleados | ~2,800 | Estimado |
| Activos totales | ~Q39,290 millones | Verificado (base Promerica +15%) |
| Agencias | 85 | Supuesto |
| Cajeros automáticos | 180 | Supuesto |
| Clientes activos | ~750,000 | Supuesto |
| Modelo de nube | Híbrido | Supuesto |
| Core bancario | Producto comercial de terceros | Supuesto |
| SOC / CSIRT | Tercerizado (MDR) | Supuesto |

El banco está sujeto a la regulación de la **Superintendencia de Bancos de Guatemala (SIB)**, específicamente:

- **JM-98-2025** — Reglamento para la Administración del Riesgo Tecnológico (vigente desde 30-oct-2025)
- **JM-91-2024 / JM-99-2025** — Reglamento de Medidas de Seguridad en Canales Electrónicos
- **JM-62-2016** — Reglamento de Gobierno Corporativo

**Los plazos regulatorios que presionan el calendario:**

| Hito regulatorio | Fecha límite |
|------------------|--------------|
| Actualización del Manual de Riesgo Tecnológico | Octubre 2026 |
| Actualización del DRP | Octubre 2026 |
| Clasificación de criticidad de proveedores | Dic 2026 – Mar 2027 |
| Revisión de canales electrónicos | Dic 2026 – Mar 2027 |

**El incidente disparador** (también ficticio): el banco detectó un caso de fraude electrónico por WhatsApp que explotó una debilidad de autenticación en uno de sus canales electrónicos. La combinación de este incidente con la presión regulatoria fue lo que autorizó el proyecto.

---

## La metodología

Estructuré el Gap Analysis contra los **6 dominios del NIST CSF 2.0**:

1. **Gobernar (GV)** — Estrategia, roles, políticas, supervisión, cadena de suministro
2. **Identificar (ID)** — Activos, riesgos, mejora continua
3. **Proteger (PR)** — Identidad, datos, infraestructura, plataformas
4. **Detectar (DE)** — Monitoreo continuo, análisis de eventos
5. **Responder (RS)** — Gestión de incidentes, comunicación, mitigación
6. **Recuperar (RC)** — Planes de recuperación, comunicación post-incidente

Con **ISO/IEC 27001:2022** como marco de referencia complementario.

La escala de madurez que usé es de 5 niveles:

| Nivel | Nombre | Descripción |
|-------|--------|-------------|
| 1 | Inicial | Sin procesos formales. Actividades ad hoc. |
| 2 | Gestionado | Procesos básicos definidos pero no documentados formalmente. |
| 3 | Definido | Procesos documentados, comunicados y ejecutados consistentemente. |
| 4 | Gestionado cuantitativamente | Procesos medidos con métricas. |
| 5 | Optimizado | Mejora continua basada en datos. |

---

## Los resultados del caso de estudio

**Recordatorio: estos resultados son del caso ficticio. No representan a la banca guatemalteca.**

### Madurez por dominio (caso de estudio)

| Dominio | Actual | Target | Gap |
|---------|--------|--------|-----|
| Gobernar (GV) | 1.7 | 3.8 | -2.1 |
| Identificar (ID) | 1.7 | 3.7 | -2.0 |
| Proteger (PR) | 2.0 | 4.0 | -2.0 |
| Detectar (DE) | 1.5 | 4.0 | -2.5 |
| Responder (RS) | 1.7 | 4.0 | -2.3 |
| Recuperar (RC) | 1.5 | 4.0 | -2.5 |
| **Promedio** | **1.7** | **3.9** | **-2.2** |

> **[INSERTAR IMAGEN: Dashboard de madurez]**
> *Archivo: dashboard-banco-del-lago.png*
> *Descripción: Dashboard completo con KPIs, gráficas de madurez por dominio, distribución de hallazgos, e inversión por horizonte.*

### Los 5 hallazgos más críticos (caso de estudio)

1. **No existe CISO formal.** La función está repartida entre TI y Riesgos. Sin un líder con autoridad, presupuesto y rendición de cuentas al Consejo, las otras 39 brechas no tienen quien las cierre.

2. **No hay MFA en canales electrónicos.** Incumplimiento directo de la JM-99-2025. El incidente de fraude explotó esta debilidad.

3. **No hay visibilidad de endpoints.** Sin EDR ni Sysmon. Los ataques en estaciones de trabajo son invisibles.

4. **DRP no probado en 18 meses.** El banco tiene un centro de cómputo alterno, pero no sabe si funciona. Un DRP no probado es un DRP que no existe.

5. **No hay plan de respuesta a incidentes.** Crisis sin guion. Sin roles, sin escalamiento, sin playbooks.

> **[INSERTAR IMAGEN: Tabla de los 5 hallazgos más críticos]**
> *Archivo: tabla-top5-hallazgos.png*
> *Descripción: Tabla con los 5 hallazgos más críticos, su dominio correspondiente, y el impacto en el negocio.*

---

## El hallazgo central del ejercicio: sin CISO

En el caso de estudio, el banco tiene actividades de seguridad, pero no tiene estructura.

**No hay Oficial de Seguridad de la Información (CISO).** La función está repartida entre la Gerencia de TI y la Unidad de Riesgos. Eso significa:

- No hay autoridad formal para tomar decisiones de seguridad.
- No hay presupuesto dedicado a seguridad.
- No hay rendición de cuentas al Consejo.
- No hay un líder que traduzca el riesgo técnico en riesgo de negocio.

**Lo que este ejercicio demuestra:** las otras 39 brechas existen porque no hay quien las lidere. Ese es el patrón que el framework expone cuando lo aplicas con rigor.

---

## El gap entre detección y respuesta

Uno de los hallazgos más interesantes del ejercicio fue el **gap entre tener un SOC tercerizado y tener capacidad real de detección y respuesta**.

En el caso de estudio, el banco tiene un **MDR (Managed Detection and Response)** que monitorea los sistemas críticos. Pero:

- **No hay correlación con el contexto del banco.** El MDR genera alertas, pero no las traduce al negocio.
- **No hay umbrales de severidad definidos por el banco.** El MDR usa sus propios criterios.
- **No hay integración entre el MDR y el equipo interno de TI.** Las alertas llegan por email, sin seguimiento estructurado.
- **No hay métricas de detección (TTD — Time To Detect).**
- **No hay un proceso formal de triaje de alertas.**

**El reto real no es la tecnología. Es la integración con el equipo interno de TI, que es quien tiene el contexto del negocio.**

> **[INSERTAR IMAGEN: Tabla del gap detección/respuesta]**
> *Archivo: tabla-gap-deteccion-respuesta.png*
> *Descripción: Tabla que compara el estado actual del caso de estudio (MDR sin integración, sin métricas) contra el estado objetivo (SOC integrado, con TTD < 30 min).*

---

## El plan de remediación (caso de estudio)

Estructuré el plan en **3 horizontes**:

### Horizonte 1: Quick Wins (0-90 días)

**Inversión: Q215,000**

| Acción | Inversión |
|--------|-----------|
| MFA en canales electrónicos | Q50,000 |
| Sysmon + Wazuh en endpoints | Q30,000 |
| Monitoreo de canales electrónicos | Q20,000 |
| Plan de respuesta a incidentes | Q20,000 |
| Prueba del DRP | Q15,000 |
| Concientización y simulacros | Q15,000 |
| Clasificación de proveedores | Q15,000 |
| Evaluación de riesgo cibernético | Q15,000 |
| Plan de comunicación post-incidente | Q10,000 |
| RTO/RPO documentados | Q10,000 |
| Otros | Q15,000 |

**Resultado:** Cierre de 16 brechas críticas en 90 días.

### Horizonte 2: Trabajo Estructural (3-6 meses)

**Inversión: Q700,000**

| Acción | Inversión |
|--------|-----------|
| CISO (anual) | Q600,000 |
| EDR en endpoints | Q120,000 |
| PAM | Q80,000 |
| Clasificación y DLP | Q60,000 |
| Backups inmutables | Q50,000 |
| SIEM propio (Wazuh) | Q50,000 |
| Pruebas de penetración | Q50,000 |
| Otros | Q240,000 |

**Resultado:** Implementación de controles faltantes. Cumplimiento regulatorio.

### Horizonte 3: Madurez (6-18 meses)

**Inversión: Q415,000**

| Acción | Inversión |
|--------|-----------|
| SOAR | Q100,000 |
| Pruebas de penetración avanzadas | Q80,000 |
| Auditoría interna | Q50,000 |
| Preparación ISO 27001 | Q50,000 |
| Auditoría de certificación | Q45,000 |
| Simulacros anuales | Q50,000 |
| Otros | Q40,000 |

**Resultado:** Madurez ≥ 3.5. Certificación ISO 27001.

> **[INSERTAR IMAGEN: Tabla del plan de remediación]**
> *Archivo: tabla-plan-remediacion.png*
> *Descripción: Tabla con los 3 horizontes, sus plazos, enfoque, inversión total, y el detalle de las acciones principales.*

### Inversión total (caso de estudio)

| Horizonte | Plazo | Inversión |
|-----------|-------|-----------|
| Horizonte 1 | 0-90 días | Q215,000 |
| Horizonte 2 | 3-6 meses | Q700,000 |
| Horizonte 3 | 6-18 meses | Q415,000 |
| **Total** | **18 meses** | **Q1,330,000** |

**Nota:** el CISO (Q600,000/año) es el 45% de la inversión total del caso. Sin ese rol, el plan no se ejecuta.

---

## Lo que este ejercicio enseña (más allá del caso)

**El valor de este ejercicio no está en los números. Está en el método.**

Lo que aprendí al aplicarlo:

1. **La gobernanza es la brecha raíz.** Si no hay CISO, no hay quien priorice, presupueste, ni rinda cuentas. Las brechas técnicas son consecuencia, no causa.

2. **La visibilidad es prerequisito de todo.** Sin inventario de activos, sin logs, sin correlación, no hay detección posible. Y sin detección, la respuesta es reactiva.

3. **Un DRP no probado es un DRP que no existe.** La diferencia entre tener un plan y tener un plan validado es la diferencia entre teoría y capacidad real.

4. **El gap entre SOC tercerizado y capacidad interna de respuesta es real.** Tener un MDR no es lo mismo que tener capacidad de detección y respuesta integrada con el negocio.

5. **El framework funciona.** NIST CSF 2.0 da la estructura. ISO 27001:2022 da los controles. La combinación permite evaluar madurez, priorizar brechas, y construir un roadmap defendible ante un comité de riesgos.

---

## El artefacto completo

El informe completo del caso de estudio, con el Gap Analysis de los 6 dominios, el plan de remediación, la presentación ejecutiva, y el dashboard de madurez, está en GitHub:

[enlace al repositorio]

Incluye:

- Gap Analysis completo (6 dominios, 40 hallazgos)
- Plan de remediación (3 horizontes)
- Presentación ejecutiva (15 slides)
- Dashboard de madurez (HTML + Chart.js)
- Documento de alcance del proyecto
- Glosario de términos

---

## Una nota final sobre los datos

Este ejercicio usa datos públicos de Banco Promerica de Guatemala como base para construir un perfil realista. **Banco Promerica es un banco real. Banco del Lago no lo es.** El +15% aplicado es una decisión de diseño del caso de estudio, no un dato de mercado.

Toda cifra está etiquetada en el documento original como **[VERIFICADO]**, **[ESTIMADO]** o **[SUPUESTO]**. Esa trazabilidad es intencional: un Gap Analysis sin supuestos explícitos no es auditable.

**Si algo queda claro de este artículo, que sea esto:** los resultados (1.7/5.0, 40 hallazgos, Q1,330,000) son del caso de estudio ficticio. No son un diagnóstico del sector. No son una predicción. Son una demostración de cómo se aplica el método.

---

*Walter Gómez es especialista en infraestructura y seguridad, con más de 20 años de experiencia en Linux y Red Hat. ISO 27001 Lead Implementer y DevSecOps Engineer. Este artículo documenta un ejercicio de aplicación de metodología a un caso de estudio ficticio.*
