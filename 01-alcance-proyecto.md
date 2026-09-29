# Documento de Alcance del Proyecto
## Gap Analysis de Ciberseguridad y Riesgo Tecnológico — Banco del Lago, S.A.

**Tipo de documento:** Project Charter / Acta de Constitución
**Estado:** Aprobado para inicio de fase de diagnóstico
**Versión:** 1.1
**Fecha:** Septiembre 2026
**Confidencialidad:** Uso interno — caso de estudio con fines de portafolio profesional

---

## 1. Propósito del documento

Este documento formaliza el alcance, los supuestos y las bases regulatorias del proyecto de **Gap Analysis de Ciberseguridad y Riesgo Tecnológico** para Banco del Lago, S.A., banco ficticio construido con datos reales del sistema financiero guatemalteco para fines de caso de estudio. Sirve como punto de partida único para todas las fases posteriores del proyecto (Gap Analysis, plan de remediación, roadmap de implementación).

Todo dato en este documento está etiquetado según su origen:

- **[VERIFICADO]** — dato real, con fuente y cálculo trazable.
- **[ESTIMADO]** — derivado por proporción o razón a partir de un dato real.
- **[SUPUESTO]** — decisión de diseño del caso de estudio, sin dato real detrás, pero técnicamente razonable.

---

## 2. Perfil institucional

### 2.1 Identidad

| Campo | Valor | Estatus |
|---|---|---|
| Razón social | Banco del Lago, S.A. | Ficticio |
| Grupo financiero | Grupo Financiero del Lago (banco + financiera + tarjetas + seguros) | [SUPUESTO] |
| Sede | Ciudad de Guatemala, zona financiera | [SUPUESTO] |
| Ente supervisor | Superintendencia de Bancos de Guatemala (SIB) | [VERIFICADO] |

### 2.2 Tamaño y posición de mercado

Base de cálculo: Banco Promerica de Guatemala +15%.

| Campo | Valor | Estatus |
|---|---|---|
| Empleados | ~2,800 | [ESTIMADO] — ajustado a coherencia operativa con 85 agencias |
| Activos totales | ~Q39,290 millones (~US$5,155 millones) | [VERIFICADO] (base Q34,165 millones) |
| Cartera de préstamos | ~Q29,190 millones | [VERIFICADO] (base Q25,383 millones) |
| Patrimonio | ~Q4,223 millones | [VERIFICADO] (base Q3,672 millones) |
| Índice de adecuación de capital | ~13.5–14% | [ESTIMADO] (mínimo regulatorio: 10%) |
| Participación en activos del sistema | ~6% | [ESTIMADO] (sistema: Q642,350 millones a dic-2025) |
| Posición en el ranking bancario | Fuera del top 5; probablemente entre 6º y 10º lugar | [ESTIMADO] (top 5 concentra 79% del crédito; top 10, 97%) |

### 2.3 Red de distribución y clientes

Sin dato reciente y comparable disponible en fuentes públicas para un banco de este perfil; se fijan como supuestos de diseño coherentes con un banco orientado a consumo y PYME.

| Campo | Valor | Estatus |
|---|---|---|
| Agencias | 85 | [SUPUESTO] |
| Cajeros automáticos propios | 180 | [SUPUESTO] |
| Clientes activos | ~750,000 | [SUPUESTO] |
| Canales digitales | Banca en línea y banca móvil, ambos transaccionales | [SUPUESTO] |
| Volumen mensual de transacciones electrónicas | ~2.8 millones | [SUPUESTO] |
| Distribución de transacciones por canal | 70% digital / 30% agencia | [SUPUESTO] |

### 2.4 Infraestructura tecnológica

| Campo | Valor | Estatus |
|---|---|---|
| Centro de cómputo principal | Ciudad de Guatemala | [SUPUESTO] |
| Centro de cómputo alterno / DRP | Fuera del área metropolitana | [SUPUESTO] |
| Core bancario | Producto comercial de terceros (no desarrollo propio) | [SUPUESTO] |
| Modelo de nube | Híbrido — cargas no críticas en nube pública; core y datos sensibles on-premise | [SUPUESTO] |
| SOC / CSIRT | Tercerizado (MDR), sin capacidad 24/7 interna | [SUPUESTO] — hallazgo de gap esperado |
| Proveedores tecnológicos críticos (sujetos a clasificación de criticidad, Art. 52 JM-98-2025) | 1. Proveedor de core bancario<br>2. Procesador/switch de tarjetas<br>3. Proveedor de nube<br>4. Proveedor de canales electrónicos / banca móvil<br>5. Proveedor de mensajería SWIFT<br>6. Proveedor de centro de cómputo alterno | [SUPUESTO] |

### 2.5 Gobernanza

| Órgano / Rol | Situación | Estatus |
|---|---|---|
| Consejo de Administración | Responsable último de la administración del riesgo tecnológico | [VERIFICADO] — obligación regulatoria (Art. 55, Ley de Bancos y Grupos Financieros) |
| Comité de Gestión de Riesgos | Existe y opera | [VERIFICADO] — obligación regulatoria |
| Comité de Auditoría | Existe y opera | [VERIFICADO] — obligación regulatoria (JM-62-2016) |
| Unidad de Administración de Riesgos | Existe y opera | [VERIFICADO] — obligación regulatoria |
| Auditoría Interna | Existe, reporta al Comité de Auditoría; no participa en la ejecución del proyecto | [VERIFICADO] — independencia exigida por JM-62-2016, Art. 16 |
| Oficial de Seguridad de la Información (CISO) | No existe formalmente; función repartida entre Gerencia de TI y Riesgos | [SUPUESTO] — hallazgo central que motiva el proyecto |

---

## 3. Marco regulatorio aplicable

| Norma | Descripción | Relevancia para el proyecto |
|---|---|---|
| **JM-98-2025** | Reglamento para la Administración del Riesgo Tecnológico. Vigente desde el 30-oct-2025; deroga la JM-104-2021. Cubre gobernanza de TI, seguridad de la información, ciberseguridad, plan de recuperación, gestión de proveedores e inteligencia artificial. | Marco normativo principal del Gap Analysis |
| **JM-91-2024 / JM-99-2025** | Reglamento de Medidas de Seguridad en Canales Electrónicos y su modificación (autenticación reforzada). | Aplica por operación de banca en línea y móvil |
| **JM-62-2016** | Reglamento de Gobierno Corporativo. Exige comité de auditoría y define funciones de auditoría interna. | Marco de gobernanza del proyecto |
| **Decreto 15-2026** | Ley Integral para la Prevención y Represión del Lavado de Dinero u Otros Activos y del Financiamiento del Terrorismo. Vigente desde el 17-sep-2026. | Contexto regulatorio ampliado, fuera del alcance técnico directo pero relevante para gobernanza integral |
| **ISO/IEC 27001:2022** | Estándar internacional de gestión de seguridad de la información. **No es obligatorio** en Guatemala. | Marco de referencia voluntario para estructurar el SGSI y evidenciar cumplimiento ante la SIB |
| **PCI DSS** | Estándar de la industria de tarjetas de pago. | Aplica por operación de tarjetas dentro del grupo financiero (no verificado en esta investigación; se asume aplicable por práctica de la industria) |

### 3.1 Calendario de cumplimiento regulatorio

La JM-98-2025 establece plazos escalonados que presionan directamente el calendario del proyecto:

| Hito regulatorio | Fecha límite | Estatus |
|---|---|---|
| Actualización del Manual de Administración del Riesgo Tecnológico | Dentro de los 12 meses posteriores a la entrada en vigor (30-oct-2025) → **octubre 2026** | Pendiente de verificación contra texto oficial |
| Actualización del Plan de Recuperación ante Desastres | Dentro de los 12 meses posteriores a la entrada en vigor → **octubre 2026** | Pendiente de verificación contra texto oficial |
| Análisis de criticidad de servicios de procesamiento y/o almacenamiento contratados (Art. 52) | Entre **diciembre 2026 y marzo 2027** según fuentes consultadas | **Pendiente de confirmación** — varía según la fuente (31-ene-2027 vs. 31-mar-2027) |
| Revisión de la regulación de canales electrónicos (JM-91-2024 / JM-99-2025) | Próxima revisión estimada entre **diciembre 2026 y marzo 2027** | [ESTIMADO] — ciclo regulatorio típico de la SIB |

**Implicación para el proyecto:** el Gap Analysis debe completarse antes de octubre de 2026 para dar tiempo a la remediación de los plazos de octubre. La clasificación de proveedores debe estar lista antes de diciembre de 2026. La revisión de canales electrónicos debe coincidir con la próxima actualización regulatoria.

---

## 4. Incidente disparador del proyecto

Escenario compuesto por dos elementos documentados a nivel sectorial, no un caso aislado inventado:

1. **Presión regulatoria con fecha límite.** El Manual de Administración del Riesgo Tecnológico y el Plan de Recuperación ante Desastres deben actualizarse dentro de los 12 meses posteriores a la entrada en vigor de la JM-98-2025 (octubre 2026). Adicionalmente, la clasificación de criticidad de proveedores tecnológicos debe completarse entre diciembre 2026 y marzo 2027, y se anticipa una nueva revisión de la regulación de canales electrónicos en el mismo período.

2. **Patrón de fraude sectorial.** El Ministerio Público acumuló más de 56,000 denuncias por fraude electrónico en tres años a nivel nacional, con modalidades de suplantación de identidad y enlaces fraudulentos distribuidos por WhatsApp como las más frecuentes. Banco del Lago detecta un incidente de este tipo que expone una debilidad de autenticación en uno de sus canales electrónicos.

La combinación de ambos elementos da al Comité de Gestión de Riesgos motivación suficiente para solicitar al Consejo de Administración la autorización del proyecto.

---

## 5. Objetivo del proyecto

Identificar las brechas de cumplimiento de Banco del Lago frente al Reglamento para la Administración del Riesgo Tecnológico (JM-98-2025) y frente a las buenas prácticas de ISO/IEC 27001:2022, y establecer una hoja de ruta priorizada de remediación que permita:

- Cumplir los plazos regulatorios de la JM-98-2025 (octubre 2026, diciembre 2026–marzo 2027).
- Formalizar la función de seguridad de la información (CISO / Oficial de Seguridad de la Información).
- Reducir la exposición al fraude en canales electrónicos.
- Preparar al banco para la próxima revisión regulatoria de canales electrónicos (JM-91-2024 / JM-99-2025).

---

## 6. Alcance

### 6.1 Incluido

- Gobernanza de riesgo tecnológico (Consejo, Comité de Gestión de Riesgos, Unidad de Riesgos).
- Gestión de infraestructura de TI, sistemas de información y bases de datos.
- Seguridad de la información (control de accesos, cifrado, gestión de vulnerabilidades, pruebas de penetración).
- **Capacidad de detección y respuesta** (monitoreo continuo, SIEM, SOC tercerizado, gestión de incidentes).
- Continuidad de operaciones de TI (DRP, centro de cómputo alterno).
- Gestión y clasificación de criticidad de proveedores tecnológicos.
- Seguridad en canales electrónicos (banca en línea, banca móvil).
- Mapeo de controles contra ISO/IEC 27001:2022 como marco de referencia complementario.

### 6.2 Excluido

- Cumplimiento antilavado bajo el Decreto 15-2026 (se trata como contexto, no como objeto de auditoría).
- Certificación formal ISO/IEC 27001 (el proyecto usa la norma como marco de referencia, no busca la certificación).
- Auditoría de riesgo de crédito, mercado o liquidez.
- Evaluación de las demás empresas del Grupo Financiero del Lago fuera del banco.

---

## 7. Gobernanza del proyecto

| Rol | Responsable | Función |
|---|---|---|
| **Sponsor** | Gerente General | Autoriza el proyecto y presenta resultados al Consejo de Administración |
| **Instancia de respaldo** | Comité de Gestión de Riesgos | Da seguimiento periódico y aprueba el plan de remediación |
| **Aprobación final** | Consejo de Administración | Aprueba el resultado del Gap Analysis y el presupuesto de remediación |
| **Dueño operativo** | Oficial de Seguridad de la Información (cargo a formalizar) | Ejecuta el diagnóstico y coordina la remediación |
| **Revisión independiente** | Auditoría Interna | Revisa el proceso y los resultados; no ejecuta ni participa en el diseño |

---

## 8. Entregables

1. Gap Analysis documentado contra JM-98-2025 e ISO/IEC 27001:2022 (matriz de cumplimiento por artículo/control).
2. Registro de hallazgos priorizados por nivel de riesgo.
3. Plan de remediación con responsables, plazos y dependencias regulatorias.
4. Propuesta de estructura para la función de seguridad de la información.
5. Dashboard de madurez con scoring por dominio del NIST CSF 2.0.

---

## 9. Criterios de éxito del proyecto

| Criterio | Métrica | Plazo |
|---|---|---|
| Gap Analysis completado | Documento aprobado por el Comité de Riesgos | 4 semanas |
| Plan de remediación aprobado | Documento con responsables y plazos | 6 semanas |
| Propuesta de estructura CISO presentada | Documento aprobado por el Consejo | 8 semanas |
| Quick wins identificados | Al menos 3 iniciativas implementables en 90 días | 4 semanas |
| Cumplimiento de plazos regulatorios | Manual y DRP actualizados | Octubre 2026 |
| Clasificación de proveedores | Lista de proveedores críticos clasificados | Diciembre 2026 |

---

## 10. Riesgos del proyecto

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Resistencia al cambio en TI | Alta | Medio | Involucrar a TI desde el inicio; comunicar beneficios del CISO formal |
| Falta de documentación existente | Alta | Alto | Entrevistas estructuradas; reconstruir inventario desde cero si es necesario |
| Presupuesto limitado para remediación | Media | Alto | Priorizar quick wins de bajo costo; presentar ROI al Consejo |
| Dependencia de proveedores externos | Media | Medio | Incluir cláusulas de seguridad en contratos; evaluar alternativas |
| Plazos regulatorios ajustados | Alta | Alto | Completar Gap Analysis antes de octubre 2026; priorizar remediación de plazos críticos |
| Falta de personal especializado | Media | Medio | Capacitar al equipo interno; considerar MDR para detección 24/7 |

---

## 11. Próxima fase

Inicio del **Gap Analysis** contra JM-98-2025 e ISO/IEC 27001:2022, usando este documento como línea base del perfil institucional. La evaluación se estructurará contra los 6 dominios del NIST CSF 2.0 (Gobernar, Identificar, Proteger, Detectar, Responder, Recuperar), con scoring de madurez de 5 niveles.

---

## 12. Control de supuestos

Toda cifra marcada como [SUPUESTO] en este documento es una decisión de diseño del caso de estudio, no un dato de Banco Promerica de Guatemala ni de ningún otro banco real. Las cifras marcadas [VERIFICADO] provienen de fuentes públicas sobre Banco Promerica de Guatemala (informes financieros y de mercado a 2025–2026) con un ajuste del +15% aplicado de forma explícita y trazable.

---

*Documento preparado como parte del portafolio técnico de Walter Gómez. Proyecto 4: Modelo de Madurez.*
