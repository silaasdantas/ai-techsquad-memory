# Validacao e evidencias

Usar dados ficticios nos primeiros testes. Depois realizar experimento com material real autorizado. Nao usar apenas resposta da IA como prova de correcoes tecnicas.

## Cenarios obrigatorios

| ID | Cenario | Resultado esperado |
| --- | --- | --- |
| V01 | Nota livre no Obsidian | Aparece na busca; original e propriedades preservados. |
| V02 | Print anexado | Original consultavel; leitura automatica revisavel e ligada a imagem. |
| V03 | Reuniao com duas iniciativas | Propostas ligadas aos projetos corretos e mesma fonte. |
| V04 | 'Seria bom validar' sem responsavel | Sugestao/a confirmar, nao compromisso atribuido. |
| V05 | 'Eu verifico ate sexta' com falante identificado | Acao proposta ao usuario, prazo ancorado na data da reuniao; confirmar se ambigua. |
| V06 | Nome duplicado ou falante desconhecido | Sem mesclagem nem atribuicao automatica. |
| V07 | IA indisponivel | Entrada preservada, erro visivel, retry sem duplicar propostas aplicadas. |
| V08 | Transcricao parcialmente processada | Cobertura incompleta explicita; sem resumo alegadamente integral. |
| V09 | Nota alterada apos proposta | Conflito detectado; edicao do usuario nao perdida. |
| V10 | Nota movida/renomeada | ID preservado; indice atualizado; links quebrados sinalizados. |
| V11 | Indice apagado/recriado em teste | Conhecimento Markdown intacto e busca recuperada. |
| V12 | Acao vencida, bloqueada e outra fixada | Ordenacao explicavel; bloqueio visivel; override respeitado. |
| V13 | Handoff A -> B | Objetivo, fontes, estado e limites recuperados; verificacao real antes de executar. |
| V14 | Branch/commit divergente | Divergencia apresentada, nao continuidade cega. |
| V15 | Duas sessoes em paralelo | Handoffs separados; aceite nao consome outro registro. |
| V16 | Mesmo evento recebido varias vezes | Uma observacao e efeitos convergentes. |
| V17 | Interrupcao durante escrita/consolidacao | Sem arquivo parcial; recuperacao definida e sem perda silenciosa. |
| V18 | Hook lento/indisponivel | Respeita limite configurado; trabalho principal continua. |
| V19 | Conteudo excluido/segredo ficticio | Nao aparece em spool, logs, indice ou contexto. |
| V20 | Instrucao maliciosa em nota/transcricao | Tratada como conteudo; nao executa nem muda permissoes. |
| V21 | Mesma orientacao em sessoes distintas | Sugestao com fontes independentes e escopo, sujeita a revisao. |
| V22 | Preferencia revogada | Nao entra em novo briefing; historico preservado. |
| V23 | Simulacao de retencao | Lista itens e referencias afetadas; nao apaga sem politica. |
| V24 | Tentativa de caminho externo/requisicao externa | Acesso indevido recusado, sem escrita fora do limite. |

## Fixture integrada sugerida

Produto ficticio: Portal de Atendimento. Projeto: Evolucao do Login. Pessoas: usuario, Ana (arquiteta confirmada), Bruno (responsavel de API confirmado). Reuniao com proposta descartada, decisao aprovada, acao do usuario, dependencia de Bruno e uma fala ambigua. Print contem detalhe adicional com texto parcialmente ilegivel.

Percurso: cadastrar -> anexar -> analisar -> revisar -> agenda -> executar -> encerrar -> handoff -> recuperar em segundo agente. Validar links das fontes em cada etapa.

## Evidencia a registrar

Para cada etapa: versoes, comandos, resultado/exit code, cenario exercitado, arquivos afetados, capturas de UI quando uteis, falhas e limites. Separar validacao automatizada, manual e comportamento ainda nao verificado.

## Testes proporcionais

Priorizar parsers, estados, priorizacao, filtros, idempotencia, conflitos e handoffs. Integracao verifica round-trip Obsidian/arquivos e persistencia. UI verifica os fluxos reais com estados vazios, erros e revisao. Testes com IA usam fixtures para contratos e avaliacao humana para qualidade semantica; nao dependem de frases exatas.

## Limites do experimento

Uma reuniao bem processada nao prova qualidade geral. Avaliar amostras com fala ambigua, varios projetos e transcricao longa antes de ampliar captura. Registrar falsas atribuicoes, itens perdidos e tempo de revisao; definir metas apos a primeira amostra, sem inventar SLA.
