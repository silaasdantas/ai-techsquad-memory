# Planejamento do Squad Memory

Status: planejamento aprovado em conversa; implementacao ainda nao iniciada.
Data: 2026-10-09.

Este pacote e autocontido. Sua finalidade e permitir construir e evoluir a solucao no ambiente corporativo com as IAs disponiveis, sem precisar baixar o projeto ai-memory ou consultar a conversa original.

## Objetivo

Criar uma memoria pessoal de trabalho sobre uma squad: produtos, projetos, refinamentos, pessoas, fontes de conversa, reunioes, decisoes, padroes, acoes e continuidade entre agentes. Reduzir a necessidade de reexplicar contexto sem transformar inferencias em fatos.

## Ordem de leitura

1. [Escopo e decisoes](01-escopo-e-decisoes.md): o que foi decidido e o que permanece aberto.
2. [Fluxos de uso](02-fluxos-de-uso.md): ciclo diario, reunioes, agenda e troca de agente.
3. [Registros e vault](03-registros-e-vault.md): organizacao, campos e relacionamentos.
4. [Comportamento tecnico](04-comportamento-tecnico.md): limites, captura, recuperacao e escrita.
5. [Plano de entregas](05-plano-de-entregas.md): sequencia, dependencias e criterios de aceite.
6. [Validacao](06-validacao.md): cenarios e evidencias de conclusao.
7. [Continuidade corporativa](07-continuidade-corporativa.md): instrucoes e prompts para implementar por etapas.
8. [Modelos de registros](08-modelos-de-registros.md): exemplos iniciais para adaptar.

## Decisoes centrais

- Interface web e armazenamento locais.
- Vault Obsidian dedicado, inicialmente pessoal, sobre a squad.
- Markdown como fonte de verdade do conhecimento; indices sao derivados.
- Entrada manual de notas, trechos do Teams, prints e transcricoes.
- Hooks para captura de interacoes com agentes, conforme capacidade real do cliente.
- Revisao antes de promover propostas a conhecimento vigente.
- Contexto compartilhado entre agentes por registros de sessao e handoffs explicitos.
- Agenda derivada de acoes e pendencias; prioridade explicavel e ajustavel.
- Aprendizado de preferencias recorrentes com evidencia e aprovacao.
- Imagens podem ser enviadas a IA; provedor e permissoes para outros tipos de conteudo ainda precisam ser definidos.

## Como utilizar este pacote

Levar a pasta inteira para o ambiente corporativo. Comecar pelo documento 07. Criar o vault e a aplicacao la, apos resolver as escolhas que bloqueiam a primeira entrega. Nao executar todas as etapas em uma unica solicitacao.

Este pacote nao cria o vault, nao instala hooks, nao configura provedores e nao modifica o prototipo existente em techlead-rag-mvp.

## Referencia e independencia

O ai-memory foi usado como referencia conceitual para captura por eventos, observacoes limitadas, resumo de sessao, consolidacao e recuperacao. Os requisitos abaixo descrevem nossa solucao e nao dependem de seus arquivos ou bibliotecas. A disponibilidade de hooks em Devin CLI, Claude e Copilot nao foi verificada no ambiente corporativo.

## Manutencao do planejamento

Atualizar estes documentos quando uma decisao mudar. Registrar motivo, alternativa e impacto. Manter requisitos aprovados, recomendacoes e pendencias distinguiveis. O progresso real deve conter evidencias, nao apenas estados como 'concluido'.
