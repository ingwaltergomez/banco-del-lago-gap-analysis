# Gap Analysis — Dominio 2: Identificar (ID)
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Descripción del dominio

La función **Identificar (ID)** del NIST CSF 2.0 desarrolla el entendimiento organizacional para gestionar el riesgo de ciberseguridad. Cubre la gestión de activos, la evaluación de riesgo, y la mejora continua.

Sin identificación, no hay protección. No puedes proteger lo que no sabes que tienes. No puedes gestionar un riesgo que no has evaluado. No puedes mejorar lo que no mides.

### Categorías del dominio ID

| Categoría | Nombre | Qué evalúa |
|-----------|--------|------------|
| **ID.AM** | Gestión de activos | Inventario de hardware, software, datos, servicios y proveedores |
| **ID.RA** | Evaluación de riesgo | Identificación de amenazas, vulnerabilidades, y análisis de impacto |
| **ID.IM** | Mejora continua | Lecciones aprendidas de incidentes y evaluaciones anteriores |

---

## 2. Evaluación de madurez

### Puntuación por categoría

| Categoría | Estado actual | Target | Gap |
|-----------|---------------|--------|-----|
| **ID.AM** — Gestión de activos | 2 | 4 | -2 |
| **ID.RA** — Evaluación de riesgo | 2 | 4 | -2 |
| **ID.IM** — Mejora continua | 1 | 3 | -2 |
| **Promedio del dominio** | **1.7** | **3.7** | **-2.0** |

**Interpretación:** El dominio Identificar está en nivel **Gestionado bajo (1.7)**, igual que Gobernar. El banco tiene algún entendimiento de sus activos y riesgos, pero **no está documentado, no es sistemático, y no alimenta la toma de decisiones**.

---

## 3. Hallazgos por categoría

### 3.1 ID.AM — Gestión de activos

**Estado actual (Nivel 2):**

- La Gerencia de TI mantiene un inventario parcial de servidores y equipos de red en una hoja de cálculo de Excel.
- El inventario **no incluye**: bases de datos, servicios en la nube, endpoints de usuarios, dispositivos móviles, ni proveedores.
- No hay dueños de activos asignados formalmente.
- No hay clasificación de criticidad de activos.
- El inventario no se actualiza de forma sistemática. La última actualización fue hace 8 meses.
- No hay inventario de software ni gestión de licencias.

**Hallazgo ID.AM-01:** El inventario de activos es parcial, desactualizado, y no cubre todos los tipos de activos.

**Hallazgo ID.AM-02:** No hay dueños de activos asignados ni clasificación de criticidad.

**Hallazgo ID.AM-03:** No existe inventario de software ni gestión de licencias.

**Brecha:** Falta un inventario completo, actualizado, con dueños y clasificación de criticidad, que cubra hardware, software, datos, servicios y proveedores.

**Recomendación:** Implementar una herramienta de descubrimiento automatizado de activos (puede ser open source como GLPI o NetBox) y establecer un proceso trimestral de actualización. Asignar dueños y clasificar criticidad de cada activo.

---

### 3.2 ID.RA — Evaluación de riesgo

**Estado actual (Nivel 2):**

- La Unidad de Administración de Riesgos evalúa riesgo operacional anualmente, pero **el riesgo cibernético no está formalmente integrado** en esa evaluación.
- No hay una evaluación de riesgo cibernético documentada.
- No hay análisis de amenazas ni de vulnerabilidades.
- No hay escenarios de riesgo documentados (ej. ransomware, fraude electrónico, fuga de datos).
- No hay cuantificación financiera del riesgo cibernético.
- La JM-98-2025 exige evaluación de riesgo tecnológico, pero el banco no la ha completado.

**Hallazgo ID.RA-01:** No existe evaluación de riesgo cibernético documentada.

**Hallazgo ID.RA-02:** No hay análisis de amenazas ni de vulnerabilidades.

**Hallazgo ID.RA-03:** No hay cuantificación financiera del riesgo cibernético.

**Brecha:** Falta una evaluación de riesgo cibernético formal, con identificación de amenazas, vulnerabilidades, análisis de impacto, y cuantificación financiera (ALE).

**Recomendación:** Realizar una evaluación de riesgo cibernético usando la metodología cuantitativa:
- `Riesgo = AV × (TL × VE)`
- `ALE = SLE × ARO`
- Priorizar los 10 riesgos más críticos.
- Presentar resultados al Comité de Riesgos.

---

### 3.3 ID.IM — Mejora continua

**Estado actual (Nivel 1):**

- No hay proceso formal de lecciones aprendidas después de incidentes.
- No hay evaluación post-incidente documentada.
- No hay métricas de mejora (ej. reducción de vulnerabilidades, mejora en tiempo de detección).
- Los incidentes se resuelven, pero **no se documentan ni se analizan para prevenir recurrencia**.
- No hay un ciclo de mejora continua (PDCA) para el programa de seguridad.

**Hallazgo ID.IM-01:** No existe proceso de lecciones aprendidas post-incidente.

**Hallazgo ID.IM-02:** No hay métricas de mejora continua del programa de seguridad.

**Brecha:** Falta un proceso formal de mejora continua, con lecciones aprendidas, métricas, y ciclos de revisión.

**Recomendación:** Implementar:
- Proceso de lecciones aprendidas post-incidente (obligatorio para incidentes de severidad alta).
- Revisión trimestral del programa de seguridad.
- Métricas de mejora (ej. reducción de vulnerabilidades críticas, mejora en tiempo de detección).
- Ciclo PDCA documentado.

---

## 4. Resumen de hallazgos

| ID | Categoría | Hallazgo | Nivel | Severidad |
|----|-----------|----------|-------|-----------|
| ID.AM-01 | Gestión de activos | Inventario parcial y desactualizado | 2 | Alta |
| ID.AM-02 | Gestión de activos | Sin dueños ni clasificación de criticidad | 2 | Alta |
| ID.AM-03 | Gestión de activos | Sin inventario de software | 2 | Media |
| ID.RA-01 | Evaluación de riesgo | Sin evaluación de riesgo cibernético | 2 | **Crítica** |
| ID.RA-02 | Evaluación de riesgo | Sin análisis de amenazas/vulnerabilidades | 2 | Alta |
| ID.RA-03 | Evaluación de riesgo | Sin cuantificación financiera | 2 | Alta |
| ID.IM-01 | Mejora continua | Sin lecciones aprendidas post-incidente | 1 | Alta |
| ID.IM-02 | Mejora continua | Sin métricas de mejora | 1 | Media |

---

## 5. Recomendaciones priorizadas

### Quick wins (implementables en 90 días)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 1 | Completar inventario de activos con dueños y criticidad | Alto | Q0 (interno) |
| 2 | Iniciar evaluación de riesgo cibernético de los 10 activos más críticos | **Crítico** | Q15,000 (consultoría) |
| 3 | Implementar proceso de lecciones aprendidas post-incidente | Medio | Q0 (interno) |

### Trabajo estructural (3-6 meses)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 4 | Implementar herramienta de descubrimiento de activos | Alto | Q20,000 (implementación) |
| 5 | Completar evaluación de riesgo cibernético con cuantificación financiera | **Crítico** | Q40,000 (consultoría) |
| 6 | Implementar métricas de mejora continua | Medio | Q10,000 (implementación) |
| 7 | Definir y documentar escenarios de riesgo | Alto | Q15,000 (consultoría) |

### Inversión total estimada

| Concepto | Costo |
|----------|-------|
| Quick wins | Q15,000 |
| Trabajo estructural | Q85,000 |
| **Total** | **Q100,000** |

---

## 6. Conclusión del dominio

El dominio **Identificar (ID)** tiene dos brechas críticas:

1. **No hay evaluación de riesgo cibernético.** El banco no sabe cuánto riesgo tiene, ni cuáles son sus riesgos más críticos. Eso es un problema regulatorio (JM-98-2025 lo exige) y un problema de negocio (no puede priorizar inversiones).

2. **No hay inventario completo de activos.** No puedes proteger lo que no sabes que tienes. El inventario parcial de Excel no cubre bases de datos, servicios en la nube, ni endpoints.

**Prioridad:** Completar el inventario de activos y la evaluación de riesgo cibernético antes de avanzar a los dominios técnicos (Proteger, Detectar, Responder, Recuperar).

---

## 7. Próximo dominio

**Dominio 3: Proteger (PR)** — Evaluación de gestión de identidad, protección de datos, y seguridad de infraestructura.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
