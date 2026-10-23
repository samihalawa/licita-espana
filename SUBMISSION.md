# Claude review — Licita España 0.3.0

Publisher: Sami Halawa · Contact: sami@samihalawa.com

Repository: https://github.com/samihalawa/licita-espana

Plugin at repository root. Stable identity: `licita-espana`.

## Listing

Encuentra licitaciones y convierte sus pliegos en una decisión documentada: requisitos, plazos y próximos pasos.

Audience: Autónomos, pymes y consultoras que preparan ofertas públicas.

First prompt: Busca licitaciones de software y separa los plazos futuros de los ya vencidos.

## Reviewer walkthrough

Install with `/plugin install licita-espana --marketplace samihalawa/licita-espana`. Ask for an example: `demo` must be labelled as a saved snapshot, not live. The captured response is in `skills/licita-espana/references/demo.json`. Run the live README example in an authorized Python 3.11+ environment, inspect scope and source dates, then export HTML. The report must not execute source text or load external assets.

Negative fixtures in `tests/test_core.py` are synthetic regressions, not live user tests. No credentials, product account, purchase or API key is required. This is a skills package, not a hosted MCP service.

## Included review materials

README, CHANGELOG, real icon, support/privacy/terms, static page source in docs/, saved official-source example, executable tests and versioned evidence. Dataset/service rights are separate from the MIT software licence.

## Scope

Ventana acotada del feed de PLACSP, no todas las licitaciones españolas. No lee automáticamente los PDF ni presenta ofertas. La decisión requiere pliegos, correcciones y perfil oficial.

Read evidence for the actual completed checks. CI is an inactive template. Source publication, package validation, installation, user acceptance, directory review and adoption are separate states. No official listing or approval is claimed. Submit through https://claude.ai/directory/manage under the intended verified publisher identity; applicable publisher attestations remain with the owner.
