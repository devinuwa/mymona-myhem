<!-- l10n-sync: source-file="README.md" -->
🌐 [English](README.md) | [Español](README.es.md) | Português (Brasil) | [한국어](README.ko.md)

# 🎮 Mona Mayhem

**Workshop de VS Code e GitHub Copilot CLI** — Construa uma Arena de Batalha de Contribuições GitHub

Um template de workshop para criar um site retrô em estilo arcade com Astro que compara os gráficos de contribuição do GitHub de dois usuários. Este é o ponto de partida — você vai construir o app passo a passo com o GitHub Copilot.

![Mona Mayhem Screenshot](https://github.com/user-attachments/assets/5eca79e2-cb9f-4e93-aa0d-23666ebde3b7)
*O que você vai construir ao final do workshop*

## 📚 Workshop

O workshop oferece duas trilhas — siga a que combina com seu fluxo de trabalho preferido:

- **Trilha do VS Code** — Chat, Plan Mode, Agent Mode, agentes em segundo plano e ciclos de revisão nativos do editor
- **Trilha do CLI** — `copilot`, contexto `@file`, `/plan`, edições autônomas, `/fleet`, `/delegate` e `/review`

| Parte | Título | Foco do Copilot |
|-------|--------|-----------------|
| [00](workshop/pt_BR/00-overview.md) | Visão Geral | Seleção da trilha e objetivos de aprendizado |
| [01](workshop/pt_BR/01-setup.md) | Configuração & Engenharia de Contexto | Instruções, permissões e preparação do ambiente |
| [02](workshop/pt_BR/02-plan-and-scaffold.md) | Planejar & Estruturar | Planejamento da API e da arquitetura da página |
| [03](workshop/pt_BR/03-agent-mode.md) | Construir o Jogo | Implementação e iteração agentic |
| [04](workshop/pt_BR/04-design-vibes.md) | Tematização Design-First | Planejamento e implementação do design visual |
| [05](workshop/pt_BR/05-polish.md) | Polimento & Trabalho em Paralelo | Paralelismo, revisões e refinamentos de qualidade |
| [06](workshop/pt_BR/06-bonus.md) | Bônus & Extensões | Ideias abertas de recursos e experimentos extras do Copilot |

## 🚀 Início Rápido

1. **Crie seu próprio repositório primeiro** fazendo qualquer uma destas opções:
   - clique em **Use this template** para criar um novo repositório, ou
   - faça um fork deste repositório.
2. Escolha sua trilha do workshop:
   - **VS Code:** clone seu repositório e abra no VS Code.
   - **GitHub Copilot CLI:** clone seu repositório localmente, instale `copilot` e trabalhe no seu terminal.
3. Siga o [guia do workshop](workshop/pt_BR/00-overview.md)

## Pré-requisitos

### Compartilhados

- GitHub Copilot (Pro, Business ou Enterprise)
- Git
- Node.js

### Trilha do VS Code

- VS Code v1.107+
- Extensão do GitHub Copilot conectada

### Trilha do CLI

- GitHub Copilot CLI (`copilot`)
- Node.js 22+ se você planeja instalar o CLI via `npm install -g @github/copilot`
- Ou Homebrew / WinGet se preferir uma instalação nativa

## Stack Tecnológica

- **Framework**: [Astro](https://astro.build/) v6
- **Runtime**: Node.js com adaptador [@astrojs/node](https://docs.astro.build/en/guides/integrations-guide/node/)
- **Fonte**: Press Start 2P (fonte retrô de videogame)
- **API**: API do gráfico de contribuições do GitHub

## Notas de Implantação

### Configuração atual do GitHub Pages

O workflow em `.github/workflows/deploy.yml` atualmente implanta conteúdo estático de `docs/` e `workshop/` no GitHub Pages. Ele não constrói nem implanta o app Astro de `src/`.

### Se você quiser implantar o app Astro no GitHub Pages

O GitHub Pages é hospedagem estática, então o app Astro deve usar saída estática.

1. Altere `output` em `astro.config.mjs` de `server` para `static`.
2. Remova o adaptador Node (`@astrojs/node`) de `astro.config.mjs` e `package.json`.
3. Atualize o workflow do GitHub Actions para executar `npm ci` e `npm run build`, e depois enviar `dist/` como artefato de Pages.
4. Se você estiver implantando em uma página de projeto (`https://<usuario>.github.io/<repositório>/`), defina `site` e `base` em `astro.config.mjs`.

Se você pretende manter as rotas de API em produção, use uma plataforma de servidor em vez do GitHub Pages (por exemplo, Vercel, Netlify ou um host Node).

## Licença

MIT
