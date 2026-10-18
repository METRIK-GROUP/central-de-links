---
name: wpdp-executivo-com-ia
description: Monta com você a base para o Claude desenhar o projeto executivo da Fase 1 no padrão do seu escritório e conduz o primeiro projeto, prancha por prancha. Segue o passo a passo do Workshop Projeto de Primeira com IA. Conectar o Claude ao seu software (CADCraft para CAD, pyRevit para Revit ou o MCP do Archicad), criar a pasta Executivo com IA, montar a biblioteca técnica, gerar o guia em Markdown, criar o padrão das pranchas, criar o revisor e entregar o primeiro projeto. Usar quando a pessoa disser "quero fazer o executivo com IA", "como começo o detalhamento com o Claude", "vamos montar o padrão das pranchas" ou "continuar o executivo com IA".
---

# Executivo com IA

> **Responda sempre em português do Brasil**, inclusive as perguntas, os títulos e todo o texto dos arquivos que você criar.

## O que esta skill faz

Ela conduz a pessoa pelos oito passos que deixam o Claude pronto para desenhar o executivo da Fase 1 no padrão do escritório dela, e depois pelo primeiro projeto.

A lógica é a mesma de trabalhar com um time: **a pessoa cria o padrão e dá o direcionamento, o Claude executa, a pessoa revisa.** Ela não precisa abrir o software de detalhamento. O que ela olha é a prancha pronta, num revisor.

Os passos 1 a 7 são feitos uma vez só. O passo 8 se repete a cada projeto.

## Regras que valem em todos os passos

1. **A decisão é humana.** Você executa e confere. Quem decide e aprova é a pessoa.
2. **Nada entra na prancha sem fonte.** Toda informação vem de um documento: layout aprovado, levantamento, briefing ou resposta do cliente. O que falta vira **A CONFIRMAR** na prancha e na lista de perguntas. Nunca preencha lacuna com palpite, nem medida, nem material, nem altura.
3. **Cada informação mora na disciplina certa.** Troca de piso é prancha de piso, não de demolição.
4. **A legenda explica, a etiqueta completa.** Etiqueta só para o que a legenda não diz. Repetir o que a legenda já diz é ruído.
5. **Nunca altere um arquivo original da pessoa ou do cliente.** Trabalhe sempre em cópias dentro da pasta Executivo com IA.
6. **Pergunte uma coisa de cada vez, em perguntas numeradas.** Quando precisar de várias respostas, numere para a pessoa responder 1, 2, 3.
7. **Nada vai para o cliente por você.** Você prepara; quem envia é a pessoa.

## Como começar cada conversa

Antes de qualquer coisa, procure a pasta **Executivo com IA** no Google Drive da pessoa.

- Se ela existir, leia o `STATUS.md` e o `licoes.md`, diga em duas linhas em que passo vocês estão e continue dali.
- Se não existir, comece pelo passo 1.

Ao terminar cada conversa, atualize o `STATUS.md` (o que foi feito, o que falta, as perguntas em aberto) e o `licoes.md` (o que você aprendeu, errou ou melhorou, com data).

## Passo 1 · Abrir o Claude Code

Esta skill precisa trabalhar com as pastas e os programas do computador da pessoa. Isso só acontece no **Claude Code**.

- Se você estiver num chat comum do Claude, sem acesso às pastas, avise e peça para a pessoa abrir o Claude Code e chamar a skill de novo por lá.
- No Claude Code, confirme que você enxerga a pasta do Google Drive da pessoa (no Mac costuma ficar em `~/Library/CloudStorage/GoogleDrive-<email>/`; no Windows, numa unidade como `G:\`). Se não encontrar, pergunte onde fica.

## Passo 2 · Conectar o Claude ao software

Pergunte qual software o escritório usa para o executivo:

1. CAD (qualquer programa que trabalhe com DWG ou DXF)
2. Revit
3. Archicad

**CAD · CADCraft** (`https://github.com/storytold/cadcraft`)

- É um programa de CAD de código aberto que você comanda por linha de comando (`cadcraft-cli`), sem precisar abrir a janela do programa.
- Instale a partir da versão mais recente publicada em `https://github.com/storytold/cadcraft/releases`, escolhendo o arquivo do sistema da pessoa. Se não houver versão pronta para o sistema dela, siga o "Quick start" do README.
- Confira que o `cadcraft-cli` responde. Faça um teste: desenhe um retângulo, salve um DXF e exporte um PNG. Mostre o PNG para a pessoa.
- No trabalho, prefira mandar os comandos num arquivo de script para o `cadcraft-cli`. O programa com janela é opcional, só para quem quiser olhar.

**Revit · pyRevit** (`https://github.com/pyrevitlabs/pyRevit`)

- O pyRevit deixa você rodar rotinas dentro do Revit. O Revit só roda no Windows.
- Siga a instalação oficial indicada no README do pyRevit e use o instalador da versão mais recente em `https://github.com/pyrevitlabs/pyRevit/releases`.
- Confira que a aba do pyRevit aparece no Revit. Faça um teste só de leitura, por exemplo listar os níveis ou as folhas de um arquivo de exemplo.
- Antes de qualquer rotina que altere um modelo, trabalhe numa cópia do arquivo.

**Archicad · MCP oficial da Graphisoft, em beta** (`https://help.graphisoft.com/.beta2026/en/AI_Assistant_NewTopics/public_mcp_connection.html`)

- É uma prévia técnica do programa Beta 2026 da Graphisoft. Avise a pessoa que o recurso pode mudar.
- Ele conecta o **Claude Desktop** ao Archicad. O passo a passo da Graphisoft:
  1. Descobrir onde fica o arquivo de configuração do Claude Desktop (você pode dizer à pessoa onde ele fica no sistema dela).
  2. No Archicad, em Options, escolher "Configure Public MCP Server", clicar em Browse, escolher esse arquivo e clicar em Configure.
  3. Fechar o Claude Desktop por completo (File > Exit, não só fechar a janela) e abrir de novo.
  4. Testar pedindo ao Claude: "Get Archicad instances". Se não funcionar, reiniciar o computador.
- A configuração é feita uma vez só. Se houver vários Archicads abertos, o Claude pergunta qual projeto usar.

Registre no `STATUS.md` qual caminho foi instalado e o resultado do teste.

## Passo 3 · Criar no Drive a pasta Executivo com IA

Crie no Google Drive da pessoa:

```
Executivo com IA/
  STATUS.md          em que passo estamos, o que falta, perguntas em aberto
  licoes.md          aprendizados, erros e melhorias, sempre com data
  PROCESSO.md        como o trabalho é feito, atualizado a cada rodada
  biblioteca/        o material de referência do escritório (passo 4)
  guia/              o guia em Markdown (passo 5)
  padrao/            o padrão das pranchas (passo 6)
  revisor/           o revisor e as revisões exportadas (passo 7)
  projetos/          uma pasta por projeto (passo 8)
```

Explique para a pessoa que esta pasta é a memória do trabalho: tudo o que você aprende fica aqui, e o próximo projeto começa melhor que o anterior.

## Passo 4 · Montar a biblioteca técnica

Peça para a pessoa colocar em `biblioteca/` (ou apontar onde estão) os materiais que definem o padrão do escritório:

- exemplos de executivos já entregues, de preferência os que ela considera bem feitos
- os checklists de cada disciplina
- workbooks, templates de prancha, carimbo e legendas, se tiver
- qualquer documento de padrão: nomenclatura de arquivos, escalas, camadas

Não mova nem altere os originais: copie ou registre o caminho.

Depois, escreva `biblioteca/INVENTARIO.md` com cada arquivo, o que ele é, a que disciplina se refere e o que está faltando. Mostre as lacunas em perguntas numeradas.

## Passo 5 · Pedir o guia em Markdown

Leia a biblioteca inteira e escreva `guia/GUIA-EXECUTIVO.md`. É ele que você consulta daqui para frente, em vez de abrir todos os checklists de cada disciplina toda vez.

O guia traz:

- a ordem das pranchas da Fase 1 do escritório
- para cada disciplina: o que a prancha mostra, as convenções de representação (linhas, hachuras, símbolos), o que vai na legenda, o que é obrigatório constar e os erros mais comuns
- carimbo, escalas, formato e nomenclatura

Cada regra do guia cita o arquivo da biblioteca de onde veio. O que a biblioteca não responde vira **A CONFIRMAR** e entra numa lista de perguntas numeradas para a pessoa.

Sempre que a biblioteca mudar, atualize o guia.

## Passo 6 · Criar o padrão das pranchas

No software escolhido no passo 2, monte o jogo completo de pranchas vazias da Fase 1, na ordem do guia, com carimbo, legenda de cada disciplina, escala e formato.

- Exporte em PDF e peça para a pessoa revisar.
- Ajuste até ela aprovar.
- Registre o padrão aprovado em `padrao/PADRAO-PRANCHAS.md` (formato, carimbo, ordem, legendas, camadas) e guarde o arquivo-modelo em `padrao/`.

Esse padrão é a base de todos os projetos. Nenhuma prancha sai fora dele.

## Passo 7 · Criar o revisor

Crie um revisor em HTML, num arquivo só, que abre no navegador. Pergunte se a pessoa prefere um artefato do Claude ou um arquivo na pasta `revisor/`.

O revisor precisa:

- mostrar as pranchas (PDF ou PNG), com zoom e arraste
- deixar a pessoa clicar num ponto e escrever uma observação
- medir: dois cliques e a distância na escala da prancha
- listar as observações por prancha, cada uma marcada como aberta ou resolvida
- exportar as observações num arquivo que você consegue ler

Quando a pessoa exportar uma revisão, leia o arquivo, registre cada item em `revisor/registro-revisoes.md` e classifique: **correção pontual** (só nesta prancha) ou **regra** (vale para sempre). Regra vai para o `licoes.md` e para o guia.

## Passo 8 · Entregar o primeiro projeto de Fase 1

Crie `projetos/<nome-do-projeto>/` e peça os dois documentos de partida:

- a **planta de levantamento** do imóvel
- o **layout aprovado** pelo cliente

Depois, a pessoa pode entregar mais material: arquivos do SketchUp, IFC, briefing, respostas do cliente. Leia direto dos arquivos e trabalhe sempre sobre cópias.

Trabalhe **prancha por prancha**, na ordem do guia. Para cada uma:

1. **Leia** os documentos e organize o que importa: ambientes, medidas, pé-direito, decisões já tomadas.
2. **Faça a lista da disciplina.** Cada item com o quê, onde, quanto, de onde veio a informação e se está resolvido ou pendente.
3. **Desenhe** a partir da lista, no padrão do passo 6, com o layout aprovado como base.
4. **Confira antes de gerar o PDF.** A base é o layout aprovado? A legenda cobre todas as convenções usadas? Os textos obrigatórios estão lá? As pendências estão listadas? Se alguma resposta for não, corrija antes.
5. **Gere o PDF** e avise a pessoa para revisar no revisor.
6. **Transforme as dúvidas em perguntas numeradas**, para o cliente ou para o escritório.
7. **Nova rodada:** quando as respostas e as revisões chegarem, atualize a lista, desenhe de novo e suba a revisão (R00, R01, R02…).

Enquanto trabalha, documente o processo em `PROCESSO.md` e registre no `licoes.md` cada erro e cada melhoria. O erro de hoje vira regra da conferência amanhã.

## O que não fazer

- Não inventar medida, material, altura ou especificação.
- Não pular a revisão humana, nem quando a conferência passar.
- Não alterar arquivos originais da pessoa ou do cliente.
- Não enviar nada ao cliente.
- Não colocar a mesma informação em duas disciplinas.
