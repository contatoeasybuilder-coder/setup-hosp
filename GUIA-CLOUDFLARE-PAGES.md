# Do zero ao Cloudflare Pages

Este guia usa **GitHub + Cloudflare Pages**. Você terá um endereço gratuito `nome-do-projeto.pages.dev`; domínio próprio é opcional. Os nomes dos botões abaixo são os exibidos em inglês e podem aparecer traduzidos na sua conta.

## 1. Entrar nas contas

1. Acesse [dash.cloudflare.com](https://dash.cloudflare.com/) e entre. Se ainda não tiver conta, escolha **Sign up**, informe e-mail e senha, crie a conta e confirme o e-mail recebido.
2. Acesse [github.com](https://github.com/) e entre. Se ainda não tiver conta, escolha **Sign up**, conclua o cadastro e confirme o e-mail. É no GitHub que os arquivos do site ficarão online.

## 2. Clonar o setup e criar seu próprio repositório

3. Instale o [Git](https://git-scm.com/downloads), caso ainda não esteja instalado. Abra o Terminal (macOS) ou Git Bash (Windows) e execute:

   ```bash
   git clone https://github.com/contatoeasybuilder-coder/setup-hosp.git
   cd setup-hosp
   ```

4. No GitHub, abra [github.com/new](https://github.com/new). Escolha sua conta em **Owner**, dê um nome ao seu repositório (por exemplo, `minhas-paginas`) e escolha **Public** ou **Private**. Deixe desmarcadas as opções de criar README, `.gitignore` e licença. Clique em **Create repository** e copie a URL HTTPS que aparecer, por exemplo `https://github.com/SEU-USUARIO/minhas-paginas.git`.
5. No mesmo Terminal, ainda dentro da pasta `setup-hosp`, troque o endereço remoto pelo endereço **do seu repositório** e envie a branch `main`:

   ```bash
   git remote remove origin
   git remote add origin https://github.com/SEU-USUARIO/minhas-paginas.git
   git push -u origin main
   ```

   Substitua `SEU-USUARIO/minhas-paginas` pelo endereço copiado no passo 4. Se o Git pedir autenticação, entre na sua conta GitHub pelo fluxo exibido. Assim, seus próximos envios irão para o seu repositório.
6. Abra seu novo repositório no navegador. Confirme que `build.sh`, `index.html`, `README.md` e `GUIA-CLOUDFLARE-PAGES.md` aparecem na raiz e que a branch exibida é `main`.

## 3. Conectar o GitHub ao Cloudflare Pages

7. Volte ao [painel da Cloudflare](https://dash.cloudflare.com/), escolha sua conta e abra **Workers & Pages → Create application → Pages → Connect to Git**. Em algumas telas, o último botão aparece como **Import an existing Git repository**.
8. Escolha **GitHub**. Faça login quando solicitado e autorize a instalação do app da Cloudflare. Se aparecer a escolha de acesso aos repositórios, selecione **Only select repositories**, marque **seu repositório criado no passo 4** e confirme **Install & Authorize**.
9. Selecione esse repositório na lista da Cloudflare e clique em **Begin setup**. Caso não apareça, volte à autorização do app no GitHub e conceda acesso a ele.
10. Preencha **Set up builds and deployments** assim:

   | Campo | Valor |
   | --- | --- |
   | Project name | Um nome único para o endereço `nome.pages.dev` |
   | Production branch | A branch anotada no passo 6 (`main`, se for esse o nome) |
   | Framework preset | **None** / sem framework |
   | Build command | `bash build.sh` |
   | Build output directory | `_site` |
   | Root directory (advanced) | **Deixe vazio**: os arquivos estão na raiz do repositório |
   | Environment variables | Nenhuma |

11. Clique em **Save and Deploy**. Espere o status do primeiro deploy ficar **Success** em **Deployments**. Abra o endereço `nome.pages.dev` mostrado no projeto: a página inicial deste setup deve aparecer. O endereço funciona sem comprar domínio.

## 4. Publicar cada página como slug

12. Crie, dentro do repositório, uma pasta com o slug e um `index.html` dentro dela. Exemplo: `curso-de-fotografia/index.html`. Coloque os arquivos dessa página em `curso-de-fotografia/assets/` e use no HTML caminhos como `assets/foto.webp`.
13. Salve a nova pasta na cópia local `setup-hosp` e, no Terminal aberto nela, execute `git add .`, `git commit -m "Adiciona pagina"` e `git push`. Confira no seu repositório GitHub que o caminho aparece como `curso-de-fotografia/index.html`, sem pasta extra antes do slug.
14. A Cloudflare inicia um novo deploy automaticamente. Quando ele ficar **Success**, abra `https://nome.pages.dev/curso-de-fotografia/`. O nome de cada pasta de primeiro nível será o slug da respectiva página.

**Ao atualizar uma página:** altere os arquivos da pasta daquele slug na cópia local e repita `git add .`, `git commit -m "Atualiza pagina"` e `git push`; acompanhe o deploy em **Workers & Pages → seu projeto → Deployments**. Se o HTML novo não aparecer, confira se o último deploy terminou com **Success** e se o arquivo está na branch de produção.

**Limites:** o plano Free do Cloudflare Pages aceita até **20.000 arquivos publicados e 25 MiB por arquivo**; um arquivo maior precisa ser reduzido ou hospedado fora do Pages.

**Domínio próprio (opcional):** no projeto Pages, abra **Custom domains → Set up a domain**, informe o domínio e siga as instruções de DNS exibidas. O endereço `pages.dev` já serve para publicar sem essa etapa.

Fontes oficiais: [criar conta Cloudflare](https://developers.cloudflare.com/fundamentals/account/create-account/), [criar conta GitHub](https://docs.github.com/en/account-and-profile/how-tos/account-management/creating-an-account-on-github), [clonar repositório](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository), [integração Git no Pages](https://developers.cloudflare.com/pages/get-started/git-integration/), [rotas e `index.html` no Pages](https://developers.cloudflare.com/pages/configuration/serving-pages/), [limites do Pages](https://developers.cloudflare.com/pages/platform/limits/) e [domínio próprio](https://developers.cloudflare.com/pages/configuration/custom-domains/). Conferido em 8 de outubro de 2026.
