<p><img src="assets/icon.png" width="72" height="72" alt="Icono de Licita España"></p>

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

## Instalar en Claude Code

```text
/plugin install licita-espana --marketplace samihalawa/licita-espana
```

O desde terminal:

```bash
claude plugin marketplace add samihalawa/licita-espana
claude plugin install licita-espana@licita-espana
```

Después, pregunta en lenguaje natural o invoca `/licita-espana:licita-espana`.

## Ver un resultado sin conexión

Desde una copia de este repositorio:

```bash
python3 skills/licita-espana/scripts/run.py demo
python3 skills/licita-espana/scripts/run.py demo --format html --output ejemplo.html
```

## Consultar y guardar un informe

```bash
python3 skills/licita-espana/scripts/run.py report licita_triage --json '{"max_pages": 1, "limit": 5}'
```

Añade `--format html --output informe.html` o `--format json`. No se sobrescriben archivos por defecto. `doctor` comprueba el entorno local sin consultar proveedores.

## Dónde funciona

| Entorno | Comportamiento |
|---|---|
| Claude Code / Codex con Python y red autorizada | Adaptadores e informes ejecutables. |
| ChatGPT con navegación/archivos | Flujo con herramientas nativas disponibles; no es un MCP alojado. |
| Sin red | Demo guardada o documentos aportados; no datos actuales inventados. |

## Alcance real

Ventana acotada del feed de PLACSP, no todas las licitaciones españolas. No lee automáticamente los PDF ni presenta ofertas. La decisión requiere pliegos, correcciones y perfil oficial.

## Verificación

```bash
python3 -m unittest discover -s tests -v
python3 scripts/check_package.py
claude plugin validate --strict .claude-plugin/plugin.json
claude plugin validate --strict .
```

[Mejoras y crítica](CHANGELOG.md) · [Evidencia versionada](evidence/) · [Revisión de Claude](SUBMISSION.md). Los tests no equivalen a adopción. `ci/validate.yml` es una plantilla inactiva.

**English:** An independent workflow for Spanish official data, with a self-contained Python adapter, offline example and readable reports. Answer language follows the user.

**Sami Halawa** · Software independiente; sin afiliación oficial. [Privacidad](PRIVACY.md) · [Condiciones](TERMS.md) · [Soporte](SUPPORT.md) · [Seguridad](SECURITY.md).

## Disponibilidad y cobertura de la fuente

Las páginas Atom de PLACSP pueden superar 8 MiB. El adaptador conserva el límite: usa una ventana inicial de hasta 1 MiB para limitar la latencia y solo procesa entradas XML completas dentro de ese prefijo y marca el resultado como parcial. La huella SHA-256 identifica los bytes del prefijo, no el documento completo. Los registros y las cancelaciones que quedan fuera no se han comprobado.

`next_request` continúa entre las coincidencias observadas dentro del prefijo. Al llegar al final de los bytes comprobados, la continuación se detiene: no salta registros no leídos. Si aparece `older_page_cursor`, señala otra ventana anterior de la fuente, no una continuación exhaustiva. Una búsqueda sin coincidencias en este prefijo no acredita ausencia de licitaciones. Comprueba siempre el perfil oficial.
