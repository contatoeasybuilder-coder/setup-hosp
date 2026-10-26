# Easy Estático — setup para Cloudflare Pages

Base enxuta para publicar várias páginas estáticas no mesmo projeto Cloudflare Pages. Cada pasta de primeiro nível com um `index.html` vira uma rota pelo nome da pasta:

**Comece pelo [guia completo, do login à primeira página publicada](GUIA-CLOUDFLARE-PAGES.md).**

Para começar, clone este setup: `git clone https://github.com/contatoeasybuilder-coder/setup-hosp.git`. O guia mostra como enviar a cópia para um repositório seu e conectá-lo ao Cloudflare Pages.

```text
meu-site/             → https://seu-dominio.com/meu-site/
  index.html
  assets/
    estilo.css
    imagem.webp
```

## Criar uma página

1. Crie uma pasta na raiz usando o slug desejado, em minúsculas e sem espaços. Exemplo: `curso-de-fotografia/`.
2. Coloque o `index.html` dentro dela. Referencie arquivos da página por caminhos relativos, como `assets/estilo.css` e `assets/imagem.webp`.
3. Adicione imagens, fontes, CSS e JavaScript numa pasta `assets/` dentro do slug.
4. Faça commit e envie para o GitHub. O Cloudflare Pages publica a rota automaticamente no próximo build.

Também são aceitos exports antigos no formato `slug/html/index.html`, com `slug/css/`, `slug/javascript/` e `slug/assets/`.

## Configurar Cloudflare Pages

Na criação do projeto Pages, conecte o repositório GitHub e configure:

- **Build command:** `bash build.sh`
- **Build output directory:** `_site`
- **Root directory:** deixe vazio (o projeto está na raiz do repositório)
- **Framework preset:** None / sem framework

O script copia cada pasta para `_site/<slug>/`, preservando os assets próprios da página; exports antigos em `slug/html/index.html` também são ajustados. Não edite `_site`: essa pasta é gerada durante o build. No plano Free, o Cloudflare Pages aceita até 20.000 arquivos publicados e até 25 MiB por arquivo.

## Endereços

- A página raiz `/` mostra a página inicial de orientação deste starter.
- Uma página na pasta `curso-de-fotografia/` fica em `/curso-de-fotografia/`.
- Para usar um domínio próprio, associe-o ao projeto Pages no painel do Cloudflare.

## Arquivos de configuração

- `_headers`: cache curto para HTML e assets atualizáveis.
- `_redirects`: ponto para redirects específicos do projeto.
- `404.html`: resposta para rotas inexistentes.
- `build.sh`: prepara o diretório publicado e conserva cada página em seu slug.

Cada página é independente; links entre slugs devem usar caminhos absolutos, por exemplo `/curso-de-fotografia/`.

## Agentes para criar e editar seções

Os arquivos de instruções acompanham o projeto; não exigem instalar extensões.
Abra esta pasta na sua ferramenta de IA e peça, por exemplo:

- **Nova seção a partir de print:** “Leia docs/agentes/secoes-por-print/SKILL.md
  e crie uma seção a partir deste print. Faça o microbriefing sobre o que
  reaproveitar e a identidade visual, pesquise referências e apresente um MVP.”
- **Ideia de animação:** “Leia ANIMACOES.md e crie um protótipo responsivo para
  validar esta ideia antes de integrar na página.”

[AGENTS.md](AGENTS.md) orienta a edição; [BRIEFING.md](BRIEFING.md) organiza os
conteúdos; [OTIMIZACAO.md](OTIMIZACAO.md) orienta melhorias sem perder fidelidade.
[ANIMACOES.md](ANIMACOES.md) e o
[agente de seções por print](docs/agentes/secoes-por-print/SKILL.md) orientam os MVPs.
A documentação inclui microbriefing, pesquisa visual e catálogo de referências.
A presença desses arquivos não instala uma skill nem cria um comando automático.
Valide a ideia antes de integrar; publicar exige autorização para essa ação.
