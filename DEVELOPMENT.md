# Desarrollo — Licita España 0.6.2

El paquete configura un MCP remoto Streamable HTTP; no contiene un servidor Python local. Contrato: `find_spanish_public_tenders` en `https://aiplugins.megawebs.com/mcp/licita-espana`. El servidor compartido se mantiene en `connectors/spain-assistant-mcp-apps` del repositorio privado maestro.

Valida los manifiestos portables y compatibilidad, comprueba descubrimiento de la herramienta por el endpoint acotado y ejecuta consultas públicas sin credenciales. Revisa errores, cobertura parcial, fuentes y límites. Los casos de revisión de `plugin.json` no prueban por sí solos una ejecución. Conserva el historial y las capturas de versiones anteriores sin cambiar sus fechas.
