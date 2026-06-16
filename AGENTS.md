# AGENTS.md
Este arquivo fornece instruções para auxiliar a IA a trabalhar com o projeto. A função do agente é ajudar no desenvolvimento e revisão do código, seguindo as melhores práticas de desenvolvimento.

## Visão Geral do Projeto
Site estático para preservar a história e tradições da Folia de Reis da Familia Ferreira, da região de Januária, situada em Minas Gerais. O site foi construído com Jekyll e hospedado no GitHub Pages. O conteúdo está em português (pt-BR).

## Dependências
Lista de dependências para rodar o projeto
- Ruby 3.2
- Jekyll
- Bundler (gerenciador de dependências do Ruby)
- Docker e Docker Compose (para subir o projeto em containers)

## Comandos Comuns
### Executar projeto no terminal
```bash
# Instalar dependências
bundle install

# Iniciar servidor de desenvolvimento na porta 4010 (com live reload)
bundle exec jekyll serve --port 4010

# Builds incrementais mais rápidos durante o desenvolvimento
bundle exec jekyll serve --incremental

# Gerar arquivos estáticos em _site/
bundle exec jekyll build

# Limpar arquivos gerados e cache
bundle exec jekyll clean
```

### Executar projeto utilizando Docker
```bash
# Iniciar projeto em background (site disponivel na porta 4000)
docker compose up -d

# Derrubar projeto e excluir volumes
docker compose down -v
```

## Arquitetura
### Sistema de Navegação
A navegação, excluindo o menu da página inicial, é definida em `_data/navigation.yml`. Ao adicionar novas páginas, atualize tanto o menu `main` quanto o sidebar `docs` conforme necessário. O sidebar possui seções por década para a linha do tempo.

Ao adicionar novas páginas, verifique-se se deve modificar o menu da página inicial também.

### Deploy
Totalmente automatizado via GitHub Actions (`.github/workflows/deploy-site-jekyll.yml`). Um push para o branch `master` dispara o build e o deploy no GitHub Pages. Nenhuma etapa manual é necessária.

### Adicionando Conteúdo
- Novas tabelas vão em `_pages/tabelas/` seguindo as convenções dos arquivos existentes
- Após adicionar ou remover alguma página, verificar se a navegação está correta no arquivo `_data/navigation.yml` no sidebar `docs` e se é necessário mudar o menu da página inicial no arquivo `index.yml`
- A URL base é `/folia-dos-ferreira` — use URLs relativas ou o filtro `| relative_url` do Jekyll para evitar links quebrados

## Regras de Código
- Evite adicionar customizações de CSS diretamente nos arquivos html, sempre prefira adicionar nos arquivos da pasta `assets/css` e referênciá-los posteriormente
- 

### Responsividade
- Ao adicionar ou modificar uma página, certifique-se que irá funcionar tanto em telas de laptops e computadores quanto de dispositivos móveis

### Acessibilidade
- Sempre-se certifique-se que as telas, ao utilizar HTML e CSS, estão seguindo as melhores práticas relacionadas a acessibilidade

### SEO
- O site utiliza alguns mecanismos para melhorar os fluxos de SEO nas páginas. Siga sempre as melhores práticas de desenvolvimento nesse quesito, para tornar as páginas acessíveis para mecanismos de buscas e agentes de IA.

## Segurança
- Sempre garanta que não existem informações confidenciais no código do projeto.
- Certifique-se que os links para páginas externas são confiáveis e sem tags de rastreabilidade
- Certifique-se de que as dependências de Ruby adicionadas não possuem riscos de segurança

## Documentação
- A cada mudança, certifique-se que a documentação no `README.md` está atualizada

## Fluxo commit
Ao realizar alguma alteração, sempre siga os seguintes passos:
- Certifique-se que não está realizando o commit na branch `master`.
  - Caso esteja na master, crie uma nova branch
  - Caso esteja em outra branch, pergunte se o commit será na branch atual ou se deve criar uma nova
  - A nova branch deve seguir a regra de nomenclatura semântica(feat/nome-branch, docs/nome-branch, refactor/nome-branch, fix/nome-branch, chore/nome-branch, etc.)
- Faça o commit com uma mensagem objetiva seguindo as regras do [conventional commit](https://www.conventionalcommits.org/en/v1.0.0/), como por exemplo: `feat: mensagem`, `fix: mensagem`, `tests: mensagem`, `refactor: mensagem, etc.
- Pergunte sempre se o usuário deseja realizar o push para o remote
