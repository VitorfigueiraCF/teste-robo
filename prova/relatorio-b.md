# Relatório B — 2ª conferência da caixa (sessão nova)

Data: 2026-10-06 (UTC). Sessão: `session_019ao21Q3UCaXgiobnuYhmQw`.
Sessão da 1ª tarefa (pelos trailers dos commits de `teste-a`): `session_01YYXjS6e4tEc8YhJHtFXwTp`.

Nenhum valor de chave aparece neste arquivo.

## 1) Máquina nova (item 8)

- `/tmp/teste-robo-marca.txt`: **NÃO EXISTE** (`ls`: "No such file or directory"; `test -e` rc=1).
- Resultado: **máquina nova PROVADA** pelo critério combinado (o arquivo que a 1ª tarefa deixou não veio).
- ⚠️ Ressalva: em `/tmp` existe `environment-manager-cse_01YYXjS6e4tEc8YhJHtFXwTp.lock`
  (0 bytes, criado em 2026-10-06 15:53:01 UTC). É o ID da sessão da 1ª tarefa, criado
  ~2 min antes do 1º commit dela (15:55). O contêiner foi um "warm spare"
  (`warm_spare_claimed=true`, `spare_origin=spawned`). Leitura provável: o contêiner novo nasce
  de uma imagem/snapshot do ambiente capturada no início da 1ª sessão. O que essa sessão
  gravou depois (o marcador) não veio. Então é um contêiner novo, mas não uma máquina "em branco".
- À parte (prova só que a sessão lê o repo, não prova máquina nova): o ramo `teste-a` aparece,
  com `prova/soma.py` e `prova/relatorio-a.md` (commits `e5651d8` e `1cb49f0`).

## 2) Chaves (só existência)

| Variável | Estado |
|---|---|
| `AWS_ACCESS_KEY_ID` | NÃO-VAZIA |
| `AWS_SECRET_ACCESS_KEY` | NÃO-VAZIA |
| `CLOUDSDK_AUTH_ACCESS_TOKEN` | NÃO-VAZIA |

Nenhuma foi impressa, comparada ou usada.

## 3) Saída de rede

Comando (uma única vez): `curl -sS -I --max-time 10 https://example.com`

Resultado cru:

```
curl: (56) CONNECT tunnel failed, response 403
HTTP/1.1 403 Forbidden
Content-Type: text/plain; charset=utf-8
X-Content-Type-Options: nosniff
Content-Length: 69
Connection: close

curl_exit=56
```

Classificação: **NÃO MEDIDO**. Quem respondeu 403 foi o proxy de saída da sessão, não o example.com.
É bloqueio de proxy. Não é "sem conexão/sem rota/DNS", então não prova DESLIGADA.
Observação: a saída passa por um proxy com filtro, e esse proxy deixou o `git fetch` no GitHub
passar. Por isso a contenção destas chaves **não está provada**.

## 4) GitHub Actions

**Não sei.** A API listou 0 workflows e 0 execuções, e não há `.github/` em `main` nem em `teste-a`.
Isso não diz se o Actions está ligado ou desligado no repositório. Nada foi criado nem executado.
