---
name: secoes-por-print
description: Cria ou reinventa seções de sites a partir de prints, copy e referências visuais. Use quando o cliente enviar uma captura de seção, pedir um novo estilo visual, explorar uma ideia de animação ou validar um MVP antes de integrar ao site. Faz microbriefing antes de construir, pesquisa referências reais na internet e valida responsividade, scroll e acessibilidade.
---

# Seções por print

Transforme uma referência em uma seção com direção visual intencional e um
protótipo que o cliente consiga experimentar antes da integração. Converse em
português, salvo preferência diferente. Um print é evidência do visual capturado;
não comprova animações, comportamento no scroll ou outros tamanhos de tela.

## 1. Entenda a referência e o ambiente

Abra o print com a ferramenta de imagem disponível. Extraia a copy, sua hierarquia
e os elementos visíveis. Sinalize trechos ilegíveis em vez de inventá-los.
Se a imagem estiver inacessível, peça que o cliente a anexe novamente na conversa.

Leia as instruções do projeto e examine as seções existentes, os tokens de cor,
fontes, componentes, recursos e comandos disponíveis. Detecte o sistema operacional
e os caminhos atuais; não imponha ferramentas ou caminhos pessoais. Preserve
alterações locais. Em uma página exportada pelo Easy Builder, leia também suas
instruções e manifesto antes de alterar o contrato de preview ou publicação.

Separe o que você observou do que está propondo. Não deduza a identidade inteira
da marca nem o funcionamento de uma animação a partir de uma captura.

## 2. Faça um microbriefing antes de construir

Use as respostas já dadas na conversa. Pergunte somente o que ainda falta,
preferencialmente em uma rodada curta de até três perguntas. Adapte estas:

1. **O que você quer reaproveitar dessa seção do print?** Só a copy; copy e
   hierarquia; alguns elementos; ou uma reprodução fiel do visual? Se forem
   elementos específicos, quais?
2. **Em qual estética devo me basear?** Nas outras seções do seu site, em uma
   referência nova ou em uma direção que eu proponha? Peça link, print ou caminho
   das seções relevantes quando necessário.
3. **Se não houver identidade acessível ou ela estiver ambígua:** quais cores e
   fontes devo usar? O cliente também pode autorizar você a propor uma paleta e
   uma combinação tipográfica. Se a identidade já estiver clara, use esta pergunta
   para esclarecer uma dúvida real sobre objetivo, interação ou movimento.

Ofereça opções curtas e espaço para resposta livre. Se as fontes do projeto forem
desconhecidas pelo cliente, investigue primeiro; não exija nomes técnicos que você
pode descobrir. Se houver conflito entre a identidade atual e o pedido, explique
o conflito e pergunte qual seguir. Não interprete silêncio como escolha de cores,
fontes ou autorização para descartar a identidade existente.

Enquanto aguarda uma resposta indispensável, pode inspecionar o projeto e buscar
referências; não construa uma direção visual baseada em uma escolha pendente.
Quando as respostas anteriores já resolvem o briefing, apresente sua leitura em
duas ou três frases e avance, sem pedir confirmação novamente.

Registre em `BRIEFING-SECAO.md`, junto do protótipo:

- Objetivo, público e ação principal, quando conhecidos.
- Papel desta seção na página: o que a pessoa deve entender, sentir e decidir;
  relação com as seções anterior e seguinte, quando acessíveis. Investigue antes
  de perguntar e registre como hipótese o que não estiver confirmado.
- Copy e elementos que devem ser preservados; o que pode mudar.
- Direção visual, cores, fontes e de onde vieram essas decisões.
- Movimento desejado, inclusive se deve acompanhar o scroll nativo.
- Dúvidas pendentes e critérios concretos de aprovação.

Se o cliente pedir **só a copy**, crie outra composição: não reutilize por padrão a
estrutura, os desenhos ou a disposição do print. Se pedir fidelidade, preserve os
elementos solicitados. Não transforme todo pedido no mesmo modelo de cards,
gradientes, planetas ou parallax.

## 3. Pesquise referências com intenção

Siga [o processo de pesquisa visual](references/pesquisa-visual.md) e escolha fontes
no [catálogo de referências](references/fontes-visuais.md) conforme o briefing;
não consulte o catálogo inteiro a cada tarefa. Use busca e
navegação reais quando disponíveis. Procure mecanismos úteis para o briefing,
incluindo referências fora do segmento do cliente. Examine os sites de origem;
não trate um resultado de busca ou uma galeria como comprovação de interação.

Apresente uma seleção curta com links, o aspecto aproveitável e a adaptação à
identidade do cliente. A pesquisa deve informar decisões de composição,
tipografia, materiais e movimento, sem substituir o briefing nem copiar um site.
Se não conseguir navegar, declare essa limitação e use apenas referências
realmente acessíveis; não invente páginas visitadas ou comportamentos observados.

Antes de construir uma proposta nova, compare internamente dois conceitos de
composição realmente distintos, seguindo [direção e revisão visual](references/direcao-e-revisao.md).
Escolha pelo papel da seção, identidade, leitura no celular e função do movimento;
registre a escolha e o motivo no briefing. Em reprodução fiel, compare soluções
de adaptação sem redesenhar o que o cliente pediu para preservar.
Se o cliente tiver pedido para escolher entre propostas, apresente até duas
direções. Não construa duas versões completas nem crie uma etapa extra de
aprovação quando ele já autorizou sua escolha.

## 4. Construa um MVP que permita avaliar a ideia

Crie em `prototipos/<nome-da-secao>/` ou no diretório de artefatos permitido pela
sessão. Mantenha a seção do site intacta até o cliente aprovar a integração.
Use a stack existente se ela facilitar a avaliação; HTML, CSS e JavaScript são
suficientes para um protótipo independente quando não houver outra necessidade.
Não adicione um framework ou biblioteca para uma interação simples.

Preserve a copy aprovada e não invente depoimentos, resultados ou promessas.
Identifique ilustrações e dados provisórios. Use recursos existentes com permissão
ou crie elementos próprios; deixe explícito quando uma imagem for apenas exemplo.

Componha desktop e celular deliberadamente: adapte ordem, proporções, tipografia,
espaçamento e controles. Não apenas reduza a tela desktop. Conteúdo essencial
precisa permanecer legível e acessível durante a interação.

Quando houver movimento:

- Complete no briefing: **“Este movimento ajuda o visitante a entender ___.”**
  Relacione a coreografia ao conteúdo: evolução, relação, contraste ou escolha.
  Não imponha scroll animado a toda seção. Se o cliente pedir um efeito de
  atmosfera, explique esse propósito e preserve a leitura; não invente uma
  justificativa narrativa para um movimento apenas decorativo.
- Se o movimento for vinculado ao scroll, derive seu progresso da posição real
  da seção. Use a rolagem nativa, permita reversão e libere o conteúdo ao sair
  da seção; não intercepte a roda do mouse para simular uma página presa.
- Evite esconder o conteúdo até um JavaScript iniciar. Garanta uma apresentação
  legível sem JavaScript e com `prefers-reduced-motion`, removendo também espaços
  longos de pinning que perderem a função sem movimento.
- Prefira `transform` e `opacity` quando adequados; evite leituras e escritas de
  layout repetidas por frame. Pause trabalho fora da tela e limpe listeners.
- No celular, reduza movimento e reorganize a cena se isso melhorar leitura e
  toque. Não sacrifique a copy para manter uma coreografia de desktop.

Use preview interativo no chat somente se a ferramenta disponível suportar isso.
Caso contrário, abra o protótipo no navegador e explique onde ele está. Nunca
apresente imagem, vídeo ou bloco de código como preview interativo executável.
Não prometa um servidor quando o ambiente não o permite.

## 5. Revise a direção visual e valide o resultado real

Faça uma segunda passagem de direção de arte no protótipo renderizado, conforme
[direção e revisão visual](references/direcao-e-revisao.md). Siga o ciclo:
**construir → inspecionar → priorizar até três fragilidades → corrigir → verificar**.
Revise hierarquia, ritmo, proporções, relação texto/imagem, tempo até o primeiro
conteúdo útil e duração do scroll. Corrija as fragilidades relevantes encontradas
antes de entregar. Não invente três defeitos, atribua notas de qualidade ou
apresente somente testes técnicos como evidência de bom design.

Confira a continuidade com as seções vizinhas quando acessíveis. Faça isso em
uma prévia de contexto sem alterar o site antes da aprovação. Se só tiver o print
isolado, declare essa limitação; não afirme que a integração visual foi validada.

Confira no navegador, quando disponível:

- Desktop e celular, incluindo largura estreita de 320 px e um tamanho móvel
  comum, além das transições de layout relevantes. Não pode haver corte de texto
  nem rolagem horizontal acidental.
- Scroll no começo, meio e fim; subida e descida; entrada e saída de sticky;
  redimensionamento e mudança de orientação quando aplicáveis.
- Foco visível, navegação por teclado, botões e links reais, toque e ordem de leitura.
- Movimento reduzido, conteúdo sem JavaScript, recursos ausentes e erros do console.

Registre o que foi conferido e o que falta. Um HTTP 200, uma compilação ou um print
isolado não comprovam responsividade e animação. Quando não houver navegador,
faça as verificações possíveis e declare que a validação visual ficou pendente.
Em `REVISAO-VISUAL.md`, registre os principais problemas observados, o que mudou,
as evidências da nova conferência e os limites restantes. Revalide os estados
afetados pelas correções; encerre quando os critérios do briefing forem atendidos
e os problemas relevantes resolvidos ou explicitamente delimitados.

## 6. Entregue para aprovação e depois integre

Entregue um preview principal, arquivos editáveis, briefing, referências e revisão. Explique
brevemente a ideia visual e o comportamento do scroll. Peça feedback concreto
sobre a direção e a interação; não entregue várias versões técnicas da mesma
página para o cliente escolher qual funciona.

Depois da aprovação, integre respeitando a stack e as demais seções. Preview,
edição e publicação devem preservar o mesmo visual e comportamento; não troque
o resultado aprovado por uma versão estática simplificada. Teste novamente no
contexto real do site. Publicação depende da autorização da sessão.

## Como usar sem instalar uma skill

Em uma conversa com acesso a esta pasta, peça:

> Leia `docs/agentes/secoes-por-print/SKILL.md` e siga esse agente para criar uma
> seção a partir do print anexado. Faça o microbriefing antes de construir e
> pesquise referências para melhorar a proposta.

Este pacote também contém metadados de skill em `agents/openai.yaml`. A presença
dos arquivos na documentação não instala uma skill nem registra um comando.
