# Modelos iniciais de registros

Exemplos conceituais; fixar schema, tipos de campos e identificadores durante E1. Copiar os modelos aprovados para Templates no vault. Valores abaixo sao ficticios. Listas vazias significam informacao ainda nao definida.

## Produto

```markdown
---
id: produto-exemplo
tipo: produto
titulo: Portal de Atendimento
estado: rascunho
fontes: []
---
# Portal de Atendimento
## Objetivo e usuarios
## Capacidades e fluxos
## Regras de negocio
## Glossario
## Integracoes e restricoes
## Pessoas e projetos relacionados
## Duvidas e fontes
```

## Projeto

```markdown
---
id: projeto-exemplo
tipo: projeto
titulo: Evolucao do Login
estado: rascunho
produtos: [produto-exemplo]
fontes: []
---
# Evolucao do Login
## Objetivo
## Escopo e exclusoes
## Entregas e andamento
## Riscos e dependencias
## Decisoes e refinamentos
## Pessoas e fontes
```

## Refinamento

```markdown
---
id: refinamento-exemplo
tipo: refinamento
titulo: Recuperacao de acesso
estado: rascunho
produtos: [produto-exemplo]
projetos: [projeto-exemplo]
fontes: []
---
# Recuperacao de acesso
## Problema e resultado esperado
## Comportamento e regras confirmadas
## Criterios de aceite
## Cenarios e excecoes
## Alternativas e decisoes
## Duvidas, bloqueios e dependencias
## Acoes relacionadas
```

## Reuniao ou entrada bruta

```markdown
---
id: reuniao-exemplo
tipo: reuniao
titulo: Alinhamento de login
estado: rascunho
data: 2026-10-09
pessoas: []
projetos: [projeto-exemplo]
fontes: []
---
# Alinhamento de login
## Fonte original
Link opcional e localizacao do original/anexos.
## Resumo revisado
## Decisoes
## Alinhamentos
## Minhas acoes
## Aguardando outras pessoas
## A confirmar
## Cobertura e limitacoes da analise
```

## Acao

```markdown
---
id: acao-exemplo
tipo: acao
titulo: Validar excecao de recuperacao
estado: a-confirmar
responsavel:
prazo:
dia_planejado:
projetos: [projeto-exemplo]
dependencias: []
fontes: [reuniao-exemplo]
---
# Validar excecao de recuperacao
## Resultado esperado
## Evidencia de origem
Trecho/localizador que sustenta a proposta.
## Bloqueios e prioridade
## Atualizacoes e conclusao
```

## Pessoa e fonte de conversa

```markdown
---
id: pessoa-exemplo
tipo: pessoa
titulo: Ana Exemplo
aliases: []
fontes: []
---
# Ana Exemplo
## Participacoes e papeis
Projeto / papel / periodo ou contexto / fonte.
## Assuntos e conversas relacionados
```

```markdown
---
id: fonte-exemplo
tipo: fonte-conversa
titulo: Grupo de alinhamento do login
modalidade: grupo-teams
url:
pessoas: []
projetos: [projeto-exemplo]
---
# Grupo de alinhamento do login
## Assuntos
## Entradas e reunioes relacionadas
## Limites de cobertura
Somente trechos fornecidos; historico completo nao importado.
```

## Decisao

```markdown
---
id: decisao-exemplo
tipo: decisao
titulo: Estrategia de recuperacao
estado: rascunho
substitui:
fontes: []
---
# Estrategia de recuperacao
## Contexto
## Escolha e justificativa
## Alternativas consideradas
## Consequencias e riscos
## Validacao e revisao
```

## Preferencia ou padrao

```markdown
---
id: padrao-exemplo
tipo: preferencia
titulo: Consultar decisoes antes de refinar
estado: rascunho
escopo: pessoal
fontes: []
---
# Consultar decisoes antes de refinar
## Orientacao proposta
## Evidencias independentes
## Contradicoes e excecoes
## Aprovacao, vigencia e revogacao
```

## Sessao e handoff

```markdown
---
id: sessao-exemplo
tipo: sessao
estado: interrompida
agente:
projetos: [projeto-exemplo]
fontes: []
---
# Sessao de trabalho
## Objetivo
## Resumo e cobertura da captura
## Concluido, tentado e nao verificado
## Decisoes e propostas
## Pendencias e handoffs
```

```markdown
---
id: handoff-exemplo
tipo: handoff
estado: rascunho
sessao_origem: sessao-exemplo
sessao_destino:
projetos: [projeto-exemplo]
fontes: [sessao-exemplo]
---
# Continuidade do trabalho
## Objetivo e escopo
## Estado atual e evidencias
## Arquivos e contexto Git, se aplicavel
## Testes executados e resultados
## Bloqueios e duvidas
## Proximo passo sugerido
## Autorizacoes conhecidas e pendentes
## Verificacoes antes de continuar
```

## Agenda

A tela Hoje consulta as acoes existentes. Se exportar uma nota diaria, incluir data de geracao e links para as acoes; ela e um retrato, nao fonte alternativa de estados. Evitar copiar tarefas para varias notas e perder sincronizacao.
