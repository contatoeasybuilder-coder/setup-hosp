# Agente de prototipos de animacao

## Objetivo
Transformar uma ideia ou referencia visual em uma secao interativa pequena, para o usuario experimentar e aprovar antes da integracao no site.

## Ambiente portavel
- Descubra a raiz do projeto, o sistema operacional, o shell e os comandos realmente disponiveis. Nunca exija uma pasta pessoal, um sistema operacional ou uma branch fixa.
- Leia as instrucoes do projeto e, se existirem, EASY-BUILDER.md e o manifesto da entrega. Preserve alteracoes locais e respeite a estrutura existente.
- Use caminhos relativos nos arquivos entregues. Nao escolha uma branch nem altere o projeto principal implicitamente.

## Microbriefing e referências
Antes de construir, aproveite as respostas da conversa e esclareça apenas o que
falta: o que reaproveitar, qual estética seguir e quais cores/fontes usar se a
identidade estiver inacessível ou ambígua. Para um print ou uma reinvenção visual,
leia `docs/agentes/secoes-por-print/SKILL.md`, a partir da raiz do projeto: ele
contém o microbriefing, a pesquisa de referências e a revisão de direção de arte.
Não imponha outra rodada de perguntas quando as respostas já estiverem claras.

Para ideias sem print, use o mesmo processo de pesquisa quando ajudar o pedido.
Selecione poucas referências pertinentes, confira a origem e distinga o movimento
observado do que está propondo. Não invente sites visitados ou interações testadas.

## Fluxo
1. Leia a referencia e separe o visual observado do movimento proposto. Uma imagem nao comprova como a animacao original funciona.
2. Se o pedido estiver claro, construa uma proposta. Se faltar uma decisao essencial, ofereca ate tres direcoes e pergunte somente o necessario.
3. Crie um prototipo independente em prototipos/<nome>/index.html, ou na pasta de artefatos da ferramenta. Prefira HTML, CSS e JavaScript sem dependencias quando forem suficientes.
4. Preserve os textos fornecidos. Identifique ilustracoes recriadas e conteudo demonstrativo. Nao invente resultados, depoimentos ou alegacoes comerciais.
5. Apresente um preview interativo dentro do chat somente quando a ferramenta suportar isso. Caso contrario, abra no navegador e explique a limitacao; uma imagem estatica nao equivale a preview interativo.
6. Ofereca controles uteis para experimentar o movimento: rolagem nativa, reproduzir/pausar e reiniciar quando aplicaveis. Nao intercepte a rolagem da pagina para impor uma animacao.
7. Teste as interacoes, teclado, tamanhos de desktop e celular, ausencia de overflow horizontal e erros no navegador. Respeite prefers-reduced-motion e mantenha o conteudo acessivel sem JavaScript.
8. Mostre a proposta e registre o que foi realmente validado. Aguarde aprovacao do conceito antes de integrar no site.
9. Na integracao aprovada, reutilize o comportamento validado, respeite a stack existente e preserve o restante da pagina. Publicacao depende da autorizacao do usuario.

## Como pedir
"Leia ANIMACOES.md e crie um MVP da secao Escolha seu planeta a partir desta referencia. Quero testar a entrada ao rolar e a selecao entre dois caminhos antes de integrar no site."

Este arquivo e uma instrucao reutilizavel para uma IA; nao instala uma extensao nem registra um comando automaticamente.
