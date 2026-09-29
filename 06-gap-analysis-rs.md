# Gap Analysis — Dominio 5: Responder (RS)
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Descripción del dominio

La función **Responder (RS)** del NIST CSF 2.0 define las actividades para tomar acción respecto a un incidente de ciberseguridad detectado. Cubre la gestión de incidentes, la comunicación, el análisis, la mitigación, y la mejora.

Sin respuesta, un incidente detectado se convierte en una crisis. Puedes detectar un ransomware a tiempo, pero si no tienes un plan de respuesta, el daño se propaga.

### Categorías del dominio RS

| Categoría | Nombre | Qué evalúa |
|-----------|--------|------------|
| **RS.MA** | Gestión de incidentes | Proceso formal de respuesta, roles, escalamiento |
| **RS.AN** | Análisis de incidentes | Investigación, causa raíz, forense |
| **RS.CO** | Comunicación | Comunicación interna, externa, con reguladores |
| **RS.MI** | Mitigación | Contención, erradicación, recuperación |

---

## 2. Evaluación de madurez

### Puntuación por categoría

| Categoría | Estado actual | Target | Gap |
|-----------|---------------|--------|-----|
| **RS.MA** — Gestión de incidentes | 2 | 4 | -2 |
| **RS.AN** — Análisis de incidentes | 1 | 4 | -3 |
| **RS.CO** — Comunicación | 2 | 4 | -2 |
| **RS.MI** — Mitigación | 2 | 4 | -2 |
| **Promedio del dominio** | **1.7** | **4.0** | **-2.3** |

**Interpretación:** El dominio Responder está en nivel **Gestionado bajo (1.7)**, similar a Gobernar e Identificar. El banco responde a incidentes, pero **sin proceso formal, sin análisis forense, y sin comunicación estructurada**.

---

## 3. Hallazgos por categoría

### 3.1 RS.MA — Gestión de incidentes

**Estado actual (Nivel 2):**

- El MDR notifica incidentes por email al equipo de TI.
- **No hay un proceso formal de respuesta a incidentes documentado.**
- No hay roles definidos para respuesta a incidentes.
- No hay un plan de escalamiento. Si el incidente es grave, no se sabe quién debe ser notificado ni en qué orden.
- No hay un registro centralizado de incidentes.
- No hay un playbook de respuesta para escenarios comunes (ransomware, fraude, fuga de datos).

**Hallazgo RS.MA-01:** No existe un plan formal de respuesta a incidentes.

**Hallazgo RS.MA-02:** No hay roles ni escalamiento definidos.

**Hallazgo RS.MA-03:** No hay playbooks de respuesta para escenarios comunes.

**Brecha:** Falta un plan de respuesta a incidentes con roles, escalamiento, playbooks, y registro centralizado.

**Recomendación:** Implementar:
- Plan de respuesta a incidentes documentado.
- Roles definidos (Incident Manager, Analista, Comunicaciones, Legal).
- Playbooks para escenarios comunes: ransomware, fraude electrónico, fuga de datos, DDoS.
- Registro centralizado de incidentes (puede ser TheHive, open source).

---

### 3.2 RS.AN — Análisis de incidentes

**Estado actual (Nivel 1):**

- **No hay capacidad de análisis forense interna.**
- El MDR investiga los incidentes, pero el banco no tiene visibilidad del análisis.
- No hay documentación de causa raíz.
- No hay análisis post-incidente.
- No hay herramientas forenses (ni comerciales ni open source).
- Los incidentes se resuelven, pero no se documentan para aprender de ellos.

**Hallazgo RS.AN-01:** No hay capacidad de análisis forense interna.

**Hallazgo RS.AN-02:** No hay documentación de causa raíz ni análisis post-incidente.

**Hallazgo RS.AN-03:** No hay herramientas forenses disponibles.

**Brecha:** Falta capacidad de análisis forense, documentación de causa raíz, y análisis post-incidente.

**Recomendación:** Implementar:
- Capacidad de análisis forense (al menos básica): Wireshark, Volatility, Autopsy.
- Proceso de documentación de causa raíz obligatorio para incidentes de severidad alta.
- Análisis post-incidente con lecciones aprendidas.
- Integración con el MDR para recibir el análisis detallado.

---

### 3.3 RS.CO — Comunicación

**Estado actual (Nivel 2):**

- Hay comunicación informal entre TI, Riesgos, y el MDR.
- **No hay un plan de comunicación de crisis.**
- No hay protocolo de comunicación con la SIB en caso de incidente grave.
- No hay protocolo de comunicación con clientes afectados.
- No hay portavoz designado para comunicaciones externas.
- No hay plantillas de comunicación pre-aprobadas.

**Hallazgo RS.CO-01:** No hay plan de comunicación de crisis.

**Hallazgo RS.CO-02:** No hay protocolo de comunicación con la SIB ni con clientes.

**Hallazgo RS.CO-03:** No hay portavoz designado ni plantillas de comunicación.

**Brecha:** Falta un plan de comunicación de crisis con protocolos para reguladores, clientes, y medios.

**Recomendación:** Implementar:
- Plan de comunicación de crisis.
- Protocolo de notificación a la SIB (plazos regulatorios, formato, responsables).
- Protocolo de comunicación con clientes afectados.
- Portavoz designado (probablemente el Gerente General o el CISO).
- Plantillas de comunicación pre-aprobadas por Legal.

---

### 3.4 RS.MI — Mitigación

**Estado actual (Nivel 2):**

- El equipo de TI contiene incidentes de forma reactiva, sin proceso documentado.
- No hay procedimientos de contención definidos (ej. aislar un servidor, bloquear una IP).
- No hay procedimientos de erradicación (ej. eliminar malware, cerrar vulnerabilidades).
- No hay coordinación formal con el MDR para la mitigación.
- La recuperación de sistemas se hace de forma manual, sin procedimiento documentado.

**Hallazgo RS.MI-01:** No hay procedimientos documentados de contención y erradicación.

**Hallazgo RS.MI-02:** No hay coordinación formal con el MDR para mitigación.

**Hallazgo RS.MI-03:** La recuperación se hace de forma manual, sin procedimiento documentado.

**Brecha:** Falta procedimientos de contención, erradicación, y recuperación documentados.

**Recomendación:** Implementar:
- Procedimientos de contención (aislamiento de sistemas, bloqueo de IPs, desactivación de cuentas).
- Procedimientos de erradicación (eliminación de malware, cierre de vulnerabilidades).
- Procedimientos de recuperación (restauración desde backup, validación de integridad).
- Coordinación formal con el MDR para mitigación.

---

## 4. Resumen de hallazgos

| ID | Categoría | Hallazgo | Nivel | Severidad |
|----|-----------|----------|-------|-----------|
| RS.MA-01 | Gestión de incidentes | Sin plan formal de respuesta | 2 | **Crítica** |
| RS.MA-02 | Gestión de incidentes | Sin roles ni escalamiento | 2 | Alta |
| RS.MA-03 | Gestión de incidentes | Sin playbooks de respuesta | 2 | Alta |
| RS.AN-01 | Análisis de incidentes | Sin capacidad forense interna | 1 | **Crítica** |
| RS.AN-02 | Análisis de incidentes | Sin documentación de causa raíz | 1 | Alta |
| RS.AN-03 | Análisis de incidentes | Sin herramientas forenses | 1 | Media |
| RS.CO-01 | Comunicación | Sin plan de comunicación de crisis | 2 | **Crítica** |
| RS.CO-02 | Comunicación | Sin protocolo con SIB ni clientes | 2 | **Crítica** |
| RS.CO-03 | Comunicación | Sin portavoz ni plantillas | 2 | Alta |
| RS.MI-01 | Mitigación | Sin procedimientos de contención | 2 | Alta |
| RS.MI-02 | Mitigación | Sin coordinación con MDR | 2 | Media |
| RS.MI-03 | Mitigación | Sin procedimiento de recuperación | 2 | Alta |

---

## 5. Recomendaciones priorizadas

### Quick wins (implementables en 90 días)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 1 | Redactar plan de respuesta a incidentes | **Crítico** | Q20,000 (consultoría) |
| 2 | Definir protocolo de notificación a la SIB | **Crítico** | Q0 (interno + legal) |
| 3 | Designar portavoz y crear plantillas de comunicación | Alto | Q0 (interno) |
| 4 | Establecer coordinación formal con MDR | Alto | Q0 (interno) |

### Trabajo estructural (3-6 meses)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 5 | Implementar capacidad forense básica (Wireshark, Volatility, Autopsy) | Alto | Q15,000 (herramientas + capacitación) |
| 6 | Desarrollar playbooks para escenarios comunes | Alto | Q30,000 (consultoría) |
| 7 | Implementar TheHive para registro de incidentes | Medio | Q20,000 (implementación) |
| 8 | Documentar procedimientos de contención y recuperación | Alto | Q20,000 (consultoría) |
| 9 | Simulacro anual de respuesta a incidentes | Alto | Q15,000 (facilitación) |

### Inversión total estimada

| Concepto | Costo |
|----------|-------|
| Quick wins | Q20,000 |
| Trabajo estructural | Q100,000 |
| **Total** | **Q120,000** |

---

## 6. Conclusión del dominio

El dominio **Responder (RS)** tiene tres brechas críticas:

1. **No hay plan formal de respuesta a incidentes.** El banco responde de forma reactiva, sin roles, sin escalamiento, sin playbooks. Eso significa que cada incidente se maneja como si fuera la primera vez.

2. **No hay capacidad de análisis forense interna.** El MDR investiga, pero el banco no tiene visibilidad ni capacidad de análisis propio. Eso limita la capacidad de aprender de los incidentes.

3. **No hay plan de comunicación de crisis.** Si ocurre un incidente grave, el banco no sabe cómo comunicarse con la SIB, con los clientes, ni con los medios. Eso es un riesgo reputacional y regulatorio.

**Prioridad:** Plan de respuesta, protocolo de comunicación con la SIB, y capacidad forense básica antes de avanzar al dominio de recuperación.

---

## 7. Próximo dominio

**Dominio 6: Recuperar (RC)** — Evaluación de planes de recuperación y comunicación post-incidente.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
