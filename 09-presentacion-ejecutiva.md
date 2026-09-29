# Presentación Ejecutiva al Consejo de Administración
## Gap Analysis de Ciberseguridad y Riesgo Tecnológico — Banco del Lago, S.A.

**Fecha:** Septiembre 2026
**Presentado por:** Gerencia General + Unidad de Riesgos
**Clasificación:** Confidencial — Uso interno del Consejo

---

## Slide 1: Portada

**Gap Analysis de Ciberseguridad y Riesgo Tecnológico**

Banco del Lago, S.A.

Resultados, Plan de Remediación y Solicitud de Presupuesto

Septiembre 2026

---

## Slide 2: Contexto

**¿Por qué estamos aquí?**

- La JM-98-2025 (Reglamento de Riesgo Tecnológico) entró en vigor el 30-oct-2025.
- El banco debe actualizar su Manual de Riesgo Tecnológico y su DRP antes de octubre 2026.
- La clasificación de criticidad de proveedores debe completarse entre diciembre 2026 y marzo 2027.
- Se anticipa una nueva revisión de la regulación de canales electrónicos en el mismo período.
- Adicionalmente, el banco detectó un incidente de fraude electrónico que expuso una debilidad de autenticación.

**Estamos dentro del plazo, pero el margen se está cerrando.**

---

## Slide 3: Metodología

**¿Cómo evaluamos?**

- Framework: **NIST CSF 2.0** (6 dominios, 23 categorías)
- Marco complementario: **ISO/IEC 27001:2022**
- Escala de madurez: 1 (Inicial) a 5 (Optimizado)
- Evaluación de 40 hallazgos en 6 dominios

**Sin cuantificación financiera del riesgo. Solo madurez y brechas.**

---

## Slide 4: Resultados Generales

**Madurez promedio: 1.7 sobre 5.0**

| Dominio | Madurez actual | Target | Gap |
|---------|----------------|--------|-----|
| Gobernar (GV) | 1.7 | 3.8 | -2.1 |
| Identificar (ID) | 1.7 | 3.7 | -2.0 |
| Proteger (PR) | 2.0 | 4.0 | -2.0 |
| Detectar (DE) | 1.5 | 4.0 | -2.5 |
| Responder (RS) | 1.7 | 4.0 | -2.3 |
| Recuperar (RC) | 1.5 | 4.0 | -2.5 |
| **Promedio** | **1.7** | **3.9** | **-2.2** |

**El banco está en nivel "Gestionado bajo" en todos los dominios.**

---

## Slide 5: Los 5 Hallazgos Más Críticos

| # | Hallazgo | Dominio | Impacto |
|---|----------|---------|---------|
| 1 | No existe CISO formal | Gobernar | Sin liderazgo de seguridad |
| 2 | No hay MFA en canales electrónicos | Proteger | Incumplimiento JM-99-2025 |
| 3 | No hay visibilidad de endpoints | Detectar | Ataques invisibles |
| 4 | DRP no probado en 18 meses | Recuperar | Recuperación no validada |
| 5 | No hay plan de respuesta a incidentes | Responder | Crisis sin guion |

---

## Slide 6: Hallazgo Central — Sin CISO

**El banco no tiene Oficial de Seguridad de la Información (CISO).**

- La función está repartida entre Gerencia de TI y Unidad de Riesgos.
- No hay autoridad formal para tomar decisiones de seguridad.
- No hay presupuesto dedicado a seguridad.
- No hay rendición de cuentas al Consejo.

**Consecuencia:** Las otras 39 brechas existen porque no hay quien las lidere.

---

## Slide 7: Hallazgo Crítico — MFA en Canales

**No hay autenticación multifactor en banca en línea ni banca móvil.**

- La JM-99-2025 exige MFA para transacciones de alto riesgo.
- El incidente de fraude electrónico (WhatsApp) explotó esta debilidad.
- 750,000 clientes activos están expuestos.
- 2.8 millones de transacciones mensuales sin protección reforzada.

**Consecuencia:** Riesgo regulatorio, financiero y reputacional.

---

## Slide 8: Plan de Remediación — Visión General

**3 horizontes, 18 meses, Q1,330,000**

| Horizonte | Plazo | Enfoque | Inversión |
|-----------|-------|---------|-----------|
| **Horizonte 1** | 0-90 días | Quick wins | Q215,000 |
| **Horizonte 2** | 3-6 meses | Trabajo estructural | Q700,000 |
| **Horizonte 3** | 6-18 meses | Madurez | Q415,000 |
| **Total** | | | **Q1,330,000** |

**Nota:** el CISO (Q600,000/año) es el 45% de la inversión. Sin ese rol, el plan no se ejecuta.

---

## Slide 9: Horizonte 1 — Quick Wins (90 días)

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

---

## Slide 10: Horizonte 2 — Trabajo Estructural (6 meses)

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

---

## Slide 11: Horizonte 3 — Madurez (18 meses)

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

---

## Slide 12: Beneficios Esperados

| Beneficio | Métrica | Plazo |
|-----------|---------|-------|
| Reducción de fraude electrónico | MFA en 100% de canales | 90 días |
| Detección temprana | TTD < 30 minutos | 6 meses |
| Recuperación probada | RTO < 4 horas | 6 meses |
| Cumplimiento regulatorio | JM-98-2025 completo | 6 meses |
| Madurez del programa | ≥ 3.5 sobre 5.0 | 18 meses |
| Certificación ISO 27001 | Obtenida | 18 meses |

---

## Slide 13: Riesgos de No Actuar

| Riesgo | Consecuencia |
|--------|--------------|
| Incumplimiento JM-98-2025 | Sanciones de la SIB |
| Fraude electrónico continuo | Pérdida financiera y reputacional |
| Ransomware exitoso | Interrupción de operaciones |
| DRP no probado | Recuperación fallida en crisis real |
| Falta de CISO | Sin liderazgo de seguridad |

**El costo de no actuar es mayor que la inversión en remediación.**

---

## Slide 14: Solicitud al Consejo

**Solicitamos:**

1. **Aprobación del Gap Analysis** y sus hallazgos.
2. **Aprobación del Plan de Remediación** en 3 horizontes.
3. **Presupuesto para Horizonte 1:** Q215,000 (90 días).
4. **Autorización para crear la posición de CISO** (Horizonte 2).
5. **Compromiso de revisión trimestral** del avance en el Comité de Riesgos.

---

## Slide 15: Próximos Pasos

| Plazo | Acción | Responsable |
|-------|--------|-------------|
| Semana 1 | Aprobación del presupuesto Horizonte 1 | Consejo |
| Semana 2 | Inicio de implementación de MFA | TI |
| Semana 2 | Inicio de despliegue de Sysmon + Wazuh | TI |
| Semana 4 | Inicio de evaluación de riesgo cibernético | Riesgos |
| Semana 8 | Primera prueba del DRP | TI + Riesgos |
| Semana 12 | Reporte de avance al Consejo | Gerencia General |

---

## Slide 16: Cierre

**El banco está en nivel 1.7 de madurez. El target es 3.9.**

**La inversión es Q1,330,000 en 18 meses.**

**El costo de no actuar es mayor.**

**Solicitamos su aprobación para iniciar el Horizonte 1.**

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
