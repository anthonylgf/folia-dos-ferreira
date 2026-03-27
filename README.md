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
├── _pages/
│   ├── 404.md               # Pagina de erro 404
│   ├── contribuir.md        # Como contribuir com o projeto
│   ├── linha-do-tempo.md    # Linha do tempo dos imperadores
│   ├── lista-tabelas.md     # Indice das tabelas cerimoniais
│   └── tabelas/             # Tabelas (canticos) e versos utilizados na folia
├── assets/
│   └── images/              # Imagens e logos do site
├── index.html               # Pagina inicial (layout splash)
├── Gemfile                  # Dependencias Ruby
└── README.md                # Este arquivo
```

---

## Deploy

O deploy e realizado automaticamente pelo **GitHub Pages**. Ao fazer push na branch principal do repositorio, o GitHub Pages compila o site com Jekyll e publica em:

**https://foliadereisdosferreiras.com.br**

Nenhuma configuracao adicional de CI/CD e necessaria.
