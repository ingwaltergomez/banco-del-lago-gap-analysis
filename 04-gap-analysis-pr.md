# Gap Analysis — Dominio 3: Proteger (PR)
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Descripción del dominio

La función **Proteger (PR)** del NIST CSF 2.0 implementa las salvaguardas para gestionar el riesgo de ciberseguridad. Cubre la gestión de identidad, la protección de datos, la seguridad de plataformas, y la resiliencia de la infraestructura.

Sin protección, la detección no sirve de nada. Puedes detectar un ataque, pero si no tienes controles, el ataque tiene éxito.

### Categorías del dominio PR

| Categoría | Nombre | Qué evalúa |
|-----------|--------|------------|
| **PR.AA** | Gestión de identidad y acceso | Autenticación, autorización, control de acceso |
| **PR.AT** | Concientización y entrenamiento | Capacitación de empleados en seguridad |
| **PR.DS** | Seguridad de datos | Cifrado, clasificación, protección de datos |
| **PR.PS** | Seguridad de plataformas | Hardening, gestión de vulnerabilidades, parches |
| **PR.IR** | Resiliencia de infraestructura | Redundancia, segmentación, capacidad |

---

## 2. Evaluación de madurez

### Puntuación por categoría

| Categoría | Estado actual | Target | Gap |
|-----------|---------------|--------|-----|
| **PR.AA** — Gestión de identidad y acceso | 2 | 4 | -2 |
| **PR.AT** — Concientización y entrenamiento | 1 | 4 | -3 |
| **PR.DS** — Seguridad de datos | 2 | 4 | -2 |
| **PR.PS** — Seguridad de plataformas | 2 | 4 | -2 |
| **PR.IR** — Resiliencia de infraestructura | 3 | 4 | -1 |
| **Promedio del dominio** | **2.0** | **4.0** | **-2.0** |

**Interpretación:** El dominio Proteger está en nivel **Gestionado (2.0)**, ligeramente mejor que Gobernar e Identificar. El banco tiene controles básicos, pero **no están documentados, no se miden, y no cubren todos los dominios**.

---

## 3. Hallazgos por categoría

### 3.1 PR.AA — Gestión de identidad y acceso

**Estado actual (Nivel 2):**

- Los empleados tienen cuentas de Active Directory para acceder a sistemas internos.
- La banca en línea usa autenticación con usuario y contraseña. **No hay autenticación multifactor (MFA) obligatoria** en canales electrónicos, a pesar de que la JM-99-2025 la exige para transacciones de alto riesgo.
- No hay gestión de identidades privilegiadas (PAM). Las cuentas de administrador se comparten en algunos casos.
- No hay revisión periódica de accesos. Los empleados que se van no siempre se desactivan a tiempo.
- No hay política de contraseñas robusta.

**Hallazgo PR.AA-01:** No hay MFA obligatoria en canales electrónicos, a pesar de la exigencia regulatoria (JM-99-2025).

**Hallazgo PR.AA-02:** No hay gestión de identidades privilegiadas (PAM). Cuentas de administrador compartidas.

**Hallazgo PR.AA-03:** No hay revisión periódica de accesos ni proceso formal de baja de empleados.

**Brecha:** Falta un programa de gestión de identidad y acceso que incluya MFA, PAM, revisiones periódicas, y proceso de baja.

**Recomendación:** Implementar:
- MFA obligatoria en banca en línea, banca móvil, y accesos administrativos.
- Solución de PAM para cuentas privilegiadas.
- Revisión trimestral de accesos.
- Proceso formal de baja de empleados (desactivación en < 24 horas).

---

### 3.2 PR.AT — Concientización y entrenamiento

**Estado actual (Nivel 1):**

- No hay programa de concientización en seguridad de la información.
- Los empleados no reciben capacitación periódica sobre phishing, fraude electrónico, o buenas prácticas.
- No hay simulacros de phishing.
- No hay métricas de efectividad de concientización.
- El incidente de fraude electrónico por WhatsApp (documentado en el alcance) **no fue detectado por el empleado afectado**, lo que evidencia la falta de concientización.

**Hallazgo PR.AT-01:** No existe programa de concientización en seguridad de la información.

**Hallazgo PR.AT-02:** No hay simulacros de phishing ni métricas de efectividad.

**Brecha:** Falta un programa de concientización continua, con capacitación periódica, simulacros de phishing, y métricas de efectividad.

**Recomendación:** Implementar:
- Capacitación obligatoria anual en seguridad de la información.
- Simulacros de phishing trimestrales.
- Campañas de concientización sobre fraude electrónico (WhatsApp, phishing, suplantación).
- Métricas de efectividad (tasa de clics en phishing, tasa de reporte).

---

### 3.3 PR.DS — Seguridad de datos

**Estado actual (Nivel 2):**

- Los datos en reposo en el core bancario están cifrados a nivel de base de datos.
- **Los datos en tránsito entre sucursales y el centro de cómputo no están cifrados** en todos los casos.
- No hay clasificación formal de información (pública, interna, confidencial, restringida).
- No hay DLP (Data Loss Prevention).
- No hay política de retención y destrucción de datos.
- Los backups no están cifrados.

**Hallazgo PR.DS-01:** No hay clasificación formal de información.

**Hallazgo PR.DS-02:** No hay cifrado de datos en tránsito en todos los enlaces.

**Hallazgo PR.DS-03:** No hay DLP ni política de retención de datos.

**Brecha:** Falta un programa de seguridad de datos que incluya clasificación, cifrado en tránsito y reposo, DLP, y política de retención.

**Recomendación:** Implementar:
- Clasificación de información (4 niveles).
- Cifrado de datos en tránsito (TLS 1.3 en todos los enlaces).
- DLP en canales de salida (email, USB, web).
- Política de retención y destrucción segura.

---

### 3.4 PR.PS — Seguridad de plataformas

**Estado actual (Nivel 2):**

- Los servidores críticos (core bancario, base de datos) tienen hardening básico.
- **No hay gestión formal de vulnerabilidades.** Los parches se aplican cuando hay tiempo, no según criticidad.
- No hay escaneo de vulnerabilidades periódico.
- No hay pruebas de penetración.
- El servidor de archivos tiene Windows Server 2016 sin parches desde 2023 (hallazgo del Proyecto 2, si aplica al banco).
- No hay EDR en endpoints.

**Hallazgo PR.PS-01:** No hay gestión formal de vulnerabilidades ni escaneo periódico.

**Hallazgo PR.PS-02:** No hay pruebas de penetración.

**Hallazgo PR.PS-03:** No hay EDR en endpoints.

**Brecha:** Falta un programa de gestión de vulnerabilidades, con escaneo periódico, priorización por criticidad, y pruebas de penetración anuales.

**Recomendación:** Implementar:
- Escaneo de vulnerabilidades mensual (OpenVAS o Nessus).
- Priorización de parches por criticidad (CVSS > 7.0 en < 30 días).
- Pruebas de penetración anuales (al menos en canales electrónicos).
- EDR en endpoints críticos.

---

### 3.5 PR.IR — Resiliencia de infraestructura

**Estado actual (Nivel 3):**

- El banco tiene un centro de cómputo alterno fuera del área metropolitana.
- Hay redundancia de enlaces de red con dos proveedores.
- Hay UPS y generador en el centro de cómputo principal.
- **El DRP no se ha probado en los últimos 18 meses.**
- No hay segmentación de red entre ambientes (producción, desarrollo, pruebas).
- No hay microsegmentación en el centro de datos.

**Hallazgo PR.IR-01:** El DRP no se ha probado en 18 meses.

**Hallazgo PR.IR-02:** No hay segmentación de red entre ambientes.

**Brecha:** Falta probar el DRP anualmente y segmentar la red por ambientes y criticidad.

**Recomendación:** Implementar:
- Prueba anual del DRP con métricas de RTO y RPO.
- Segmentación de red por ambientes (producción, desarrollo, pruebas).
- Microsegmentación en el centro de datos (VLANs, firewall interno).

---

## 4. Resumen de hallazgos

| ID | Categoría | Hallazgo | Nivel | Severidad |
|----|-----------|----------|-------|-----------|
| PR.AA-01 | Identidad y acceso | Sin MFA en canales electrónicos | 2 | **Crítica** |
| PR.AA-02 | Identidad y acceso | Sin PAM, cuentas compartidas | 2 | Alta |
| PR.AA-03 | Identidad y acceso | Sin revisión periódica de accesos | 2 | Alta |
| PR.AT-01 | Concientización | Sin programa de concientización | 1 | **Crítica** |
| PR.AT-02 | Concientización | Sin simulacros de phishing | 1 | Alta |
| PR.DS-01 | Seguridad de datos | Sin clasificación de información | 2 | Alta |
| PR.DS-02 | Seguridad de datos | Sin cifrado en tránsito completo | 2 | Alta |
| PR.DS-03 | Seguridad de datos | Sin DLP ni retención | 2 | Media |
| PR.PS-01 | Plataformas | Sin gestión de vulnerabilidades | 2 | **Crítica** |
| PR.PS-02 | Plataformas | Sin pruebas de penetración | 2 | Alta |
| PR.PS-03 | Plataformas | Sin EDR en endpoints | 2 | Alta |
| PR.IR-01 | Resiliencia | DRP no probado en 18 meses | 3 | Alta |
| PR.IR-02 | Resiliencia | Sin segmentación de red | 3 | Media |

---

## 5. Recomendaciones priorizadas

### Quick wins (implementables en 90 días)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 1 | Implementar MFA en canales electrónicos | **Crítico** | Q50,000 |
| 2 | Iniciar programa de concientización con simulacros de phishing | **Crítico** | Q15,000 |
| 3 | Iniciar escaneo de vulnerabilidades mensual | Alto | Q20,000 (herramienta) |
| 4 | Probar el DRP | Alto | Q10,000 (horas extra) |

### Trabajo estructural (3-6 meses)

| # | Acción | Impacto | Costo estimado |
|---|--------|---------|----------------|
| 5 | Implementar PAM | Alto | Q80,000 |
| 6 | Implementar EDR en endpoints | Alto | Q120,000 |
| 7 | Clasificación de información y DLP | Medio | Q60,000 |
| 8 | Segmentación de red y microsegmentación | Medio | Q40,000 |
| 9 | Pruebas de penetración anuales | Alto | Q50,000 |

### Inversión total estimada

| Concepto | Costo |
|----------|-------|
| Quick wins | Q95,000 |
| Trabajo estructural | Q350,000 |
| **Total** | **Q445,000** |

---

## 6. Conclusión del dominio

El dominio **Proteger (PR)** tiene tres brechas críticas:

1. **No hay MFA en canales electrónicos.** Eso es un incumplimiento directo de la JM-99-2025 y una exposición al fraude electrónico que ya se materializó en el incidente disparador.

2. **No hay programa de concientización.** El empleado afectado por el fraude no supo detectarlo. Eso es un fallo de concientización, no de tecnología.

3. **No hay gestión de vulnerabilidades.** El banco no sabe qué vulnerabilidades tiene, ni cuáles son críticas, ni cuándo parchearlas.

**Prioridad:** MFA, concientización, y gestión de vulnerabilidades antes de avanzar a los dominios de detección y respuesta.

---

## 7. Próximo dominio

**Dominio 4: Detectar (DE)** — Evaluación de monitoreo continuo y análisis de eventos.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
