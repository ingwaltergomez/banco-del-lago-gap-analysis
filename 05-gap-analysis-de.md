# Gap Analysis — Dominio 4: Detectar (DE)
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Descripción del dominio

La función **Detectar (DE)** del NIST CSF 2.0 define las actividades para identificar la ocurrencia de un evento de ciberseguridad. Cubre el monitoreo continuo y el análisis de eventos adversos.

Sin detección, un ataque puede durar semanas o meses sin ser descubierto. El banco puede tener todos los controles de protección, pero si no detecta cuándo fallan, no puede responder.

### Categorías del dominio DE

| Categoría | Nombre | Qué evalúa |
|-----------|--------|------------|
| **DE.CM** | Monitoreo continuo | Monitoreo de redes, endpoints, y actividad de usuarios |
| **DE.AE** | Análisis de eventos adversos | Correlación, análisis, y declaración de incidentes |

---

## 2. Evaluación de madurez

### Puntuación por categoría

| Categoría | Estado actual | Target | Gap |
|-----------|---------------|--------|-----|
| **DE.CM** — Monitoreo continuo | 2 | 4 | -2 |
| **DE.AE** — Análisis de eventos adversos | 1 | 4 | -3 |
| **Promedio del dominio** | **1.5** | **4.0** | **-2.5** |

**Interpretación:** El dominio Detectar está en nivel **Gestionado bajo (1.5)**, el más bajo de todos los dominios evaluados hasta ahora. El banco tiene un SOC tercerizado, pero **sin visibilidad completa, sin correlación, y sin capacidad de análisis**.

---

## 3. Hallazgos por categoría

### 3.1 DE.CM — Monitoreo continuo

**Estado actual (Nivel 2):**

- El banco tiene un **SOC tercerizado (MDR)** que monitorea los sistemas críticos.
- El MDR recibe logs de: firewall perimetral, servidores críticos, y Active Directory.
- **No hay visibilidad de endpoints.** No hay EDR ni Sysmon desplegado en las estaciones de trabajo.
- **No hay visibilidad de red interna.** No hay IDS/IPS en la red interna.
- **No hay visibilidad de la nube.** Las cargas en nube pública no están monitoreadas.
- No hay SIEM propio. El MDR usa su propia plataforma, pero el banco no tiene acceso directo a los logs.
- No hay monitoreo de canales electrónicos (banca en línea, banca móvil).

**Hallazgo DE.CM-01:** No hay visibilidad de endpoints (sin EDR ni Sysmon).

**Hallazgo DE.CM-02:** No hay visibilidad de red interna (sin IDS/IPS).

**Hallazgo DE.CM-03:** No hay visibilidad de cargas en nube pública.

**Hallazgo DE.CM-04:** No hay monitoreo de canales electrónicos.

**Brecha:** Falta visibilidad completa de endpoints, red interna, nube, y canales electrónicos. El MDR actual solo cubre una fracción de la superficie de ataque.

**Recomendación:** Implementar:
- EDR en endpoints críticos y estaciones de trabajo.
- Sysmon + Wazuh para visibilidad de endpoints.
- Suricata o Zeek para visibilidad de red interna.
- Monitoreo de canales electrónicos (logs de banca en línea y móvil).
- SIEM propio (Wazuh) que consolide todos los logs, aunque el MDR siga operando.

---

### 3.2 DE.AE — Análisis de eventos adversos

**Estado actual (Nivel 1):**

- El MDR genera alertas, pero **no hay correlación con el contexto del banco**.
- No hay umbrales de severidad definidos por el banco. El MDR usa sus propios criterios.
- No hay análisis de causa raíz documentado para los incidentes.
- No hay métricas de detección (TTD — Time To Detect).
- No hay integración entre el MDR y el equipo interno de TI. Las alertas llegan por email, sin seguimiento estructurado.
- No hay un proceso formal de triaje de alertas.

**Hallazgo DE.AE-01:** No hay correlación de eventos con el contexto del banco.

**Hallazgo DE.AE-02:** No hay métricas de detección (TTD, tasa de falsos positivos).

**Hallazgo DE.AE-03:** No hay proceso formal de triaje de alertas.

**Brecha:** Falta un proceso de análisis de eventos que correlacione alertas, defina severidad, y mida efectividad de detección.

**Recomendación:** Implementar:
- Proceso formal de triaje de alertas (con SLA de respuesta).
- Correlación de eventos usando SIEM propio (Wazuh).
- Métricas de detección: TTD, tasa de falsos positivos, alertas por severidad.
- Integración estructurada entre MDR y TI interno.

---

## 4. Resumen de hallazgos

| ID | Categoría | Hallazgo | Nivel | Severidad |
|----|-----------|----------|-------|-----------|
| DE.CM-01 | Monitoreo continuo | Sin visibilidad de endpoints | 2 | **Crítica** |
| DE.CM-02 | Monitoreo continuo | Sin visibilidad de red interna | 2 | **Crítica** |
| DE.CM-03 | Monitoreo continuo | Sin visibilidad de nube | 2 | Alta |
| DE.CM-04 | Monitoreo continuo | Sin monitoreo de canales electrónicos | 2 | **Crítica** |
| DE.AE-01 | Análisis de eventos | Sin correlación con contexto del banco | 1 | Alta |
| DE.AE-02 | Análisis de eventos | Sin métricas de detección | 1 | Alta |
| DE.AE-03 | Análisis de eventos | Sin proceso de triaje | 1 | **Crítica** |

---

## 5. Recomendaciones priorizadas

### Quick wins (implementables en 90 días)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 1 | Desplegar Sysmon + Wazuh en endpoints críticos | **Crítico** | Q30,000 (implementación) |
| 2 | Definir proceso de triaje de alertas con SLA | **Crítico** | Q0 (interno) |
| 3 | Iniciar monitoreo de canales electrónicos | **Crítico** | Q20,000 (integración) |

### Trabajo estructural (3-6 meses)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 4 | Desplegar Suricata/Zeek en red interna | Alto | Q40,000 (implementación) |
| 5 | Implementar SIEM propio (Wazuh) | Alto | Q50,000 (infraestructura + implementación) |
| 6 | Definir métricas de detección (TTD, falsos positivos) | Medio | Q10,000 (consultoría) |
| 7 | Integrar monitoreo de nube pública | Medio | Q30,000 (integración) |
| 8 | Establecer integración estructurada con MDR | Alto | Q15,000 (consultoría) |

### Inversión total estimada

| Concepto | Costo |
|----------|-------|
| Quick wins | Q50,000 |
| Trabajo estructural | Q145,000 |
| **Total** | **Q195,000** |

---

## 6. Conclusión del dominio

El dominio **Detectar (DE)** tiene tres brechas críticas:

1. **No hay visibilidad de endpoints.** Sin EDR ni Sysmon, el banco no sabe qué procesos se ejecutan, qué conexiones hacen las estaciones de trabajo, ni qué archivos se modifican.

2. **No hay visibilidad de canales electrónicos.** El banco no monitorea su banca en línea ni su banca móvil. Eso significa que el fraude electrónico (el incidente disparador) no se detecta hasta que el cliente se queja.

3. **No hay proceso de triaje de alertas.** El MDR genera alertas, pero no hay un proceso interno que las reciba, las priorice, y las investigue con SLA definido.

**Prioridad:** Visibilidad de endpoints, monitoreo de canales electrónicos, y proceso de triaje antes de avanzar a los dominios de respuesta y recuperación.

---

## 7. Próximo dominio

**Dominio 5: Responder (RS)** — Evaluación de gestión de incidentes, comunicación, y mitigación.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
