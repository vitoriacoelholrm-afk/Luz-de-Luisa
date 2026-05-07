# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Projeto

Catálogo digital da **Boutique Luz de Luisa** — loja física e virtual de moda feminina em Contagem/MG.

- Site público: https://vitoriacoelholrm-afk.github.io/Luz-de-Luisa/
- Repositório: https://github.com/vitoriacoelholrm-afk/Luz-de-Luisa
- Instagram: @boutique.luzdeluisa
- Endereço: Rua Rio Poti 421, Novo Riacho · Contagem/MG

## Estrutura

Projeto estático com um único arquivo principal:

- `index.html` — catálogo completo (HTML + CSS inline + SVG)
- `logo.png` — logo oficial da boutique (fundo rosa, exibida no nav)
- `.claude/launch.json` — configuração do servidor de prévia local (porta 3000, Python http.server)

## Servidor de prévia

```bash
# Iniciado automaticamente pelo Claude Preview via .claude/launch.json
python -m http.server 3000
```

## Deploy

O site é publicado via **GitHub Pages** (branch `master`, raiz `/`). Qualquer `git push` para `master` atualiza o site público automaticamente em alguns minutos.

```bash
git add <arquivos>
git commit -m "mensagem"
git push
```

## Arquitetura do index.html

O arquivo é dividido em seções na seguinte ordem:

1. **Nav** — logo + links de navegação + botão "Comprar Online"
2. **Hero** — headline principal, botões de CTA e estatísticas (posts/seguidoras)
3. **Strip** — barra de benefícios (frete, troca, endereço)
4. **Novidades** (`#novidades` / `#colecao`) — grid 3 colunas de produtos com badges, preços e swatches de cor
5. **Banner quote** — citação da loja + contador de seguidoras + link Instagram
6. **Lookbook** (`#lookbook`) — grade de looks combinados
7. **Sobre** (`#sobre`) — história da loja + estatísticas
8. **Depoimentos** (`#depoimentos`) — avaliações reais do Google (Kaylane Silva, Bianca Crisley, Thais Couto Reis)
9. **Newsletter** — formulário de cadastro de e-mail
10. **Footer** — links, redes sociais e informações de contato

## Paleta de cores (variáveis CSS)

| Variável     | Valor     | Uso                        |
|--------------|-----------|----------------------------|
| `--pink`     | `#e8357a` | Cor principal, nav         |
| `--pink-lt`  | `#fde8f0` | Fundos suaves              |
| `--pink-dk`  | `#9b1a4a` | Títulos, textos de destaque|
| `--hot`      | `#ff4d8d` | Gradientes, botões         |
| `--cream`    | `#fff8fb` | Fundo do body              |
| `--muted`    | `#c47a9a` | Textos secundários         |
| `--gold`     | `#e8c060` | Estrelas, badges especiais |

## Fontes

- `Playfair Display` — títulos e destaques (serif, itálico)
- `Nunito` — corpo do texto (sans-serif)

## Identidade visual

- O nav tem fundo `var(--pink)` com links brancos
- A logo (`logo.png`) é exibida no nav com `height: 56px; width: auto`
- Badges de produto: `.b-new` (rosa), `.b-hot` (rosa escuro), `.b-sale` (vermelho), `.b-sp` (dourado)
