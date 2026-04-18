# Folia dos Ferreira

Site dedicado a preservar a história e as tradições da Folia de Reis da família Ferreira, localizada no distrito de São Joaquim, na cidade de Januária, Minas Gerais. Desde 1952 com muita devoção e tradição.

O site apresenta a linha do tempo dos imperadores da folia, as tabelas (cânticos cerimoniais) utilizadas durante os festejos, e links para as redes sociais da comunidade.

**Acesse o site:** [https://foliadereisdosferreiras.com.br](https://foliadereisdosferreiras.com.br)

---

## Stack tecnológica

| Tecnologia | Descrição |
|---|---|
| [Jekyll](https://jekyllrb.com/) | Gerador de sites estáticos |
| [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) | Tema Jekyll (remote theme) |
| [GitHub Pages](https://pages.github.com/) | Hospedagem e deploy automático |
| Ruby | Linguagem base do Jekyll |

---

## Pré-requisitos

Antes de executar o projeto localmente, certifique-se de ter instalado:

- **Ruby** (versão compatível com a gem `github-pages`)
- **Bundler** (gerenciador de dependências Ruby)
- **Git**

### Instalação dos pré-requisitos (macOS)

```bash
# Instalar Ruby via Homebrew
brew install ruby

# Instalar o Bundler
gem install bundler
```

### Instalação dos pré-requisitos (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev git
gem install bundler
```

---

## Dependências do projeto

As dependências estão definidas no `Gemfile`:

- **github-pages** - Inclui o Jekyll e todas as dependências necessárias para compatibilidade com GitHub Pages (inclui transitivamente o `jekyll-seo-tag` para geração de meta tags SEO e dados estruturados)
- **jekyll-paginate** - Paginação de posts
- **jekyll-sitemap** - Geração automática de sitemap
- **jekyll-gist** - Incorporação de GitHub Gists
- **jekyll-feed** - Geração de feed RSS
- **jemoji** - Suporte a emojis
- **jekyll-include-cache** - Otimização de performance
- **tzinfo-data** - Dados de fuso horário (necessário em Windows e alguns ambientes Linux)
- **wdm** - Monitor de arquivos para live reload (apenas Windows)

---

## Como executar localmente

```bash
# 1. Clonar o repositório
git clone https://github.com/anthonylgf/folia-dos-ferreira.git
cd folia-dos-ferreira

# 2. Instalar as dependências
bundle install

# 3. Iniciar o servidor de desenvolvimento
bundle exec jekyll serve
```

O site estará disponível em: **http://localhost:4000/**

### Comandos úteis

| Comando | Descrição |
|---|---|
| `bundle exec jekyll serve` | Inicia o servidor local com watch (auto-rebuild) |
| `bundle exec jekyll serve --incremental` | Rebuild incremental (mais rápido) |
| `bundle exec jekyll build` | Gera os arquivos estáticos em `_site/` |
| `bundle exec jekyll clean` | Remove os arquivos gerados (`_site/`, cache) |

---

## Estrutura do projeto

```
folia-dos-ferreira/
├── _config.yml              # Configuração principal do site
├── _data/
│   └── navigation.yml       # Estrutura de navegação (menus)
├── _includes/
│   └── head/
│       └── custom.html      # Extensões do HEAD (JSON-LD, meta tags SEO)
├── _pages/
│   ├── 404.md               # Página de erro 404 (caso o usuário acesse um caminho que não existe)
│   ├── contribuir.md        # Como contribuir com o projeto
│   ├── linha-do-tempo.md    # Linha do tempo dos imperadores
│   ├── lista-tabelas.md     # Índice das tabelas cerimoniais
│   └── tabelas/             # Tabelas (cânticos) e versos utilizados na folia
├── assets/
│   └── images/              # Imagens e logos do site
├── index.html               # Página inicial
├── robots.txt               # Configuração para crawlers (sitemap)
├── CNAME                    # Domínio customizado para GitHub Pages
├── Gemfile                  # Dependências Ruby
```

---

## SEO e Dados Estruturados

O site possui otimizações para melhorar a descoberta nos mecanismos de busca:

- **`_includes/head/custom.html`** - Adiciona dados estruturados JSON-LD (Schema.org) com informações sobre a organização, o site (WebSite) e redes sociais
- **`robots.txt`** - Arquivo que permite indexação completa e aponta crawlers para o sitemap
- **Meta tags otimizadas** - Descrições e títulos ricos em palavras-chave relevantes (folia de reis, terno de reis, Januária, MG)
- **`jekyll-seo-tag`** - Incluído via `github-pages`, gera automaticamente meta tags Open Graph (og:title, og:description, og:image) para compartilhamento em redes sociais

O Jekyll com `jekyll-sitemap` gera automaticamente o arquivo `sitemap.xml` que facilita a indexação de todas as páginas pelo Google e outros buscadores.

---

## Deploy

O deploy é realizado automaticamente via **GitHub Actions**. Ao fazer push na branch `master`, o workflow `.github/workflows/deploy-site-jekyll.yml` dispara o build com Jekyll e publica o site no **GitHub Pages** em:

**https://foliadereisdosferreiras.com.br**

Nenhuma configuração adicional é necessária.
