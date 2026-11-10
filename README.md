# Licita España

Consulta una ventana acotada del feed oficial PLACSP por términos, CPV y plazo; devuelve enlaces, cobertura y continuación.

**Versión 0.6.3 · Conector MCP alojado e instrucciones complementarias · Sami Halawa · MIT**

## Instalación y uso

```bash
/plugin install licita-espana --marketplace samihalawa/2026-MASTER-Marketplace-Plugins-Connectors-etc
```


Instala el paquete en un anfitrión compatible con plugins y MCP remoto. La configuración incluida conecta `https://aiplugins.megawebs.com/mcp/licita-espana` mediante Streamable HTTP y expone `find_spanish_public_tenders`. No necesitas Python local, instalar dependencias ni proporcionar una clave del editor. La disponibilidad de la conexión depende del anfitrión y de la fuente pública.

> Busca licitaciones de servicios en una página de PLACSP y devuelve hasta dos resultados con sus enlaces.

- Busca licitaciones de obras con prefijo CPV 45 en PLACSP y devuelve como máximo dos resultados.
- Busca consultoría en hasta dos páginas de PLACSP. Indica la cobertura y cómo continuar.

Lee [la habilidad](skills/licita-espana/SKILL.md) para el procedimiento, [las fuentes](skills/licita-espana/references/sources.md) y [el contrato de acceso](skills/licita-espana/references/runtime.md). La herramienta realiza la consulta acotada descrita; la lectura de documentos, interpretación y creación de archivos usan capacidades adicionales del anfitrión. Conserva los identificadores, enlaces, fechas y límites realmente devueltos.

## Alcance

No presenta solicitudes u ofertas, no firma, no compra, no consulta datos protegidos ni activa vigilancia. Una respuesta parcial o fallida no prueba ausencia de registros. No se garantiza elegibilidad, resultado jurídico, titularidad ni financiación.

Los [ejemplos guardados](examples/demo.md) son capturas históricas de versiones anteriores, no consultas actuales. El historial de 0.5.0 conserva la edición de instrucciones; 0.6.0 añade una conexión remota explícita y no reetiqueta esas capturas. La aprobación en un directorio se verifica por separado.

[Producto e instalación](https://aiplugins.megawebs.com/plugins/licita-espana) · [Privacidad](https://aiplugins.megawebs.com/plugins/licita-espana/privacy) · [Condiciones](https://aiplugins.megawebs.com/plugins/licita-espana/terms) · [Soporte](https://aiplugins.megawebs.com/plugins/licita-espana/support)
