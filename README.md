# Pessoal

Portfólio pessoal e projetos próprios — site de apresentação e um PWA de lista de compras.

## Projetos

| Pasta | O que é | Publicado |
|-------|---------|-----------|
| [`about.me/`](about.me/) | Site de portfólio (HTML/CSS/JS) | [hcerqueira.github.io/about.me](https://hcerqueira.github.io/about.me/) |
| [`lista-de-compra/`](lista-de-compra/) | PWA de lista de compras e estoque doméstico | GitHub Pages |

## about.me

Site estático de portfólio, uma breve apresentação pessoal.
Ver [`about.me/README.md`](about.me/README.md).

## lista-de-compra

Aplicativo web (PWA) para controle de compras e estoque doméstico.
Funciona online e offline, instalável em tablets, celulares e PCs.

Features principais:

- Controle de itens, quantidades, preços e categorias
- Cálculo automático de quantidade a comprar
- Histórico de compras e gastos mensais
- Dashboard resumido
- Sincronização opcional com Google Sheets

Ver [`lista-de-compra/README.md`](lista-de-compra/README.md) para detalhes.

## Desenvolvimento local

Cada projeto roda standalone, sem build step:

```bash
python3 -m http.server 8000
# about.me:          http://localhost:8000/about.me/
# lista-de-compra:   http://localhost:8000/lista-de-compra/
Deploy
GitHub Pages serve direto do branch main. Commit no main = deploy automático.

Segurança
Pre-commit com gitleaks ativo. Dados sensíveis fora do repositório.

Última atualização: 2026-09-11
