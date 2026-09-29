# Gap Analysis — Dominio 1: Gobernar (GV)
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Descripción del dominio

La función **Gobernar (GV)** del NIST CSF 2.0 establece y monitorea la estrategia, las expectativas y la política de gestión de riesgo de ciberseguridad de la organización. Es la función que **da dirección, autoridad y supervisión** a todo el programa de seguridad.

Sin gobernanza, las otras cinco funciones (Identificar, Proteger, Detectar, Responder, Recuperar) operan sin rumbo, sin presupuesto, y sin rendición de cuentas.

### Categorías del dominio GV

| Categoría | Nombre | Qué evalúa |
|-----------|--------|------------|
| **GV.OC** | Contexto organizacional | Entendimiento del entorno, misión, partes interesadas y requisitos legales/regulatorios |
| **GV.RM** | Estrategia de gestión de riesgo | Prioridades, tolerancia al riesgo, apetito de riesgo |
| **GV.RR** | Roles, responsabilidades y autoridades | Asignación clara de responsabilidades de ciberseguridad |
| **GV.PO** | Políticas, procesos y procedimientos | Políticas de ciberseguridad documentadas y comunicadas |
| **GV.OV** | Supervisión | Monitoreo del desempeño del programa de seguridad |
| **GV.SC** | Gestión de riesgo de cadena de suministro | Riesgo de proveedores y terceros |

---

## 2. Evaluación de madurez

### Escala de madurez utilizada

| Nivel | Nombre | Descripción |
|-------|--------|-------------|
| **1** | Inicial | Sin procesos formales. Actividades ad hoc. |
| **2** | Gestionado | Procesos básicos definidos pero no documentados formalmente. |
| **3** | Definido | Procesos documentados, comunicados y ejecutados consistentemente. |
| **4** | Gestionado cuantitativamente | Procesos medidos con métricas. |
| **5** | Optimizado | Mejora continua basada en datos. |

### Puntuación por categoría

| Categoría | Estado actual | Target | Gap |
|-----------|---------------|--------|-----|
| **GV.OC** — Contexto organizacional | 2 | 4 | -2 |
| **GV.RM** — Estrategia de gestión de riesgo | 2 | 4 | -2 |
| **GV.RR** — Roles y responsabilidades | 1 | 4 | -3 |
| **GV.PO** — Políticas y procedimientos | 2 | 4 | -2 |
| **GV.OV** — Supervisión | 2 | 3 | -1 |
| **GV.SC** — Cadena de suministro | 1 | 4 | -3 |
| **Promedio del dominio** | **1.7** | **3.8** | **-2.1** |

**Interpretación:** El dominio Gobernar está en nivel **Gestionado bajo (1.7)**, con brechas críticas en roles (GV.RR) y cadena de suministro (GV.SC). Eso significa que el banco tiene actividades de seguridad, pero **no tiene una estructura formal que las dirija, mida ni supervise**.

---

## 3. Hallazgos por categoría

### 3.1 GV.OC — Contexto organizacional

**Estado actual (Nivel 2):**

- El banco entiende su misión y su rol en el sistema financiero guatemalteco.
- La Unidad de Administración de Riesgos tiene identificados los requisitos regulatorios principales (JM-98-2025, JM-91-2024, JM-62-2016).
- **Pero no existe un documento formal que articule el contexto organizacional en términos de ciberseguridad.**
- Las partes interesadas (Consejo, Comité de Riesgos, clientes, regulador) están identificadas, pero sus expectativas de ciberseguridad no están documentadas.

**Hallazgo GV.OC-01:** No existe un documento de contexto organizacional de ciberseguridad que conecte la misión del banco con los requisitos de seguridad.

**Brecha:** Falta un documento formal que articule misión, partes interesadas, requisitos legales y regulatorios, y expectativas de ciberseguridad.

**Recomendación:** Crear un documento de "Contexto Organizacional de Ciberseguridad" que sirva como base para el SGSI y para el mapeo a ISO/IEC 27001:2022 (cláusula 4).

---

### 3.2 GV.RM — Estrategia de gestión de riesgo

**Estado actual (Nivel 2):**

- La Unidad de Administración de Riesgos gestiona riesgo operacional y de crédito, pero **el riesgo cibernético no está formalmente integrado en esa gestión**.
- No existe una declaración de apetito de riesgo cibernético aprobada por el Consejo.
- No hay prioridades de riesgo documentadas ni tolerancia al riesgo definida.

**Hallazgo GV.RM-01:** No existe una declaración de apetito de riesgo cibernético aprobada por el Consejo de Administración.

**Brecha:** Falta una declaración formal de apetito y tolerancia al riesgo cibernético, aprobada por el Consejo y comunicada a toda la organización.

**Recomendación:** Redactar y presentar al Consejo una "Declaración de Apetito de Riesgo Cibernético" que defina:
- Umbrales de tolerancia (ej. pérdida máxima aceptable por incidente).
- Prioridades de riesgo (ej. proteger canales electrónicos primero).
- Criterios de aceptación de riesgo residual.

---

### 3.3 GV.RR — Roles, responsabilidades y autoridades

**Estado actual (Nivel 1):**

- **No existe un CISO formal.** La función de seguridad de la información está repartida entre la Gerencia de TI y la Unidad de Riesgos.
- Las responsabilidades de ciberseguridad no están documentadas en descripciones de puesto.
- El Comité de Gestión de Riesgos tiene responsabilidad sobre riesgo tecnológico, pero no hay un rol dedicado a ciberseguridad que reporte directamente al Consejo.
- La autoridad para tomar decisiones de seguridad (ej. bloquear un despliegue, aislar un sistema) no está formalmente asignada.

**Hallazgo GV.RR-01:** No existe un Oficial de Seguridad de la Información (CISO) formal con autoridad y presupuesto.

**Hallazgo GV.RR-02:** Las responsabilidades de ciberseguridad no están documentadas ni asignadas formalmente.

**Brecha:** Falta una estructura organizacional de seguridad formal, con CISO, responsabilidades documentadas, y autoridad definida.

**Recomendación:** Formalizar la función de CISO con:
- Reporte directo al Consejo de Administración o al Comité de Riesgos.
- Presupuesto propio.
- Autoridad para vetar despliegues inseguros.
- Responsabilidad sobre el programa de seguridad, no solo sobre TI.

---

### 3.4 GV.PO — Políticas, procesos y procedimientos

**Estado actual (Nivel 2):**

- Existen políticas de seguridad de la información básicas (contraseñas, acceso a sistemas), pero **están desactualizadas y no cubren todos los dominios del CSF 2.0**.
- No hay una política de gestión de incidentes.
- No hay una política de clasificación de información.
- No hay una política de gestión de vulnerabilidades.
- La política de seguridad no ha sido revisada desde 2023.

**Hallazgo GV.PO-01:** Las políticas de seguridad están desactualizadas y no cubren todos los dominios del CSF 2.0.

**Brecha:** Falta un conjunto completo de políticas de seguridad alineadas al CSF 2.0 y a ISO/IEC 27001:2022.

**Recomendación:** Desarrollar o actualizar las políticas de:
- Gestión de incidentes
- Clasificación de información
- Gestión de vulnerabilidades
- Control de acceso
- Continuidad de negocio
- Gestión de proveedores

---

### 3.5 GV.OV — Supervisión

**Estado actual (Nivel 2):**

- El Comité de Gestión de Riesgos se reúne mensualmente y recibe reportes de riesgo operacional.
- **No recibe reportes específicos de ciberseguridad** (métricas, incidentes, vulnerabilidades).
- No hay KPIs de seguridad definidos.
- No hay un dashboard de seguridad para el Consejo.

**Hallazgo GV.OV-01:** El Comité de Riesgos no recibe reportes específicos de ciberseguridad.

**Brecha:** Falta un mecanismo formal de supervisión de ciberseguridad, con métricas y reportes periódicos al Consejo.

**Recomendación:** Definir e implementar:
- KPIs de seguridad (ej. tiempo medio de detección, número de vulnerabilidades críticas, incidentes por mes).
- Reporte mensual de ciberseguridad al Comité de Riesgos.
- Reporte trimestral al Consejo de Administración.

---

### 3.6 GV.SC — Gestión de riesgo de cadena de suministro

**Estado actual (Nivel 1):**

- **No existe un proceso formal de clasificación de criticidad de proveedores tecnológicos.**
- La JM-98-2025 exige esta clasificación antes de diciembre 2026–marzo 2027, pero el banco no ha iniciado el proceso.
- No hay cláusulas de seguridad en los contratos con proveedores críticos.
- No hay evaluación de riesgo de proveedores.

**Hallazgo GV.SC-01:** No existe clasificación de criticidad de proveedores tecnológicos, a pesar de la obligación regulatoria.

**Hallazgo GV.SC-02:** Los contratos con proveedores críticos no incluyen cláusulas de seguridad.

**Brecha:** Falta un programa de gestión de riesgo de cadena de suministro, con clasificación de proveedores, cláusulas contractuales, y evaluación continua.

**Recomendación:** Implementar:
- Clasificación de criticidad de los 6 proveedores críticos identificados.
- Cláusulas de seguridad obligatorias en contratos nuevos.
- Evaluación anual de riesgo de proveedores críticos.
- Plan de contingencia para proveedores de alto riesgo.

---

## 4. Resumen de hallazgos

| ID | Categoría | Hallazgo | Nivel | Severidad |
|----|-----------|----------|-------|-----------|
| GV.OC-01 | Contexto organizacional | No existe documento de contexto de ciberseguridad | 2 | Media |
| GV.RM-01 | Estrategia de riesgo | No existe declaración de apetito de riesgo | 2 | Alta |
| GV.RR-01 | Roles | No existe CISO formal | 1 | **Crítica** |
| GV.RR-02 | Roles | Responsabilidades no documentadas | 1 | Alta |
| GV.PO-01 | Políticas | Políticas desactualizadas e incompletas | 2 | Alta |
| GV.OV-01 | Supervisión | Sin reportes de ciberseguridad al Comité | 2 | Media |
| GV.SC-01 | Cadena de suministro | Sin clasificación de proveedores | 1 | **Crítica** |
| GV.SC-02 | Cadena de suministro | Sin cláusulas de seguridad en contratos | 1 | Alta |

---

## 5. Recomendaciones priorizadas

### Quick wins (implementables en 90 días)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 1 | Crear documento de contexto organizacional | Medio | Q0 (interno) |
| 2 | Definir KPIs de seguridad y reporte mensual al Comité | Medio | Q0 (interno) |
| 3 | Iniciar clasificación de los 6 proveedores críticos | Alto | Q15,000 (consultoría) |

### Trabajo estructural (3-6 meses)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 4 | Redactar declaración de apetito de riesgo | Alto | Q25,000 (consultoría) |
| 5 | Formalizar la función de CISO | **Crítico** | Q600,000/año (salario) |
| 6 | Desarrollar conjunto completo de políticas | Alto | Q40,000 (consultoría) |
| 7 | Incluir cláusulas de seguridad en contratos | Medio | Q0 (legal interno) |

### Inversión total estimada

| Concepto | Costo |
|----------|-------|
| Quick wins | Q15,000 |
| Trabajo estructural | Q665,000 |
| **Total** | **Q680,000** |

**Nota:** el costo del CISO (Q600,000/año) es el 88% de la inversión total. Sin ese rol, las demás acciones no tienen quien las lidere.

---

## 6. Conclusión del dominio

El dominio **Gobernar (GV)** es la brecha más crítica del banco. Sin CISO formal, sin apetito de riesgo definido, sin políticas actualizadas, y sin clasificación de proveedores, el banco **no tiene la estructura para dirigir su programa de seguridad**.

Las otras cinco funciones del CSF 2.0 (Identificar, Proteger, Detectar, Responder, Recuperar) dependen de que Gobernar funcione. Si no se cierra esta brecha primero, cualquier inversión en tecnología de seguridad será un parche sin dirección.

**Prioridad:** Formalizar el CISO y la declaración de apetito de riesgo antes de avanzar a los dominios técnicos.

---

## 7. Próximo dominio

**Dominio 2: Identificar (ID)** — Evaluación de gestión de activos, evaluación de riesgo, y mejora continua.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
