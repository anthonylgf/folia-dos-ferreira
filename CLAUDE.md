# CLAUDE.md

Este arquivo fornece orientações ao Claude Code (claude.ai/code) ao trabalhar com o código neste repositório.

## Visão Geral do Projeto

Site estático para preservar a história e tradições da Folia de Reis da Familia Ferreira, da região de Januária, situada em Minas Gerais. O site foi construído com Jekyll e hospedado no GitHub Pages. O conteúdo está em português (pt-BR).

**Site ao vivo:** https://foliadereisdosferreiras.com.br

## Dependências
Lista de dependências para rodar o projeto

- Ruby
- Jekyll
- Bundler (gerenciador de dependências do Ruby)

## Comandos Comuns

```bash
# Instalar dependências
bundle install

# Iniciar servidor de desenvolvimento (com live reload)
bundle exec jekyll serve

# Builds incrementais mais rápidos durante o desenvolvimento
bundle exec jekyll serve --incremental

# Gerar arquivos estáticos em _site/
bundle exec jekyll build

# Limpar arquivos gerados e cache
bundle exec jekyll clean
```

## Arquitetura

**Site estático Jekyll** usando o tema remoto `minimal-mistakes` (skin: `neon`).

### Estrutura de Conteúdo

- `_pages/` — Todo o conteúdo do site em arquivos Markdown
  - `tabelas/` — Páginas de tabelas com cantos/versos (tabela-*.md)
  - `linha-do-tempo.md` — Linha do tempo dos imperadores organizada por década
  - `lista-tabelas.md` — Página de índice listando todas as tabelas
  - `contrubuir.md` - Página com instruções sobre como contribuir para o projeto
- `_data/navigation.yml` — Define todos os menus de navegação (menu principal + estrutura de sidebar com seções por década)
- `_config.yml` — Configuração do Jekyll incluindo tema, plugins, URL base (`/folia-dos-ferreira`) e metadados do autor/redes sociais
- `CNAME` - Arquivo necessário para configurar os domínios customizados no Github Pages
- `index.html` - Página inicial do projeto, com os links apontando para redes sociais e outras páginas
- `assets/images/` — Imagens e logos do site

### Sistema de Navegação

Toda a navegação é definida em `_data/navigation.yml`. Ao adicionar novas páginas, atualize tanto o menu `main` quanto o sidebar `docs` conforme necessário. O sidebar possui seções por década para a linha do tempo.

### Deploy

Totalmente automatizado via GitHub Actions (`.github/workflows/deploy-site-jekyll.yml`). Um push para o branch `master` dispara o build e o deploy no GitHub Pages. Nenhuma etapa manual é necessária.

### Adicionando Conteúdo

- Novas tabelas vão em `_pages/tabelas/` seguindo as convenções dos arquivos existentes
- Após adicionar ou remover alguma página, verificar se a navegação está correta no arquivo `_data/navigation.yml` no sidebar `docs`
- A URL base é `/folia-dos-ferreira` — use URLs relativas ou o filtro `| relative_url` do Jekyll para evitar links quebrados
