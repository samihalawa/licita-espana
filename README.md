![Icono de Licita España](assets/icon.png)

# Licita España

## Decide qué licitación merece tu tiempo.

Encuentra licitaciones y convierte sus pliegos en una decisión documentada: requisitos, plazos y próximos pasos.

**Para:** Autónomos, pymes y consultoras que preparan ofertas públicas.

**Fuente:** PLACSP · **Sin cuenta adicional ni API key** · **Python 3.11+** · **MIT**

### Qué obtienes

- Expediente, organismo, presupuesto y plazo, juntos.
- Continúa sin perder coincidencias dentro de la página.
- Prepara una matriz de requisitos con cláusula y evidencia.

### Pruébalo con una pregunta

> Busca licitaciones de software y separa los plazos futuros de los ya vencidos.

También: “Revisa estos pliegos y señala los requisitos, las pruebas que faltan y las cláusulas.”

[Ver el informe de ejemplo](examples/demo.md) · [Código de la página del producto](docs/index.html) · [Flujo completo](skills/licita-espana/references/workflow.md)

La demostración es una **captura guardada de fuentes oficiales**, no una consulta actual. Conserva fecha, enlaces y alcance.

## Instalar el candidato 0.3.1 en Claude Code

```text
/plugin install licita-espana --marketplace https://github.com/samihalawa/licita-espana.git#release/v0.3.0-local
```

O desde terminal:

```bash
claude plugin marketplace add https://github.com/samihalawa/licita-espana.git#release/v0.3.0-local
claude plugin install licita-espana@licita-espana
```

Después, pregunta en lenguaje natural o invoca `/licita-espana:licita-espana`.

## Ejemplo sin conexión

Pide al MCP declarado `licita-espana` la herramienta `licita_espana_demo`. El ejemplo conserva su fecha y sus fuentes; nunca se presenta como una consulta actual.

## Consulta e informe

El anfitrión invoca `licita_triage` con los argumentos descritos en [Esquemas MCP](skills/licita-espana/references/mcp-tools.json). Para obtener un informe determinista, utiliza `licita_espana_report` con la operación elegida, sus argumentos y el formato `markdown`, `html` o `json`. La herramienta devuelve texto; no guarda archivos. El anfitrión puede guardar el resultado únicamente en la ruta solicitada por el usuario.

## Dónde funciona

| Entorno | Comportamiento |
|---|---|
| Claude Code con MCP habilitado y Python 3.11+ | Proceso MCP local declarado, adaptadores e informes. |
| Anfitrión sin MCP local | Solo navegación/archivos nativos autorizados; no se ejecutan scripts como alternativa ni se afirma haber ejecutado el adaptador. |
| Sin red | Herramienta de ejemplo guardado; no se inventan datos actuales. |

No hay servidor público, escucha de red ni instalación de dependencias. El único proceso de ejecución del plugin es el MCP declarado. Las instrucciones de desarrollo están separadas del flujo de uso.

## Alcance real

Ventana acotada del feed de PLACSP, no todas las licitaciones españolas. No lee automáticamente los PDF ni presenta ofertas. La decisión requiere pliegos, correcciones y perfil oficial.

## Verificación

[Desarrollo y pruebas](DEVELOPMENT.md). Las comprobaciones de instalación y protocolo no equivalen a aprobación del directorio ni a aceptación en todos los anfitriones.

[Mejoras y crítica](CHANGELOG.md) · [Evidencia versionada](evidence/) · [Revisión de Claude](SUBMISSION.md). Los tests no equivalen a adopción. `ci/validate.yml` es una plantilla inactiva.

**English:** An independent workflow for Spanish official data, with a self-contained Python adapter, offline example and readable reports. Answer language follows the user.

**Sami Halawa** · Software independiente; sin afiliación oficial. [Privacidad](PRIVACY.md) · [Condiciones](TERMS.md) · [Soporte](SUPPORT.md) · [Seguridad](SECURITY.md).

## Disponibilidad y cobertura de la fuente

Las páginas Atom de PLACSP pueden superar 8 MiB. El adaptador conserva el límite: usa una ventana inicial de hasta 1 MiB para limitar la latencia y solo procesa entradas XML completas dentro de ese prefijo y marca el resultado como parcial. La huella SHA-256 identifica los bytes del prefijo, no el documento completo. Los registros y las cancelaciones que quedan fuera no se han comprobado.

`next_request` continúa entre las coincidencias observadas dentro del prefijo. Al llegar al final de los bytes comprobados, la continuación se detiene: no salta registros no leídos. Si aparece `older_page_cursor`, señala otra ventana anterior de la fuente, no una continuación exhaustiva. Una búsqueda sin coincidencias en este prefijo no acredita ausencia de licitaciones. Comprueba siempre el perfil oficial.

## Datos enviados a servicios externos

Las consultas en vivo envían únicamente los parámetros públicos necesarios de la consulta a los servicios oficiales identificados en [Fuentes y endpoints](skills/licita-espana/references/sources.md). El proveedor recibe esos parámetros y la dirección de red del entorno que ejecuta la consulta. No se envían credenciales, adjuntos, perfiles personales ni el historial de conversación. Estos accesos se realizan desde el MCP local declarado o las herramientas nativas autorizadas del anfitrión; no existe un conector público alojado. Los proxies con credenciales heredadas se rechazan antes de realizar una conexión.

Las respuestas oficiales pueden contener nombres, direcciones u otros datos personales públicos. La caché local es solo de memoria, durante un máximo de cinco minutos mientras se ejecuta el proceso. Los resultados pueden permanecer en la conversación o en informes guardados explícitamente por el usuario; su conservación depende del anfitrión y del usuario. El editor no opera un servicio que reciba o almacene estos datos. Consulta [Privacidad](PRIVACY.md) para los detalles y los límites de reutilización.
