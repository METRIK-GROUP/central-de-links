---
name: wpdp-executivo-preditiva
description: Aponta onde o projeto tende a dar problema no executivo e na obra, antes do primeiro traço do detalhamento. Lê o que já existe do projeto (briefing, levantamento, layout, restrições) e devolve as bandeiras por disciplina, cada uma com o que a origina e o que fazer para fechar. Usar quando a pessoa disser "vou começar o executivo", "o que pode dar errado aqui" ou "revisa meu projeto antes da obra".
---

# Análise preditiva do executivo

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

1. **Civil e estrutura.** Demolição, alvenaria nova, viga e pilar que não podem ser tocados, impermeabilização, nível de contrapiso, rebaixo de forro.
2. **Elétrica e automação.** Ponto onde vai ter bancada, tomada em ilha, carga de chuveiro e forno, quadro que não comporta, interruptor no lado errado da porta, ponto de dado e de TV.
3. **Hidráulica.** Prumada existente contra ponto novo, caimento, esgoto de máquina, ponto de água quente, registro acessível.
4. **Climatização e exaustão.** Dreno da condensadora, posição da evaporadora contra viga e cortineiro, exaustão de cooktop, ventilação de banheiro sem janela.
5. **Marcenaria e bancadas.** Folga de instalação, porta que bate em porta, gaveta que não abre por causa de rodapé, altura de bancada contra usuário, apoio de cuba, vão de eletrodoméstico.
6. **Acabamentos e paginação.** Início de paginação, recorte em ralo e em ponto, junta, transição de piso, arremate de forro.
7. **Circulação e uso.** Largura de passagem, giro de porta, área de aproximação, altura de guarda-corpo, uso por criança, idoso ou pet quando o briefing indicar.
8. **Prazo e sequência.** O que precisa ser decidido antes do quê, e o que tem prazo de fornecedor maior que o prazo de obra.

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

**4. As demais, por disciplina.** Importantes e de atenção, agrupadas.

**5. A ordem de decisão.** O que precisa ser decidido antes do quê, considerando prazo de fornecedor. É a seção que evita o executivo travar esperando uma escolha.

**6. O que eu não consegui analisar.** As disciplinas sem material suficiente, com o que falta em cada uma.

**7. O que eu assumi.** Toda inferência listada, para confirmar ou derrubar.

## Como a skill se comporta

Antes de gerar, faz **uma pergunta por vez**, numerada, com opções rotuladas por letra e sempre a alternativa "outra, eu explico", para permitir resposta por voz. No máximo cinco perguntas, e só sobre o que muda o resultado.

Se o material for suficiente, entrega direto.

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

Esta é a versão do Workshop Projeto de Primeira com IA. Ela roda com o que estiver na mão e cobre as oito disciplinas acima.

A versão completa, que cruza cada achado contra a Biblioteca Técnica do escritório e contra os checklists próprios da pessoa, emenda na revisão do executivo desenhado e vira plano de ação priorizado com aceite item a item, faz parte do programa de Implementação.
