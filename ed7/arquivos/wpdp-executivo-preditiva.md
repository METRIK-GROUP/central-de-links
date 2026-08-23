---
name: wpdp-executivo-preditiva
description: Aponta onde o projeto tende a dar problema no executivo e na obra, antes do primeiro traço do detalhamento. Lê o que já existe do projeto (briefing, levantamento, layout, restrições) e devolve as bandeiras por disciplina, cada uma com o que a origina e o que fazer para fechar. Usar quando a pessoa disser "vou começar o executivo", "o que pode dar errado aqui" ou "revisa meu projeto antes da obra".
---

# Análise preditiva do executivo

> **Responda sempre em português do Brasil**, inclusive as perguntas, os títulos e todo o texto do entregável.

## O que esta skill entrega

Um **relatório de pontos de atenção**, gerado antes do detalhamento começar. Ela responde uma pergunta só: *onde este projeto tende a dar problema.*

Não é revisão de prancha pronta. É o contrário: é olhar o que já se sabe do projeto e antecipar o que vai virar dor de cabeça na obra, enquanto ainda é barato resolver.

Sai como página HTML navegável, autossuficiente, que abre no navegador e imprime.

## Por que antes e não depois

Erro encontrado na prancha custa uma revisão. O mesmo erro encontrado na obra custa uma quebra, um retrabalho de fornecedor e uma conversa difícil com o cliente. Esta skill existe para trazer o achado para o lado barato.

## Quando usar

Quando o layout está fechado e o executivo vai começar. Também vale rodar de novo depois de uma mudança grande de escopo.

Não serve para revisar um executivo já desenhado, nem para conferir se a prancha está no padrão do escritório.

## O que ela precisa receber

Pelo menos dois destes:

- briefing preenchido ou transcrição da reunião
- dados do imóvel: áreas, pé-direito, esquadrias, prumadas, idade da construção
- observações da visita técnica
- layout definido ou programa de necessidades por ambiente
- restrições conhecidas: condomínio, estrutura, prazo, verba
- os checklists de executivo que a pessoa já usa, se tiver

**Se faltar material, a skill não inventa.** Ela lista o que falta, explica o que aquilo impede de analisar, e roda com o que tem.

## As disciplinas que ela varre

Esta versão cobre **a fase 1 do executivo**, que é a fase que prepara a obra para começar certo: civil, instalações e acabamentos.

A fase 1 se separa **por disciplina, não por ambiente**. Cada disciplina atravessa a casa inteira, e é assim que a skill varre.

**Levantamento e layout vêm antes.** São pré-requisito da fase 1, não fazem parte dela: entram como material de entrada, já resolvidos, e a análise parte deles.

A fase 2, que resolve marcenaria, louças e metais, mobiliário e arremates, não entra nesta versão.

### As disciplinas da fase 1, na ordem oficial do método

É a ordem em que as pranchas são feitas no escritório, uma dependendo da anterior.

1. **Construir e demolir.** O que sai, o que entra e o que muda de posição no perímetro dos ambientes.
2. **Climatização.** Onde o equipamento fica, por onde o ar e o dreno atravessam e o que isso ocupa do projeto.
3. **Elétrica e dados.** Onde vai precisar de ponto, de comando e de sinal, e o que a instalação existente suporta.
4. **Hidráulico e gás.** Por onde a água e o gás chegam, por onde a água sai e o quanto os pontos novos dependem do que já existe.
5. **Paginação de revestimentos.** Como o revestimento começa, encontra e termina em cada superfície.
6. **Forro.** O que precisa caber acima dele e como ele conversa com esquadria, cortina e equipamento.
7. **Luminotécnico.** Onde a luz nasce, o que ela ilumina e como cada ambiente é acionado.
8. **Som e imagem.** Onde o equipamento fica, o que ele exige de infraestrutura e o que ele pede da superfície que o recebe.
9. **Pintura e texturas.** Onde cada tratamento de superfície começa e termina, e o que ele exige de base pronta.

### Disciplinas transversais

Não são pranchas próprias: são varridas junto com as demais, em qualquer modo de execução.

10. **Circulação e uso.** Como as pessoas atravessam, alcançam e usam os ambientes, incluindo os perfis de morador que o briefing indicar.
11. **Prazo e sequência.** O que precisa ser decidido antes do quê, e onde o prazo de fornecedor conflita com o prazo de obra.

## Como cada bandeira é escrita

Toda bandeira carrega quatro campos obrigatórios. Sem os quatro, ela não entra no relatório:

> **O que é.** A descrição objetiva do ponto de atenção.
> **De onde veio.** A fala, a medida ou a restrição que originou o achado, citada.
> **O que acontece se ninguém olhar.** A consequência concreta na obra, não um aviso genérico.
> **Como fechar.** O que precisa constar no executivo para resolver.

Cada bandeira recebe também um nível: **crítico** (para a obra se não resolver), **importante** (gera retrabalho ou custo extra) ou **atenção** (vale confirmar).

## A regra que separa isto de um checklist genérico

Toda bandeira precisa nascer de algo que está **neste projeto**. A skill nunca despeja uma lista de boas práticas que serviria para qualquer obra.

Se ela não tem material suficiente para levantar uma bandeira numa disciplina, ela diz isso, com o nome da disciplina e o que precisaria receber para analisar. Silêncio honesto vale mais que lista genérica.

Ela também nunca ensina o fornecedor a executar. A bandeira diz **o que precisa constar no executivo** (ponto, medida, compatibilização, especificação), nunca **como** o eletricista ou o marceneiro deve fazer o trabalho dele.

## O que ela produz, seção por seção

**1. O projeto em uma tela.** Ambiente, área, quem usa, o que foi pedido. Para quem abrir o relatório entender do que se trata em vinte segundos.

**2. O placar.** Quantas bandeiras por nível e por disciplina, para saber onde está concentrado o risco.

**3. As bandeiras críticas.** Primeiro as que param a obra, cada uma com os quatro campos.

**4. As demais, por disciplina.** Importantes e de atenção, agrupadas na ordem das disciplinas e, por fim, nas transversais.

**5. A ordem de decisão.** O que precisa ser decidido antes do quê, considerando prazo de fornecedor. É a seção que evita o executivo travar esperando uma escolha.

**6. O que eu não consegui analisar.** As disciplinas sem material suficiente, com o que falta em cada uma.

**7. O que eu assumi.** Toda inferência listada, para confirmar ou derrubar.

## Como a skill se comporta

Antes de gerar, faz **uma pergunta por vez**, numerada, com opções rotuladas por letra e sempre a alternativa "outra, eu explico", para permitir resposta por voz. No máximo cinco perguntas, e só sobre o que muda o resultado.

### A primeira pergunta é sempre esta

Antes de qualquer análise, ela pergunta **onde estão os checklists de projeto executivo do escritório**. Não é uma pergunta opcional nem uma formalidade: é o checklist que direciona a varredura inteira.

> **(a)** estão nesta pasta, e o caminho é este
> **(b)** eu tenho, mas não sei onde estão agora
> **(c)** eu ainda não tenho um checklist de executivo
> **(d)** outra, eu explico

Junto com o checklist ela aceita, e pede, o resto do material de apoio que existir: o padrão de executivo do escritório, os detalhamentos de referência e os workbooks de cada disciplina.

**Por que isso importa tanto.** Com o checklist na mão, a skill confere o projeto contra o critério de quem vai executar, e cada bandeira nasce do jeito que aquele escritório entrega. Sem ele, ela só consegue comparar contra o que é comum ao mercado, e o resultado é uma lista que serviria para qualquer obra, ou seja, previsível e pouco útil.

**Se a resposta for (c), ela roda assim mesmo, mas não finge que dá no mesmo.** Entrega a varredura geral, e abre o relatório com um aviso claro: esta análise está genérica porque não recebeu o checklist de executivo do escritório, e o que ela deixou de conferir por causa disso. No fim, lista as perguntas que o checklist responderia, para servir de ponto de partida a quem quiser montar o seu.

Ela nunca trata a ausência de checklist como detalhe, e nunca inventa um critério para preencher o vazio.

## Idioma

Tudo em **português do Brasil**, sempre, mesmo que a conversa tenha começado em outra língua e mesmo que o material recebido esteja em inglês.

Isso vale para a resposta no chat, para as perguntas que ela faz, para os títulos e rótulos da página HTML, para os nomes dos arquivos gerados e para qualquer texto dentro do entregável. Nada de "Overview", "Summary", "Next steps" ou nome de seção em inglês.

Termo técnico que já se usa em inglês no dia a dia do escritório (briefing, layout, moodboard, checklist, workbook) pode ficar como está. O resto é português, com acentuação completa e correta.

## Identidade visual do entregável

- Fundo `#F5F4F0`, caixas brancas, cantos de 8px, sombra suave
- Texto `#1E1E1E`, apoio `#5F5E5A`, linhas `#DCDAD0`
- Cor de destaque verde petróleo `#028980` em título de seção e numeração
- Os níveis de bandeira usam apenas peso e um marcador discreto, não semáforo colorido: crítico em texto forte com barra lateral, importante com barra mais leve, atenção sem barra
- Tipografia sem serifa, título pesado, corpo leve, muito espaço em branco
- Navegação fixa no topo, responsivo, sem depender de nada além do Google Fonts
- Nada de fundo escuro, gradiente colorido ou ícone decorativo

## O que esta skill nunca faz

- Inventar medida, restrição ou fala que não esteja no material
- Entregar lista genérica de boas práticas disfarçada de análise
- Apontar bandeira sem dizer de onde ela veio
- Ensinar o fornecedor a executar
- Prometer que o projeto está livre de problema: ela reduz risco, não elimina

## Nota

Esta é a versão do Workshop Projeto de Primeira com IA. Ela roda com o que estiver na mão e cobre as nove disciplinas da fase 1 mais as transversais.

A versão completa, que avança também sobre a fase 2, cruza cada achado contra a Biblioteca Técnica do escritório e contra os checklists próprios da pessoa, emenda na revisão do executivo desenhado e vira plano de ação priorizado com aceite item a item, faz parte do programa de Implementação.
