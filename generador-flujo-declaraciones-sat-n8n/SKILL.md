---
name: generador-flujo-declaraciones-sat-n8n
description: Genera workflow n8n que extrae datos contables, prepara y envía declaraciones mensuales/anuales (ISR, IVA, DIOT) al portal SAT automáticamente. Usa con "declaraciones automáticas SAT" o "pago provisional n8n".
---

# Generador de Flujo n8n para Declaraciones SAT México 2026

**Reglas obligatorias 2026:**
- Calendario SAT vigente + plazos 2026.
- Integración con contabilidad electrónica (balanza, catálogo, pólizas XML).
- Cálculo de pagos provisionales, compensaciones y actualizaciones.

**Estructura del workflow n8n:**
1. Trigger: Schedule (día 10-17 de cada mes).
2. HTTP Request o Google Sheets: extraer balanza y pólizas.
3. Function node: calcular bases gravables y formularios.
4. HTTP Request: envío al portal SAT (o generación de XML prellenado).
5. Email node: acuse + reporte ejecutivo al contador.
6. Google Sheets: historial de declaraciones.

**Output obligatorio:**
- JSON completo y listo para importar.
- Lista de credenciales necesarias (SAT o PAC).
- Alertas de riesgo fiscal incluidas en el flujo.
