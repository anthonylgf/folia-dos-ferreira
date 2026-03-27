# Folia dos Ferreira

Site dedicado a preservar a historia e as tradicoes da Folia de Reis da familia Ferreira, localizada no distrito de Sao Joaquim, na cidade de Januaria, Minas Gerais. Desde 1952 com muita devocao e tradicao.

O site apresenta a linha do tempo dos imperadores da folia, as tabelas (canticos cerimoniais) utilizadas durante os festejos, e links para as redes sociais da comunidade.

**Acesse o site:** [https://foliadereisdosferreiras.com.br](https://foliadereisdosferreiras.com.br)

---

## Stack tecnologica

| Tecnologia | Descricao |
|---|---|
| [Jekyll](https://jekyllrb.com/) | Gerador de sites estaticos |
| [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) | Tema Jekyll (remote theme) |
| [GitHub Pages](https://pages.github.com/) | Hospedagem e deploy automatico |
| Ruby | Linguagem base do Jekyll |

---

## Pre-requisitos

Antes de executar o projeto localmente, certifique-se de ter instalado:

- **Ruby** (versao compativel com a gem `github-pages`)
- **Bundler** (gerenciador de dependencias Ruby)
- **Git**

### Instalacao dos pre-requisitos (macOS)

```bash
# Instalar Ruby via Homebrew
brew install ruby

# Instalar o Bundler
gem install bundler
```

### Instalacao dos pre-requisitos (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev git
gem install bundler
```

---

## Dependencias do projeto

As dependencias estao definidas no `Gemfile`:

- **github-pages** - Inclui o Jekyll e todas as dependencias necessarias para compatibilidade com GitHub Pages
- **jekyll-paginate** - Paginacao de posts
- **jekyll-sitemap** - Geracao automatica de sitemap
- **jekyll-gist** - Incorporacao de GitHub Gists
- **jekyll-feed** - Geracao de feed RSS
- **jekyll-seo-tag** - Geracao de meta tags SEO e dados estruturados
- **jemoji** - Suporte a emojis
- **jekyll-include-cache** - Otimizacao de performance
- **jekyll-algolia** - Integracao com busca Algolia

---

## Como executar localmente

```bash
# 1. Clonar o repositorio
git clone https://github.com/anthonylgf/folia-dos-ferreira.git
cd folia-dos-ferreira

# 2. Instalar as dependencias
bundle install

# 3. Iniciar o servidor de desenvolvimento
bundle exec jekyll serve
```

O site estara disponivel em: **http://localhost:4000/**

### Comandos uteis

| Comando | Descricao |
|---|---|
| `bundle exec jekyll serve` | Inicia o servidor local com watch (auto-rebuild) |
| `bundle exec jekyll serve --incremental` | Rebuild incremental (mais rapido) |
| `bundle exec jekyll build` | Gera os arquivos estaticos em `_site/` |
| `bundle exec jekyll clean` | Remove os arquivos gerados (`_site/`, cache) |

---

## Estrutura do projeto

```
folia-dos-ferreira/
├── _config.yml              # Configuracao principal do site
├── _data/
│   └── navigation.yml       # Estrutura de navegacao (menus)
├── _includes/
│   └── head/
│       └── custom.html      # Extensoes do HEAD (JSON-LD, meta tags SEO)
├── _pages/
│   ├── 404.md               # Pagina de erro 404 (caso o usuário acesse um caminho que não existe)
│   ├── contribuir.md        # Como contribuir com o projeto
│   ├── linha-do-tempo.md    # Linha do tempo dos imperadores
│   ├── lista-tabelas.md     # Indice das tabelas cerimoniais
│   └── tabelas/             # Tabelas (canticos) e versos utilizados na folia
├── assets/
│   └── images/              # Imagens e logos do site
├── index.html               # Pagina inicial
├── robots.txt               # Configuracao para crawlers (sitemap)
├── CNAME                    # Dominio customizado para GitHub Pages
├── Gemfile                  # Dependencias Ruby
```

---

## SEO e Dados Estruturados

O site possui otimizacoes para melhorar a descoberta nos mecanismos de busca:

- **`_includes/head/custom.html`** - Adiciona dados estruturados JSON-LD (Schema.org) com informacoes sobre a organizacao, rede social, e funcionalidade de busca
- **`robots.txt`** - Arquivo que permite indexacao completa e aponta crawlers para o sitemap
- **Meta tags otimizadas** - Descricoes e titulos ricos em palavras-chave relevantes (folia de reis, terno de reis, Januaria, MG)
- **`jekyll-seo-tag`** - Plugin que gera automaticamente meta tags Open Graph (og:title, og:description, og:image) para compartilhamento em redes sociais

O Jekyll com `jekyll-sitemap` gera automaticamente o arquivo `sitemap.xml` que facilita a indexacao de todas as paginas pelo Google e outros buscadores.

---

## Deploy

O deploy e realizado automaticamente pelo **GitHub Pages**. Ao fazer push na branch principal do repositorio, o GitHub Pages compila o site com Jekyll e publica em:

**https://foliadereisdosferreiras.com.br**

Nenhuma configuracao adicional de CI/CD e necessaria.
