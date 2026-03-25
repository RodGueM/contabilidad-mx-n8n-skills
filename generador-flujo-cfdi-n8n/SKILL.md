---
name: generador-flujo-cfdi-n8n
description: Genera workflow n8n completo y listo para importar que automatiza la creación, timbrado y envío de CFDI 4.0 (ingreso, egreso, pago, etc.) conforme a reglas SAT 2026. Usa cuando el usuario mencione "automatizar CFDI", "facturación automática" o "timbrado n8n".
---

# Generador de Flujo n8n para CFDI 4.0 México 2026

**Reglas obligatorias 2026:**
- CFDI 4.0 + catálogos actualizados (vigentes desde 30-ene-2026 y marzo-2026).
- Complementos vigentes (Carta Porte 2.0, Impuestos Locales, etc.).
- Validación RFC, uso CFDI, tipo de relación y cálculo exacto de impuestos (IVA 16%/0%/8%, ISR retenido).
- Timbrado vía PAC (HTTP Request con credenciales seguras).

**Estructura del workflow n8n que debes generar:**
1. Trigger: Schedule o Webhook (datos desde Google Sheets/Excel/Form).
2. Function/Code node: generar XML válido.
3. HTTP Request: timbrado en PAC (ej. Edicom, Finkok, etc.).
4. IF node: validar respuesta SAT.
5. Email node: enviar PDF + XML al receptor + acuse.
6. Google Sheets / Airtable: registrar timbrado.
7. Error Workflow + notificación Slack/Email.

**Output obligatorio:**
- JSON completo listo para importar en n8n (con "name", "nodes", "connections", "settings", etc.).
- Instrucciones paso a paso para importar y configurar credenciales.
- Lista de nodos usados y variables de entorno requeridas.
