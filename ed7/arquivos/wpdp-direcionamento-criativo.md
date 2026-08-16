---
name: wpdp-direcionamento-criativo
description: Transforma a conversa com o cliente em direção de projeto defensável. Lê a transcrição da reunião, o checklist e o questionário, e devolve uma página com o que o cliente disse na íntegra, o que aquilo significa em decisão de projeto, as contradições que ninguém percebeu e o partido proposto com justificativa. Usar quando a pessoa disser "já fiz o briefing e não sei por onde começar", "traduz isso em projeto" ou "monta o direcionamento".
---

# Direcionamento criativo, a partir do que o cliente disse

> **Responda sempre em português do Brasil**, inclusive as perguntas, os títulos e todo o texto do entregável.

## O que esta skill entrega

Uma página HTML navegável chamada **Direcionamento Criativo**, que responde uma pergunta só: *o que este cliente disse, e o que isso obriga o projeto a ser.*

Ela não é um resumo do briefing. O resumo joga fora justamente o que interessa, que é a palavra do cliente. Aqui a fala é preservada e ao lado dela aparece a tradução em decisão de projeto, para o profissional conseguir defender cada escolha na hora da apresentação.

O entregável é único, autossuficiente, abre no navegador e imprime.

## Quando usar

Depois da reunião de briefing, com a transcrição na mão, e antes de desenhar a primeira linha. Serve tanto para reforma quanto para obra nova, residencial ou comercial.

Não serve para gerar o briefing (isso é a reunião com o cliente, não é trabalho de IA) nem para desenhar layout.

## O que ela precisa receber

Pelo menos um destes, e quanto mais melhor:

- a transcrição da reunião de briefing, mesmo bagunçada
- o checklist de briefing preenchido
- o questionário que o cliente respondeu antes
- anotações soltas, áudios transcritos, mensagens de WhatsApp
- dados do imóvel e restrições conhecidas

**Se faltar material, a skill não inventa.** Ela diz o que falta e segue com o que tem, marcando os buracos.

## A regra central: nunca perder a palavra do cliente

Toda decisão de projeto proposta precisa estar ancorada em algo que o cliente **de fato disse**. A skill trabalha sempre em par:

> **O que ele disse** (verbatim, entre aspas, sem reescrever)
> **O que isso significa para o projeto** (a tradução, que é trabalho do profissional)

Quando a decisão não vem de uma fala, e sim de uma restrição técnica ou de repertório do profissional, ela entra marcada como **decisão técnica** ou **repertório**, nunca como pedido do cliente. Confundir as três coisas é o que faz o cliente sentir que o projeto não é dele.

A skill nunca atribui ao cliente um desejo que ele não verbalizou.

## O que ela produz, seção por seção

**1. Nas palavras deles.** As frases mais reveladoras da reunião, verbatim, cada uma com uma etiqueta do que ela ancora (cozinha, rotina, veto, prazo, verba, medo). Sem correção de português, sem reescrita. É a seção que o cliente lê e sente que foi ouvido.

**2. Quem são e como vivem.** Composição da família, rotina real durante a semana e no fim de semana, quem recebe, quem trabalha em casa, animais, quem decide o quê. Tudo extraído do material, nada suposto.

**3. As contradições.** A parte mais valiosa e a que ninguém faz. A skill cruza tudo o que foi pedido e aponta onde os pedidos brigam entre si, onde o pedido briga com o imóvel, e onde o pedido briga com o prazo ou com a verba. Cada contradição vem com as duas falas que a originam e uma pergunta objetiva para resolver na próxima conversa.

**4. O partido proposto.** Três a cinco decisões de projeto, cada uma escrita como afirmação e cada uma com a justificativa ancorada. Não é conceito poético, é decisão: o que vai acontecer no espaço e por quê.

**5. A materialidade de partida.** Direção de materiais e atmosfera, em texto, coerente com o que foi dito e com o orçamento sinalizado. Sem imagem: imagem entra depois, com o cliente junto.

**6. O que perguntar antes de desenhar.** A lista de pendências reais, cada uma com a pergunta pronta para mandar por mensagem. Ordenada por quanto ela trava o projeto.

**7. O que eu assumi.** Toda inferência que a skill precisou fazer aparece aqui, listada, para o profissional confirmar ou derrubar. Nada de premissa escondida no meio do texto.

## Como a skill se comporta

Antes de gerar, ela faz **uma pergunta por vez**, numerada, com as opções rotuladas por letra e sempre uma alternativa "outra, eu explico". Isso permite responder por voz, falando só o número e a letra. Ela pergunta no máximo cinco vezes e só sobre o que realmente muda o resultado.

Se o material for suficiente, ela não pergunta nada e já entrega.

## Idioma

Tudo em **português do Brasil**, sempre, mesmo que a conversa tenha começado em outra língua e mesmo que o material recebido esteja em inglês.

Isso vale para a resposta no chat, para as perguntas que ela faz, para os títulos e rótulos da página HTML, para os nomes dos arquivos gerados e para qualquer texto dentro do entregável. Nada de "Overview", "Summary", "Next steps" ou nome de seção em inglês.

Termo técnico que já se usa em inglês no dia a dia do escritório (briefing, layout, moodboard, checklist, workbook) pode ficar como está. O resto é português, com acentuação completa e correta.

## Identidade visual do entregável

- Fundo `#F5F4F0`, caixas brancas, cantos de 8px, sombra suave
- Texto `#1E1E1E`, apoio `#5F5E5A`, linhas `#DCDAD0`
- Uma única cor de destaque, verde petróleo `#028980`, usada só em título de seção, etiqueta e numeração
- Tipografia sem serifa, título pesado, corpo leve, muito espaço em branco
- As falas do cliente em bloco destacado, com a citação em corpo maior
- Navegação fixa no topo com link para cada seção
- Responsivo, funciona no celular, sem depender de nada além do Google Fonts
- Nada de fundo escuro, gradiente colorido ou ícone decorativo

Se a pessoa pedir a identidade do escritório dela, troque apenas cores e tipografia e mantenha a estrutura.

## O que esta skill nunca faz

- Inventar fala, desejo, medida ou restrição que não esteja no material
- Reescrever a fala do cliente para ficar mais bonita
- Entregar conceito genérico que serviria para qualquer projeto
- Propor solução que o imóvel ou a verba não comportam sem sinalizar o conflito
- Sugerir imagem gerada por IA como referência de projeto
- Esconder premissa: tudo o que foi assumido aparece na seção 7

## Nota

Esta é a versão do Workshop Projeto de Primeira com IA. Ela para no direcionamento escrito e defensável.

A versão completa, que pesquisa tendência e comportamento em fontes externas, monta o moodboard por ambiente com curadoria de imagem e harmonização de paleta, e emenda direto na etapa de layout, faz parte do programa de Implementação.
