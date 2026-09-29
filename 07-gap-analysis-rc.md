# Gap Analysis — Dominio 6: Recuperar (RC)
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Descripción del dominio

La función **Recuperar (RC)** del NIST CSF 2.0 define las actividades para restaurar los activos y operaciones que se vieron afectados por un incidente de ciberseguridad. Cubre la ejecución del plan de recuperación y la comunicación post-incidente.

Sin recuperación, un incidente detectado y contenido sigue siendo una interrupción del negocio. Puedes contener un ransomware, pero si no puedes restaurar los sistemas, el banco no opera.

### Categorías del dominio RC

| Categoría | Nombre | Qué evalúa |
|-----------|--------|------------|
| **RC.RP** | Ejecución del plan de recuperación | Restauración de sistemas, datos, y servicios |
| **RC.CO** | Comunicación post-incidente | Comunicación con stakeholders después del incidente |

---

## 2. Evaluación de madurez

### Puntuación por categoría

| Categoría | Estado actual | Target | Gap |
|-----------|---------------|--------|-----|
| **RC.RP** — Ejecución del plan de recuperación | 2 | 4 | -2 |
| **RC.CO** — Comunicación post-incidente | 1 | 4 | -3 |
| **Promedio del dominio** | **1.5** | **4.0** | **-2.5** |

**Interpretación:** El dominio Recuperar está en nivel **Gestionado bajo (1.5)**, empatado con Detectar como el más bajo de todos. El banco tiene un centro de cómputo alterno, pero **el DRP no se prueba, no se documenta, y no se comunica**.

---

## 3. Hallazgos por categoría

### 3.1 RC.RP — Ejecución del plan de recuperación

**Estado actual (Nivel 2):**

- El banco tiene un **centro de cómputo alterno** fuera del área metropolitana.
- Hay **redundancia de enlaces de red** con dos proveedores.
- Hay **UPS y generador** en el centro de cómputo principal.
- **El DRP no se ha probado en los últimos 18 meses.**
- No hay métricas de RTO (Recovery Time Objective) ni RPO (Recovery Point Objective) documentadas.
- No hay procedimientos de recuperación documentados para sistemas críticos.
- No hay backups inmutables. Los backups pueden ser cifrados por ransomware.
- No hay un plan de recuperación escalonado (qué sistemas se restauran primero, en qué orden).
- No hay un equipo de recuperación designado.

**Hallazgo RC.RP-01:** El DRP no se ha probado en 18 meses.

**Hallazgo RC.RP-02:** No hay RTO ni RPO documentados.

**Hallazgo RC.RP-03:** No hay procedimientos de recuperación documentados.

**Hallazgo RC.RP-04:** No hay backups inmutables.

**Hallazgo RC.RP-05:** No hay plan de recuperación escalonado.

**Brecha:** Falta un DRP probado, con RTO/RPO documentados, procedimientos de recuperación, backups inmutables, y plan escalonado.

**Recomendación:** Implementar:
- Documentar RTO y RPO por sistema crítico.
- Documentar procedimientos de recuperación por sistema.
- Implementar backups inmutables (para prevenir cifrado por ransomware).
- Definir plan de recuperación escalonado (primero core bancario, luego canales, luego sistemas de soporte).
- Probar el DRP anualmente con métricas.
- Designar equipo de recuperación con roles definidos.

---

### 3.2 RC.CO — Comunicación post-incidente

**Estado actual (Nivel 1):**

- **No hay plan de comunicación post-incidente.**
- No hay protocolo de comunicación con clientes después de un incidente.
- No hay protocolo de comunicación con la SIB después de un incidente.
- No hay protocolo de comunicación con empleados.
- No hay protocolo de comunicación con medios.
- No hay lecciones aprendidas documentadas después de incidentes.
- No hay actualización del DRP basada en lecciones aprendidas.

**Hallazgo RC.CO-01:** No hay plan de comunicación post-incidente.

**Hallazgo RC.CO-02:** No hay protocolo con clientes, SIB, empleados, ni medios.

**Hallazgo RC.CO-03:** No hay lecciones aprendidas documentadas ni actualización del DRP.

**Brecha:** Falta un plan de comunicación post-incidente con protocolos para todos los stakeholders, y un proceso de lecciones aprendidas que actualice el DRP.

**Recomendación:** Implementar:
- Plan de comunicación post-incidente con protocolos para: clientes, SIB, empleados, medios.
- Plantillas de comunicación pre-aprobadas por Legal.
- Proceso de lecciones aprendidas post-incidente.
- Actualización del DRP basada en lecciones aprendidas.
- Revisión anual del plan de comunicación.

---

## 4. Resumen de hallazgos

| ID | Categoría | Hallazgo | Nivel | Severidad |
|----|-----------|----------|-------|-----------|
| RC.RP-01 | Recuperación | DRP no probado en 18 meses | 2 | **Crítica** |
| RC.RP-02 | Recuperación | Sin RTO ni RPO documentados | 2 | **Crítica** |
| RC.RP-03 | Recuperación | Sin procedimientos de recuperación | 2 | Alta |
| RC.RP-04 | Recuperación | Sin backups inmutables | 2 | **Crítica** |
| RC.RP-05 | Recuperación | Sin plan de recuperación escalonado | 2 | Alta |
| RC.CO-01 | Comunicación post-incidente | Sin plan de comunicación post-incidente | 1 | **Crítica** |
| RC.CO-02 | Comunicación post-incidente | Sin protocolos con stakeholders | 1 | Alta |
| RC.CO-03 | Comunicación post-incidente | Sin lecciones aprendidas ni actualización del DRP | 1 | Alta |

---

## 5. Recomendaciones priorizadas

### Quick wins (implementables en 90 días)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 1 | Documentar RTO y RPO por sistema crítico | **Crítico** | Q10,000 (consultoría) |
| 2 | Probar el DRP | **Crítico** | Q15,000 (horas extra + facilitación) |
| 3 | Redactar plan de comunicación post-incidente | **Crítico** | Q10,000 (consultoría) |

### Trabajo estructural (3-6 meses)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 4 | Documentar procedimientos de recuperación por sistema | Alto | Q30,000 (consultoría) |
| 5 | Implementar backups inmutables | **Crítico** | Q50,000 (infraestructura) |
| 6 | Definir plan de recuperación escalonado | Alto | Q10,000 (consultoría) |
| 7 | Designar equipo de recuperación con roles | Medio | Q0 (interno) |
| 8 | Implementar proceso de lecciones aprendidas | Medio | Q10,000 (consultoría) |
| 9 | Capacitar al equipo en recuperación | Alto | Q20,000 (capacitación) |

### Inversión total estimada

| Concepto | Costo |
|----------|-------|
| Quick wins | Q35,000 |
| Trabajo estructural | Q120,000 |
| **Total** | **Q155,000** |

---

## 6. Conclusión del dominio

El dominio **Recuperar (RC)** tiene tres brechas críticas:

1. **El DRP no se ha probado en 18 meses.** El banco tiene un centro de cómputo alterno, pero no sabe si funciona. Un DRP no probado es un DRP que no existe.

2. **No hay RTO ni RPO documentados.** El banco no sabe cuánto tiempo puede estar caído un sistema crítico, ni cuánta data puede perder. Eso es un riesgo regulatorio (JM-98-2025 lo exige) y operativo.

3. **No hay backups inmutables.** Los backups pueden ser cifrados por ransomware. El incidente de 2023 (ransomware que cifró la bodega) demostró que el banco pagó el rescate porque no tenía backups inmutables.

**Prioridad:** Probar el DRP, documentar RTO/RPO, e implementar backups inmutables antes de considerar el programa de seguridad completo.

---

## 7. Resumen del Gap Analysis completo

Con los 6 dominios evaluados, el panorama es:

| Dominio | Madurez actual | Target | Gap |
|---------|----------------|--------|-----|
| **Gobernar (GV)** | 1.7 | 3.8 | -2.1 |
| **Identificar (ID)** | 1.7 | 3.7 | -2.0 |
| **Proteger (PR)** | 2.0 | 4.0 | -2.0 |
| **Detectar (DE)** | 1.5 | 4.0 | -2.5 |
| **Responder (RS)** | 1.7 | 4.0 | -2.3 |
| **Recuperar (RC)** | 1.5 | 4.0 | -2.5 |
| **Promedio general** | **1.7** | **3.9** | **-2.2** |

**El banco está en nivel "Gestionado bajo" en todos los dominios.** Tiene actividades de seguridad, pero no tiene estructura, no tiene métricas, y no tiene mejora continua.

---

## 8. Próxima fase

**Plan de remediación** con iniciativas priorizadas, responsables, plazos, y presupuesto. El plan se estructurará en 3 horizontes:

- **Horizonte 1 (0-90 días):** Quick wins. Cerrar brechas críticas de bajo costo.
- **Horizonte 2 (3-6 meses):** Trabajo estructural. Implementar controles faltantes.
- **Horizonte 3 (6-18 meses):** Madurez. Métricas, mejora continua, y preparación para certificación ISO 27001.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
