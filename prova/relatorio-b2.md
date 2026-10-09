# Relatório B2 — máquina nova + conectores

Data da medição: 2026-10-09 ~02:30 UTC
Sessão: `session_01UvoenX755Jmm81SusuTLLU` (lock `cse_01UvoenX755Jmm81SusuTLLU`)

## 1) Marcas da tarefa anterior

| Arquivo | Resultado |
|---|---|
| /tmp/marca-inicio.txt | não existe |
| /tmp/marca-meio.txt | não existe |
| $HOME/marca-casa.txt (HOME=/root) | não existe |
| /root/marca-casa.txt | não existe |
| /tmp/marca-fim.txt | não existe |

Máquina nova: **PROVADA** (nenhuma marca apareceu; nenhuma checagem deu erro).

## 2) Arquivos de lock de ambiente em /tmp (só nome e hora)

| Nome | Hora (UTC) |
|---|---|
| environment-manager-cse_01UvoenX755Jmm81SusuTLLU.lock | 2026-10-09 02:29:42 (desta sessão) |
| environment-manager-cse_01YYXjS6e4tEc8YhJHtFXwTp.lock | 2026-10-06 15:53:01 (**OUTRA sessão**) |
| uv-bcb837755ba79986.lock | 2026-10-03 05:41:49 |
| uv-ce9cd633bb00c47d.lock | 2026-10-03 05:41:51 |

Também casam com "environment-manager" (não são lock): `environment-manager-2796066470.diag.log`,
`environment-manager.out`, symlink `code-sign -> /opt/env-runner/environment-manager`.

- Locks: 4 no total (2 de environment-manager + 2 do uv).
- 1 lock é de outra sessão (`cse_01YYXjS6e4tEc8YhJHtFXwTp`, de 2026-10-06, 3 dias antes),
  provavelmente da imagem/cache do ambiente. Ela não carrega nenhuma das marcas da tarefa anterior.

## 3) Sessão viva e lê o repositório

- Ramo `teste-a2` aparece (head `215dc12`) e contém `prova/relatorio-a2.md`: **sim**.
- Isso NÃO prova que a máquina é nova; só mostra que a sessão lê o repositório.

## 4) Conectores / servidores MCP desta sessão (lista crua, nenhum foi usado)

Servidores MCP com ferramentas carregadas nesta sessão:

| Servidor | Estado |
|---|---|
| github | ativo (ferramentas carregadas) |
| claude-code-remote | ativo (ferramentas carregadas) |
| Claude_Docs | ativo (ferramentas carregadas) |
| ccd_session | ativo (ferramentas carregadas) |

Conectores da conta (ListConnectors):

| Conector | installState | connected | enabledInChat |
|---|---|---|---|
| Gmail | not_connected | false | false |
| Google Calendar | not_connected | false | false |
| Google Drive | disconnected | false | false |
| Supabase | disconnected | false | false |
| Vercel | disconnected | false | false |

Config local: `/root/.claude.json` mcpServers = vazio; sem `.mcp.json` nem `.claude/` no repositório.

## Autor deste commit

`Claude <noreply@anthropic.com>`, a identidade git configurada nesta sessão (igual à de `teste-a` e `teste-b`).
Observação: o commit de `teste-a2` foi feito com outra identidade (`VitorfigueiraCF`).
