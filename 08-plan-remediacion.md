# Plan de Remediación
## Banco del Lago, S.A.

**Proyecto:** Gap Analysis de Ciberseguridad y Riesgo Tecnológico
**Framework:** NIST CSF 2.0 + ISO/IEC 27001:2022
**Fecha:** Septiembre 2026
**Clasificación:** Uso interno — caso de estudio

---

## 1. Resumen ejecutivo

El Gap Analysis identificó **40 hallazgos** en los 6 dominios del NIST CSF 2.0, con una madurez promedio de **1.7 sobre 5.0**. El banco tiene actividades de seguridad, pero no tiene estructura, métricas, ni mejora continua.

Este plan de remediación estructura las acciones correctivas en **3 horizontes**:

| Horizonte | Plazo | Enfoque | Inversión |
|-----------|-------|---------|-----------|
| **Horizonte 1** | 0-90 días | Quick wins. Cerrar brechas críticas de bajo costo. | Q215,000 |
| **Horizonte 2** | 3-6 meses | Trabajo estructural. Implementar controles faltantes. | Q700,000 |
| **Horizonte 3** | 6-18 meses | Madurez. Métricas, mejora continua, certificación. | Q415,000 |
| **Total** | | | **Q1,330,000** |

**Nota:** el costo del CISO (Q600,000/año) está incluido en el Horizonte 2. Sin ese rol, las demás acciones no tienen quien las lidere.

---

## 2. Horizonte 1: Quick Wins (0-90 días)

**Objetivo:** Cerrar las brechas más críticas con inversión mínima, demostrando valor rápido al Consejo.

### Iniciativas

| # | Iniciativa | Dominio | Hallazgos que cierra | Responsable | Inversión |
|---|------------|---------|---------------------|-------------|-----------|
| 1.1 | Implementar MFA en canales electrónicos | Proteger | PR.AA-01 | Gerencia de TI | Q50,000 |
| 1.2 | Desplegar Sysmon + Wazuh en endpoints críticos | Detectar | DE.CM-01 | Gerencia de TI | Q30,000 |
| 1.3 | Definir proceso de triaje de alertas con SLA | Detectar | DE.AE-03 | Gerencia de TI + Riesgos | Q0 |
| 1.4 | Iniciar monitoreo de canales electrónicos | Detectar | DE.CM-04 | Gerencia de TI | Q20,000 |
| 1.5 | Documentar RTO y RPO por sistema crítico | Recuperar | RC.RP-02 | Riesgos + TI | Q10,000 |
| 1.6 | Probar el DRP | Recuperar | RC.RP-01 | TI + Riesgos | Q15,000 |
| 1.7 | Redactar plan de respuesta a incidentes | Responder | RS.MA-01 | Riesgos + TI | Q20,000 |
| 1.8 | Definir protocolo de notificación a la SIB | Responder | RS.CO-02 | Legal + Riesgos | Q0 |
| 1.9 | Iniciar programa de concientización con simulacros de phishing | Proteger | PR.AT-01, PR.AT-02 | RRHH + TI | Q15,000 |
| 1.10 | Iniciar clasificación de proveedores críticos | Gobernar | GV.SC-01 | Riesgos + Compras | Q15,000 |
| 1.11 | Completar inventario de activos con dueños y criticidad | Identificar | ID.AM-01, ID.AM-02 | TI | Q0 |
| 1.12 | Iniciar evaluación de riesgo cibernético de los 10 activos más críticos | Identificar | ID.RA-01 | Riesgos + consultor | Q15,000 |
| 1.13 | Crear documento de contexto organizacional | Gobernar | GV.OC-01 | Riesgos | Q0 |
| 1.14 | Definir KPIs de seguridad y reporte mensual al Comité | Gobernar | GV.OV-01 | Riesgos | Q0 |
| 1.15 | Implementar proceso de lecciones aprendidas post-incidente | Identificar | ID.IM-01 | Riesgos + TI | Q0 |
| 1.16 | Redactar plan de comunicación post-incidente | Recuperar | RC.CO-01 | Comunicaciones + Legal | Q10,000 |

### Inversión Horizonte 1

| Concepto | Costo |
|----------|-------|
| MFA en canales electrónicos | Q50,000 |
| Sysmon + Wazuh en endpoints | Q30,000 |
| Monitoreo de canales electrónicos | Q20,000 |
| RTO/RPO documentados | Q10,000 |
| Prueba del DRP | Q15,000 |
| Plan de respuesta a incidentes | Q20,000 |
| Concientización y simulacros | Q15,000 |
| Clasificación de proveedores | Q15,000 |
| Evaluación de riesgo cibernético | Q15,000 |
| Plan de comunicación post-incidente | Q10,000 |
| **Total Horizonte 1** | **Q215,000** |

### Métricas de éxito Horizonte 1

| Métrica | Target |
|---------|--------|
| MFA implementada en canales electrónicos | 100% |
| Endpoints con Sysmon + Wazuh | 100% de endpoints críticos |
| DRP probado | 1 prueba completada |
| RTO/RPO documentados | 100% de sistemas críticos |
| Plan de respuesta a incidentes | Aprobado por Comité |
| Proveedores críticos clasificados | 6 de 6 |
| Inventario de activos completado | 100% |

---

## 3. Horizonte 2: Trabajo Estructural (3-6 meses)

**Objetivo:** Implementar los controles faltantes que requieren inversión y tiempo.

### Iniciativas

| # | Iniciativa | Dominio | Hallazgos que cierra | Responsable | Inversión |
|---|------------|---------|---------------------|-------------|-----------|
| 2.1 | Formalizar la función de CISO | Gobernar | GV.RR-01, GV.RR-02 | Consejo + RRHH | Q600,000/año |
| 2.2 | Redactar declaración de apetito de riesgo | Gobernar | GV.RM-01 | Riesgos + Consejo | Q25,000 |
| 2.3 | Desarrollar conjunto completo de políticas | Gobernar | GV.PO-01 | Riesgos + consultor | Q40,000 |
| 2.4 | Incluir cláusulas de seguridad en contratos | Gobernar | GV.SC-02 | Legal + Compras | Q0 |
| 2.5 | Implementar PAM | Proteger | PR.AA-02 | TI | Q80,000 |
| 2.6 | Implementar EDR en endpoints | Proteger | PR.PS-03 | TI | Q120,000 |
| 2.7 | Clasificación de información y DLP | Proteger | PR.DS-01, PR.DS-03 | TI + Riesgos | Q60,000 |
| 2.8 | Implementar backups inmutables | Recuperar | RC.RP-04 | TI | Q50,000 |
| 2.9 | Implementar SIEM propio (Wazuh) | Detectar | DE.CM-02, DE.AE-01 | TI | Q50,000 |
| 2.10 | Desplegar Suricata/Zeek en red interna | Detectar | DE.CM-02 | TI + Redes | Q40,000 |
| 2.11 | Implementar capacidad forense básica | Responder | RS.AN-01, RS.AN-03 | TI + consultor | Q15,000 |
| 2.12 | Desarrollar playbooks para escenarios comunes | Responder | RS.MA-03 | Riesgos + TI | Q30,000 |
| 2.13 | Implementar TheHive para registro de incidentes | Responder | RS.MA-02 | TI | Q20,000 |
| 2.14 | Documentar procedimientos de contención y recuperación | Responder | RS.MI-01, RS.MI-03 | TI + Riesgos | Q20,000 |
| 2.15 | Documentar procedimientos de recuperación por sistema | Recuperar | RC.RP-03 | TI + Riesgos | Q30,000 |
| 2.16 | Definir plan de recuperación escalonado | Recuperar | RC.RP-05 | Riesgos + TI | Q10,000 |
| 2.17 | Establecer integración estructurada con MDR | Detectar | DE.AE-02, RS.MI-02 | TI + Riesgos | Q15,000 |
| 2.18 | Implementar métricas de detección (TTD, falsos positivos) | Detectar | DE.AE-02 | Riesgos + TI | Q10,000 |
| 2.19 | Integrar monitoreo de nube pública | Detectar | DE.CM-03 | TI | Q30,000 |
| 2.20 | Implementar herramienta de descubrimiento de activos | Identificar | ID.AM-01, ID.AM-03 | TI | Q20,000 |
| 2.21 | Completar evaluación de riesgo cibernético con cuantificación financiera | Identificar | ID.RA-02, ID.RA-03 | Riesgos + consultor | Q40,000 |
| 2.22 | Implementar métricas de mejora continua | Identificar | ID.IM-02 | Riesgos | Q10,000 |
| 2.23 | Documentar procedimientos de contención | Responder | RS.MI-01 | TI + Riesgos | Q20,000 |
| 2.24 | Probar el DRP anualmente con métricas | Recuperar | RC.RP-01 | TI + Riesgos | Q15,000 |
| 2.25 | Designar equipo de recuperación con roles | Recuperar | RC.RP-05 | RRHH + TI | Q0 |
| 2.26 | Capacitar al equipo en recuperación | Recuperar | RC.RP-03 | RRHH + TI | Q20,000 |
| 2.27 | Implementar proceso de lecciones aprendidas | Recuperar | RC.CO-03 | Riesgos | Q10,000 |
| 2.28 | Incluir protocolos de comunicación con clientes, empleados, medios | Recuperar | RC.CO-02 | Comunicaciones + Legal | Q10,000 |
| 2.29 | Implementar cifrado de datos en tránsito | Proteger | PR.DS-02 | TI + Redes | Q40,000 |
| 2.30 | Segmentación de red y microsegmentación | Proteger | PR.IR-02 | TI + Redes | Q40,000 |
| 2.31 | Implementar pruebas de penetración anuales | Proteger | PR.PS-02 | TI + consultor | Q50,000 |
| 2.32 | Implementar escaneo de vulnerabilidades mensual | Proteger | PR.PS-01 | TI | Q20,000 |
| 2.33 | Documentar y probar procedimientos de erradicación | Responder | RS.MI-02 | TI + Riesgos | Q15,000 |

### Inversión Horizonte 2

| Concepto | Costo |
|----------|-------|
| CISO (anual) | Q600,000 |
| Apetito de riesgo | Q25,000 |
| Políticas completas | Q40,000 |
| PAM | Q80,000 |
| EDR en endpoints | Q120,000 |
| Clasificación y DLP | Q60,000 |
| Backups inmutables | Q50,000 |
| SIEM propio (Wazuh) | Q50,000 |
| Suricata/Zeek | Q40,000 |
| Capacidad forense | Q15,000 |
| Playbooks | Q30,000 |
| TheHive | Q20,000 |
| Procedimientos de contención | Q20,000 |
| Procedimientos de recuperación | Q30,000 |
| Plan escalonado | Q10,000 |
| Integración con MDR | Q15,000 |
| Métricas de detección | Q10,000 |
| Monitoreo de nube | Q30,000 |
| Descubrimiento de activos | Q20,000 |
| Evaluación de riesgo completa | Q40,000 |
| Métricas de mejora | Q10,000 |
| Prueba anual DRP | Q15,000 |
| Capacitación en recuperación | Q20,000 |
| Lecciones aprendidas | Q10,000 |
| Comunicación post-incidente | Q10,000 |
| Cifrado en tránsito | Q40,000 |
| Segmentación de red | Q40,000 |
| Pruebas de penetración | Q50,000 |
| Escaneo de vulnerabilidades | Q20,000 |
| Procedimientos de erradicación | Q15,000 |
| **Total Horizonte 2** | **Q700,000** |

### Métricas de éxito Horizonte 2

| Métrica | Target |
|---------|--------|
| CISO formalizado | 1 rol creado y ocupado |
| Apetito de riesgo aprobado | Por Consejo |
| Políticas completas | 6 políticas nuevas/actualizadas |
| PAM implementado | 100% de cuentas privilegiadas |
| EDR en endpoints | 100% de endpoints críticos |
| Backups inmutables | 100% de sistemas críticos |
| SIEM propio | 100% de logs consolidados |
| DRP probado | 2 pruebas completadas |
| Capacidad forense | 3 herramientas implementadas |
| Playbooks | 4 escenarios documentados |

---

## 4. Horizonte 3: Madurez (6-18 meses)

**Objetivo:** Alcanzar madurez nivel 4 (Gestionado cuantitativamente) en los 6 dominios, y preparar al banco para certificación ISO 27001.

### Iniciativas

| # | Iniciativa | Dominio | Hallazgos que cierra | Responsable | Inversión |
|---|------------|---------|---------------------|-------------|-----------|
| 3.1 | Implementar ciclo PDCA documentado | Todos | ID.IM-02 | CISO | Q15,000 |
| 3.2 | Revisión trimestral del programa de seguridad | Todos | GV.OV-01 | CISO + Comité | Q10,000 |
| 3.3 | Implementar métricas de madurez por dominio | Todos | ID.IM-02 | CISO | Q15,000 |
| 3.4 | Auditoría interna de seguridad | Todos | GV.OV-01 | Auditoría Interna | Q50,000 |
| 3.5 | Pruebas de penetración avanzadas | Proteger | PR.PS-02 | Consultor externo | Q80,000 |
| 3.6 | Simulacro anual de respuesta a incidentes | Responder | RS.MA-01 | CISO | Q25,000 |
| 3.7 | Simulacro anual de recuperación | Recuperar | RC.RP-01 | CISO | Q25,000 |
| 3.8 | Implementar SOAR para automatización | Detectar/Responder | DE.AE-03, RS.MA-01 | CISO + TI | Q100,000 |
| 3.9 | Preparación para certificación ISO 27001 | Todos | GV.PO-01 | CISO | Q50,000 |
| 3.10 | Auditoría de certificación ISO 27001 | Todos | Todos | Consultor externo | Q45,000 |

### Inversión Horizonte 3

| Concepto | Costo |
|----------|-------|
| Ciclo PDCA | Q15,000 |
| Revisión trimestral | Q10,000 |
| Métricas de madurez | Q15,000 |
| Auditoría interna | Q50,000 |
| Pruebas de penetración avanzadas | Q80,000 |
| Simulacro de respuesta | Q25,000 |
| Simulacro de recuperación | Q25,000 |
| SOAR | Q100,000 |
| Preparación ISO 27001 | Q50,000 |
| Auditoría de certificación | Q45,000 |
| **Total Horizonte 3** | **Q415,000** |

### Métricas de éxito Horizonte 3

| Métrica | Target |
|---------|--------|
| Madurez promedio | ≥ 3.5 sobre 5.0 |
| Ciclo PDCA | Documentado y operando |
| Auditoría interna | 1 auditoría completada |
| Simulacro de respuesta | 1 simulacro completado |
| Simulacro de recuperación | 1 simulacro completado |
| SOAR implementado | 100% de playbooks automatizados |
| Certificación ISO 27001 | Obtenida |

---

## 5. Resumen de inversión total

| Horizonte | Plazo | Inversión | % del total |
|-----------|-------|-----------|-------------|
| Horizonte 1 | 0-90 días | Q215,000 | 16% |
| Horizonte 2 | 3-6 meses | Q700,000 | 53% |
| Horizonte 3 | 6-18 meses | Q415,000 | 31% |
| **Total** | **18 meses** | **Q1,330,000** | **100%** |

**Nota:** el CISO (Q600,000/año) es el 45% de la inversión total. Sin ese rol, las demás acciones no tienen quien las lidere.

---

## 6. Beneficios esperados

| Beneficio | Métrica | Horizonte |
|-----------|---------|-----------|
| Reducción de exposición al fraude electrónico | MFA en 100% de canales | H1 |
| Detección temprana de incidentes | TTD < 30 minutos | H2 |
| Recuperación probada | RTO < 4 horas, RPO < 1 hora | H2 |
| Cumplimiento regulatorio | JM-98-2025 completo | H2 |
| Madurez del programa | ≥ 3.5 sobre 5.0 | H3 |
| Certificación ISO 27001 | Obtenida | H3 |

---

## 7. Riesgos del plan

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|--------------|---------|------------|
| Resistencia al cambio en TI | Alta | Medio | Involucrar a TI desde el inicio; comunicar beneficios |
| Presupuesto limitado | Media | Alto | Priorizar quick wins; presentar ROI al Consejo |
| Falta de personal especializado | Alta | Alto | Contratar CISO; capacitar al equipo; considerar consultoría |
| Plazos regulatorios ajustados | Alta | Alto | Completar Horizonte 1 antes de octubre 2026 |
| Dependencia de proveedores externos | Media | Medio | Incluir cláusulas de seguridad; evaluar alternativas |

---

## 8. Próxima fase

**Presentación ejecutiva al Consejo de Administración** con el resumen del Gap Analysis, el plan de remediación, y la solicitud de presupuesto.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
