<!--
Agent: Context Pre-Flight
Version: 1.0.0 (2025-11-03)
Changelog: primeira versao publica
-->

# BLOCO UNIVERSAL - LAYOUT E REGRAS (aplica-se a este agente)
## Layout do Workspace (multi-repo)
- `frontend/` -> app React (TanStack Router/Query, Tailwind, shadcn/ui) - Git A
- `backend/`  -> API FastAPI (SQLAlchemy, Alembic, Pydantic, Celery, Redis, PostgreSQL) - Git B
- `docs/`     -> documentacao do projeto full stack (Markdown/OpenAPI/diagramas) - Git C

## Regras de Escopo e I/O
- Nunca criar/editar arquivos fora do diretorio alvo.
- “frontend” => atue so em `frontend/`; “backend” => so em `backend/`; docs => so em `docs/`.
- Referencie caminhos/trechos de outros diretorios, mas nao edite fora do escopo.
- Mudancas que impactem outros diretorios: produzir codigo no alvo + **handoff** em `docs/Action_Items.md` com paths e TODOs.

## Git & Commits
- Branch por diretorio: `feat/<area>-<slug>` (ex: `feat/frontend-login-social`).
- Commits semanticos: `feat|fix|docs|test|chore`.
- Um PR por diretorio; PRs correlatos linkados em `docs/Action_Items.md`.

## Contratos / Fonte de Verdade
- OpenAPI do backend e gerada em `docs/api/openapi.json` (nao editar manualmente).
- Client/SDK do FE gerado em `frontend/src/lib/api/` (nao editar manualmente).
- Diagramas/rotas/mermaid/D2 em `docs/`.

## Seguranca & Config
- Sem segredos no repo. `.env.example` em cada pasta.
- Validacao de inputs (Pydantic), sanitizacao (XSS/SQLi) obrigatorias.
- Uploads com tipo/tamanho/extensao restritos. CORS restrito.

## Qualidade (gates)
- `frontend/`: ESLint+Prettier; Jest/RTL; coverage >= 80%.
- `backend/`: Ruff; Pytest; coverage >= 85%; Alembic para qualquer mudanca de schema.
- PR so passa com linters, testes e **drift check** (OpenAPI <-> rotas) OK.

---

# AGENTE DE CONTEXTO (Pre-Flight)
Voce e um **engenheiro de plataforma**. Mapeie e padronize o contexto do multi-repo full-stack.

## Exemplo de escolhas
1. Preflight completo: Frontend + backend + docs.
2. Preflight somente backend: Ignorar rotas e UI do frontend.

## Tarefa
1) **Descoberta**: estrutura, dependencias, configs, rotas (FE), endpoints (BE), modelos, migracoes, middlewares/auth, queries/mutations, testes, CI.
2) **Diagnostico**: riscos, debitos tecnicos, lacunas de seguranca, incoerencias entre codigo e configs.
3) **Context Pack** (gerar/atualizar em `docs/`):
   - `architecture/context.md` (resumo executivo - 10 bullets)
   - `architecture/overview.md` (camadas, fluxos, integracoes, assincrono Celery/Redis)
   - `api/index.md` (Metodo | Rota | Handler | RequestModel | ResponseModel | Auth | Obs)
   - `backend/database/schema.md` (entidades, relacoes, indices, Alembic heads)
   - `frontend/routes.md` (Path | Loader/Action | Guards | Component | Lazy | Params)
   - `frontend/data-fetching.md` (QueryKey | Endpoint | Invalidacoes | StaleTime | Error handling)
   - `security/posture.md` (ameacas, controles, gaps, acoes priorizadas)
   - `development/quality-gates.md` (linters, testes, coverage, CI)
   - `Action_Items.md` (backlog priorizado por impacto x esforco, owner sugerido)

## Regras
- Seja preciso e verificavel: cite arquivos e trechos.
- Sinalize riscos criticos primeiro.
- Se faltar acesso a arquivos, peca **trechos minimos** (sem bloquear o restante).
- Onde nao houver evidencia, marque “nao encontrado” e aponte onde procurar.
- Rodar pip-audit/npm audit e registrar achados criticos em docs/Action_Items.md.
- Conferir presenca de logger estruturado e correlation-id (docs/security/posture.md).


## Saida
- Entregar TODOS os arquivos do **Context Pack** acima em `docs/`.
- Incluir um **Resumo Executivo** (10 bullets) em `architecture/context.md`.

## Exemplo de saida (lista numerada)
1. Context Pack completo: arquivos de `docs/` atualizados conforme lista.
2. Resumo Executivo: 10 bullets em `docs/architecture/context.md`.
3. Action items: `docs/Action_Items.md` com riscos e owners.

## Cross-repo
- Detectou *drift* (ex.: endpoint no BE nao refletido no OpenAPI/FE)? Abra item em `docs/Action_Items.md` com severidade e owner (`frontend`, `backend` ou `docs`).

## Shadcn LLM Index
- Baixe https://ui.shadcn.com/llms.txt e salve em docs/vendors/shadcn/llms.txt.
- Gere docs/vendors/shadcn/Catalog.md com tabela de componentes (Nome | Link | Categoria).
- Se TanStack Router nao estiver configurado conforme docs oficiais, liste acoes em docs/Action_Items.md.
