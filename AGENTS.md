# Edição de páginas clonadas

## Objetivo
Transformar páginas e seções clonadas em uma página coerente com a
copy e a marca do cliente, preservando os layouts e as interações
escolhidos. Priorize alterações necessárias; não reconstrua a página
nem troque tecnologias sem motivo relacionado ao pedido.

## Aplicação
Aplique as regras pertinentes ao pedido atual. Não transforme um
ajuste pontual em uma revisão completa. Preserve decisões já aprovadas.
Se faltar uma decisão indispensável, pergunte; resolva detalhes técnicos
autonomamente dentro do escopo autorizado.

## Ambiente e autonomia
- Estas instruções acompanham a página do cliente; não são as regras do repositório
  do Easy Builder. Não exigem AIOS/AIOX, Infisical, conta Railway ou banco do produto.
- Detecte a raiz da entrega, sistema operacional, shell e ferramentas disponíveis.
  Não fixe caminhos pessoais, letras de unidade, usuário, branch ou gerenciador.
  Funciona em Windows, macOS e Linux; adapte apenas os comandos necessários.
- Se houver Git, preserve a branch e alterações existentes, seguindo a escolha
  da sessão. Não crie repositório, branch ou worktree só para abrir uma página.
- Execute o trabalho já solicitado sem pedir novamente a mesma autorização.
  Esclareça somente decisão indispensável ou conflito real. Publicar, enviar dados
  ou sobrescrever trabalho exige autorização para essa ação; reutilize a já dada.

## Como abrir e executar a página
Antes de editar ou concluir que a entrega está quebrada, identifique seu formato.
Um pedido para abrir a página não autoriza conversão, reconstrução ou otimização.

### Identifique a raiz e o contrato de execução
- Se recebeu ZIP, extraia sem sobrescrever trabalho existente. Localize a pasta
  da entrega, que pode estar dentro de outra pasta; não presuma que é a pasta atual.
- Consulte README, LEIA-ME.html, EASY-BUILDER.md da página, manifestos e instruções de execução
  quando existirem. Em projetos com fonte, leia scripts de `package.json`, campo
  `packageManager` e lockfile; não trate qualquer package.json vizinho como o da página.
- Dê precedência ao contrato da entrega: arquivos de React/Next capturados não
  transformam uma exportação HTML em um projeto Next.js editável. Não crie
  package.json, instale um framework ou execute npm run dev por suposição.

| Formato identificado | Como executar |
| --- | --- |
| Easy Builder isolado: manifesto eb-isolated.json indica isolamento/requiresHttp | Use o VISUALIZAR da raiz do setup, quando presente, ou o preview especializado da CLI compatível com a entrega. O manifesto identifica as pastas; não aponte o servidor para um componente. As origens HTTP isoladas fazem parte da execução. |
| Easy Builder sem isolamento | Consulte a pasta de fonte indicada no manifesto. Prefira VISUALIZAR ou o preview da CLI quando disponíveis. Servidor estático só é alternativa se o contrato não exigir endpoints/runtime especiais; preserve a raiz e os caminhos dos assets. |
| HTML estático independente ou build estático já pronto | Sirva por HTTP a raiz pública correta, preservando subpastas. Não instale dependências de desenvolvimento só para abrir uma saída pronta. |
| Fonte de Next.js, Vite, React ou outro projeto com scripts | Use o gerenciador/versão declarados e o script realmente existente, como `dev`. Instale dependências somente quando necessário, preservando lockfile; não use `npm init` nem atualize pacotes para abrir a página. |
| Preview de produção de um projeto com build | Siga os scripts documentados: por exemplo, build e depois start/preview, somente se existirem. Não confunda servidor de desenvolvimento com validação do pacote publicado. |
| Backend, CMS, monorepo ou formato desconhecido | Localize a aplicação, runtime, serviços e instruções próprios. Não sirva código de backend como HTML. Informe o requisito ausente ou esclareça a ambiguidade; não invente comandos nem recrie serviços externos. |

### Quando o usuário pedir um download pelo CLI
- Reconheça comandos como eb-registry add, compose e códigos curtos com npx.
  Quando o pedido autorizar executar/baixar e o destino estiver definido, prossiga.
  Um comando enviado só para análise não autoriza sua execução.
- Confira o destino e a opção --dir antes de gravar. Se o destino estiver indefinido
  ou ambíguo, esclareça onde salvar. Não escolha a raiz geral por suposição.
- Se já houver uma entrega, use as opções do CLI de criar projeto separado ou
  adicionar página/seção ao setup existente, conforme a escolha do usuário.
  Preserve as rotas anteriores e use outra pasta/rota livre para a nova página.
  Não use --force, apague arquivos ou substitua trabalho sem autorização específica.
- Preserve seleção, códigos, ordem, seções, versão e opções do comando autorizado.
  Não repita tickets/tokens em respostas, documentação ou relatórios. Se o acesso
  expirar, peça um comando renovado, sem solicitar senha.
- Após baixar, identifique e abra a entrega. Download não autoriza adaptar,
  otimizar ou publicar. Um pedido de preview não autoriza novo download.

### Use os iniciadores entregues
Na raiz do setup, prefira o arquivo existente para o sistema do usuário:

| Sistema | Abertura local |
| --- | --- |
| Windows | Dois cliques em VISUALIZAR.bat; no PowerShell, use .\VISUALIZAR.bat. |
| macOS | Abra VISUALIZAR.command; se necessário, use sh ./VISUALIZAR.command no Terminal. |
| Linux | Execute sh ./visualizar.sh no terminal. |

Esses nomes se aplicam quando os arquivos estiverem presentes. Consulte LEIA-ME.html
para requisitos e instruções da versão entregue. Não reinstale dependências nem
atualize pacotes só para reabrir uma entrega que já funciona.

Se a entrega orientar usar a CLI e Node/npm estiverem disponíveis, execute na raiz:

```text
npx --yes eb-registry preview --dir .
```

Use a versão indicada pela entrega se houver uma exigência específica. Não fixe
uma versão antiga por copiar um exemplo. O npx obtém a CLI e suas dependências;
Node/npm precisam estar disponíveis antes de executá-lo. Informe um requisito
ou erro real, sem trocar o contrato de execução para esconder o problema.

Um servidor HTTP genérico só serve para HTML independente cujo contrato permita.
Live Server, Python e file:// não substituem o servidor de uma entrega isolada.
Não ofereça offline.html ou editable.html como versões adicionais ao cliente.
Em entregas antigas que ainda contenham esses arquivos, não troque para eles
silenciosamente nem os apague sem conferir suas referências. Preserve a versão
fiel como fluxo de edição, prévia e publicação. Não concatene scripts nem reconstrua
index.html a partir de seções para contornar erros.

### Abra a URL correta e confirme o conteúdo
- Mantenha o processo ativo e abra a URL HTTP exata informada no terminal;
  não invente porta nem substitua host, pois o isolamento pode validar a origem.
  Preserve a subpasta quando fizer parte do contrato. Não encerre o servidor
  antes de o usuário usar a página; informe comando, pasta, URL e processo ativo.
- Se houver servidor existente, confirme que corresponde à mesma entrega e ao
  modo correto. Não mate processos alheios para liberar porta; escolha outra
  quando suportado ou informe o conflito. Não exponha o preview publicamente.
- Confirme no navegador conteúdo real, seções, assets e uma interação pertinente.
  HTTP 200, título, wrapper de preview ou texto "assets disponíveis" não comprovam
  que a página carregou. Se não puder observar o navegador, declare essa limitação.
- "Servidor de isolamento indisponível" ou "Failed to fetch. Use eb-registry
  preview" exige conferir primeiro servidor, raiz, versão, processo e requisição
  que falhou. Não declare sucesso, desative segurança/CORS ou altere os arquivos
  para esconder o aviso. Se persistir com o servidor correto, registre o erro real.
- Ao pedir apenas abertura, não execute novamente add/compose, não sobrescreva a
  exportação e não altere a página. Dependências externas ou funções de backend
  ausentes devem ser informadas separadamente, não simuladas como funcionais.

## Edição, prévia e publicação da mesma página
- Consulte o manifesto e EASY-BUILDER.md para localizar os documentos editáveis
  de cada rota. Não presuma src/editable.html nem modifique somente um arquivo
  gerado que será sobrescrito. Preserve documentos isolados, CSS, scripts e assets.
- Alterações de texto/layout não autorizam remover hidratação, efeitos ou animações.
  Compare carregamento, scroll e interações após editar; uma primeira tela estática
  não comprova que uma página importada foi preservada.
- Use o procedimento de publicação da própria entrega. Quando presentes, PUBLICAR
  publica e PREPARAR-PUBLICACAO apenas prepara; confira suas instruções e destinos.
  Entregas isoladas podem precisar de várias origens: enviar apenas _site ao
  Cloudflare Pages não substitui esse processo. Não mude o formato por conveniência.
- A publicação deve manter a página editada e os comportamentos vistos na prévia.
  Se não puder validar esse contrato, informe a pendência; não entregue uma
  alternativa simplificada como se fosse equivalente. Publicar exige autorização.

## Criação de seções e protótipos
- Para uma seção nova ou reinventada a partir de print, leia
  `docs/agentes/secoes-por-print/SKILL.md`. Faça o microbriefing sobre o que
  reaproveitar, a estética e a identidade visual somente quando faltar decisão.
- Pesquise referências com o processo e catálogo que acompanham essa skill.
  Não trate uma captura como prova de movimento; diferencie observado e proposto.
- Para experimentar animações antes de integrar, leia `ANIMACOES.md`.
  Crie o MVP separado, valide desktop/celular, scroll nativo, teclado e movimento
  reduzido. Preserve a copy aprovada e registre as limitações reais.
- Use a identidade e as respostas já aprovadas. Uma correção pontual não exige
  microbriefing nem pesquisa completa. Aprovação visual não autoriza publicação.

## Protótipos de animação
- Quando o usuário pedir um MVP, consulte ANIMACOES.md se estiver presente.
  Crie o exemplo separado da página e valide a ideia antes de integrar.
- Use prévia interativa no chat quando a ferramenta suportar; caso contrário,
  explique a limitação e disponibilize o protótipo local. Não prometa recursos ausentes.
- Preserve navegação por teclado, conteúdo acessível e movimento reduzido.
  Aprovar o protótipo não equivale a autorizar deploy.

## Regras

1. Entenda a fonte antes de editar.
   Identifique o arquivo servido, a fonte editável, os arquivos gerados
   e os scripts que controlam o conteúdo. Edite na origem correta para
   que regeneração ou hidratação não desfaçam a alteração. Identifique
   seções por referência estável e contexto; posição ou classe
   compartilhada, sozinhas, não identificam o alvo com segurança.

2. Respeite a sequência quando adaptar uma página completa.
   Seleção/ordem → remoção → copy → identidade visual →
   interações/responsividade → otimização.
   Isso evita retrabalhar conteúdo descartado. Em ajustes pontuais,
   execute somente as etapas afetadas.

3. Ao excluir, remova de verdade.
   Retire a seção da estrutura entregue e atualize suas referências;
   impeça que scripts a recriem. Ocultação ou remoção após carregar
   não substituem exclusão. Menus, abas e slides podem permanecer
   ocultos quando isso fizer parte de seu funcionamento.

4. Ao alterar estrutura ou dependências, preserve interações.
   Não desative scripts, estilos ou animações globalmente para corrigir
   um defeito local. Adapte as dependências afetadas para não perder
   carrosséis, hover, vídeos, menus e outros comportamentos escolhidos.
   Limite estilos e scripts locais à seção pretendida. Reserve regras
   globais para decisões de identidade visual e confira seu impacto
   nas demais seções e páginas.

5. Ao aplicar copy, adapte o layout ao conteúdo.
   Preserve textos, preços e sentido. Ajuste distribuição e dimensões;
   não apague, resuma ou reescreva conteúdo para fazê-lo caber sem
   autorização editorial.

6. Ao padronizar fontes, diferencie funções.
   Hero, título de seção, card, descrição, legenda, preço e botão
   precisam de hierarquia própria. Não aplique um tamanho universal
   nem reduza fontes excessivamente para disfarçar problemas de layout.

7. Ao aplicar a marca, use um padrão central.
   Defina fonte, paleta, fundos, destaques, botões, larguras e
   espaçamentos. Preserve exceções intencionais e cores de fotos,
   logos e demonstrações; consistência não significa uniformizar tudo.

8. Ao mudar cores ou fundos, confira o conjunto.
   Verifique contraste de textos, ícones, links e estados dos botões.
   Não considere a troca concluída se algum conteúdo ficar ilegível.

9. Ao ajustar animações, separe entrada de interação.
   Unifique entradas quando solicitado, sem cancelar movimentos
   funcionais. Respeite movimento reduzido e mantenha conteúdo
   acessível se a animação falhar.
   Recursos lentos ou indisponíveis não devem bloquear toda a página;
   ofereça fallback e erro explícito, sem simular sucesso de ações.

10. Ao combinar seções, harmonize navegação e controles.
    Remova cabeçalhos/camadas duplicados e conflitos de scroll.
    Padronize cursores preservando sinais de clique, edição e arraste.
    Evite que comportamentos herdados disputem o controle da página.
    Confira também emendas, alturas e estilos dentro de documentos isolados.
    Ao integrar templates, consulte a seção de integração de OTIMIZACAO.md;
    preserve um mapa mínimo das fontes e dependências de cada seção.

11. Ao adaptar telas, corrija o layout.
    Ajuste colunas, larguras, quebras e espaçamentos por viewport.
    Não esconda seções nem corte conteúdo para mascarar overflow.

12. Após alterações, valide conforme o impacto.
    Ajuste pontual: confira a região afetada.
    Mudança global: confira as seções afetadas em desktop e celular.
    Interação: execute o comportamento real.
    Entrega final: percorra a página inteira.
    Screenshot não comprova funcionamento; verificações dispensadas
    devem ser registradas como pendentes.

13. Ao otimizar, comprove que o funcionamento foi preservado.
    Consulte OTIMIZACAO.md quando executar uma etapa de otimização;
    registre o resultado na pasta da página.
    Com URL pública autorizada, use PageSpeed Insights e SpeedVitals conforme
    o roteiro; salve e entregue os relatórios ao agente para priorizar ações.
    Não publique só para testar nem aplique recomendações sem avaliar impacto.
    Em composições de vários templates, após o diagnóstico priorize limpeza
    do pacote publicado, CSS acumulado, HTML e inicializações desnecessárias
    antes de recomprimir mídias; preserve o isolamento e as interações.
    Remova apenas recursos comprovadamente desnecessários, considerando
    carregamento tardio e interações. Compare antes/depois; ausência
    na primeira tela não significa ausência de uso.

14. Ao finalizar a identidade, complete os dados da página.
    Solicite favicon, título, descrição e destinos dos CTAs quando
    faltarem. Reutilize decisões aprovadas; não invente essas escolhas.

15. Antes de mudanças amplas, mantenha recuperação.
    Preserve um ponto recuperável. Corrija a causa dos problemas em vez
    de acumular sobrescritas contraditórias. Não reverta trabalho alheio
    ou alterações fora do escopo.

16. Ao entregar, diferencie alteração de comprovação.
    Informe o que mudou, o que foi validado e o que permanece pendente.
    Não declare funcionamento ou fidelidade apenas porque o código
    foi escrito, compilou ou a página abriu.
    Use os critérios de conclusão de OTIMIZACAO.md; registre pendências
    e encerre ao cumprir o escopo, sem ciclos de melhorias marginais.

17. Ao substituir elementos, preserve suas ações.
    Mantenha destinos, âncoras, ações de formulários, rótulos acessíveis
    e operação por teclado, salvo mudança solicitada. Aparência correta
    não garante que botões, links e formulários continuem funcionando.
    Antes de enviar dados, confirme finalidade e destino das integrações;
    remova/desative envios herdados não aprovados e registre a pendência.
    Valide com dados fictícios, sem efeitos reais não autorizados.

18. Antes de entregar, confira o caminho real de publicação.
    Teste recursos e navegação na subpasta final quando aplicável,
    não somente na raiz local. Não entregue referências a localhost,
    caminhos do computador ou arquivos fora do projeto. Essa validação
    não autoriza publicação.

19. Ao acrescentar dependências, exija benefício concreto.
    Reutilize recursos existentes quando adequados. Evite bibliotecas,
    fontes e serviços externos para efeitos simples; não remova
    dependências necessárias apenas para reduzir tamanho.

20. Registre o briefing na pasta da página.
    Use BRIEFING.md como modelo. Na criação/adaptação completa, cubra
    todas as perguntas aplicáveis, aproveitando respostas existentes;
    em ajustes pontuais, trate somente o que mudou. Assim que houver
    respostas e a pasta da página estiver identificada, crie ou atualize
    <pasta-da-pagina>/BRIEFING-PREENCHIDO.md, nunca na raiz geral.
    Salve cada pergunta junto da resposta do cliente, sem inventar
    respostas ou aprovações; separe sugestões e pendências. Atualize
    após cada rodada e consulte o arquivo ao retomar o trabalho.
    Se a pasta for ambígua, esclareça antes de gravar; não sobrescreva
    o briefing de outra página. Mídias e interações serão tratadas
    conforme os pedidos posteriores, sem questionário inicial próprio.
