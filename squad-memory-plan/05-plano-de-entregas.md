# Plano de entregas

Cada etapa deve produzir uma pequena versao utilizavel, documentacao atualizada e evidencia de validacao. Nao iniciar etapa dependente com contrato anterior indefinido.

## E0 - Descoberta no ambiente corporativo

Dependencias: nenhuma.

Tarefas: ler instrucoes locais; verificar ferramentas/versoes; identificar clientes de agentes e capacidades; escolher stack permitida; definir caminhos; registrar politica de dados/provedor; definir usuario/aliases. Listar decisoes que podem esperar e as que bloqueiam a etapa seguinte.

Entregaveis: documento de ambiente, decisoes tecnicas justificadas e plano ajustado. Aceite: E1 tem comandos, ferramentas e caminhos definidos; nenhum hook e considerado disponivel sem evidencia.

## E1 - Vault, registros e busca basica

Dependencias: E0.

Tarefas: criar estrutura e templates; implementar leitura de notas/propriedades/links; cadastro e edicao manual de produtos, projetos, refinamentos, pessoas, fontes e acoes; implementar busca textual e reindexacao. Criar UI minima que permita consultar/editar, sem depender de IA.

Aceite: conhecimento legivel no Obsidian; busca encontra fontes; indice reconstruivel; propriedades desconhecidas preservadas; pasta externa ao vault inacessivel para escrita.

## E2 - Entrada manual e anexos

Dependencias: E1.

Tarefas: Nova entrada/Inbox; texto e arquivos permitidos; preservacao do original; link Teams opcional; metadados conhecidos; descricao manual de imagens; estados de processamento e revisao.

Aceite: nota bruta com print pode ser registrada e consultada sem IA; anexo abre corretamente; entrada pode ser vinculada a varios assuntos sem duplicar original.

## E3 - Analise e revisao assistidas

Dependencias: E2 e configuracao/autorizacao do provedor.

Tarefas: resumo de reuniao; leitura visual; extracao de decisoes, alinhamentos, acoes e duvidas com localizadores; identidade/aliases do usuario; processamento de transcricao longa; revisao por item; escrita aprovada com conflito de versao.

Aceite: transcricao + print geram proposta corrigivel; ambiguidades nao viram compromissos; falha da IA preserva entrada; nenhuma nota editada no Obsidian e sobrescrita silenciosamente.

## E4 - Agenda e acompanhamento

Dependencias: E3; pode ser exercitada com acoes manuais da E1.

Tarefas: Hoje/Aguardando/A confirmar; prazo versus dia planejado; dependencia/bloqueio; regra explicavel de prioridade; override; conclusao, cancelamento, reabertura e acompanhamento de terceiros.

Aceite: mesma acao aparece coerentemente em projeto e agenda; prioridade tem motivo; alteracao de estado persiste e atualiza visoes; item externo nao e alterado automaticamente.

## E5 - Sessoes e handoff manual entre agentes

Dependencias: E1; usar conhecimento de E3/E4 quando disponivel.

Tarefas: iniciar/checkpoint/encerrar explicitamente; gerar briefing citado; criar handoff minimo; leitura sem consumo; selecao/aceite; divergencias do workspace; sessoes paralelas.

Aceite: agente B continua trabalho iniciado por A com fontes e limites; handoff nao concede autorizacao nova; diferenca de branch/arquivos e indicada. Um fluxo manual deve funcionar antes de hooks.

## E6 - Primeiro adaptador de hooks

Dependencias: E5 e verificacao de capacidades em E0.

Tarefas: escolher um cliente com eventos demonstrados; fixar contrato; filtros antes de persistencia; limites numericos; captura/entrega idempotentes; retry e estado visivel; checkpoint/fim; documentar instalacao e desativacao reversiveis.

Aceite: reentrega e reinicio nao duplicam observacoes/efeitos; hooks respeitam limite temporal; conteudo excluido nao aparece em fila/log/arquivo; encerramento manual continua disponivel.

## E7 - Outros clientes e interoperabilidade

Dependencias: E6.

Tarefas: validar Devin CLI, Claude e modalidade concreta de Copilot; implementar apenas adaptadores suportados; manter fallback manual; testar trocas em ambas as direcoes; comparar cobertura de captura.

Aceite: matriz documenta versao, eventos, injecao, limites e fallback por cliente. Nao exigir que todos tenham hooks iguais. Handoff comum e consumivel por todos os clientes escolhidos.

## E8 - Preferencias recorrentes e retencao

Dependencias: E3, E6 e uso real suficiente.

Tarefas: identificar recorrencias independentes; propor preferencias por escopo; contradicoes, aprovacao/revogacao; politica separada de retencao com simulacao, referencias e recuperacao quando possivel.

Aceite: uma regra rejeitada nao entra no briefing; regra revogada deixa de orientar; duplicatas nao contam como novas evidencias; nenhuma exclusao roda sem politica aprovada.

## Ordem recomendada

E0 -> E1 -> E2 -> E3 -> E4 -> E5 -> E6 -> E7 -> E8.

E5 pode antecipar E3/E4 se continuidade entre agentes for a maior dor. Essa escolha muda a ordem, nao elimina revisao, agenda ou entrada manual do escopo.

## Definition of Done por entrega

- Comportamento demonstrado com cenario da etapa.
- Testes proporcionais ao risco e resultados registrados.
- Comandos locais de execucao/validacao documentados.
- Limites, falhas e escolhas pendentes explicitados.
- Documento de progresso e handoff de implementacao atualizados.
- Nenhuma dependencia, instalacao ou configuracao sensivel introduzida sem autorizacao aplicavel.
