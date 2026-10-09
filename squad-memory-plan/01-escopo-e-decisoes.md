# Escopo e decisoes

## Problema

O contexto de trabalho esta distribuido entre conversas com agentes, Teams, reunioes, notas e imagens. Isso dificulta encontrar a origem de uma decisao, acompanhar compromissos e continuar um trabalho em outro agente.

## Decisoes confirmadas pelo usuario

| ID | Decisao | Consequencia |
| --- | --- | --- |
| D01 | Interface e armazenamento locais | Aplicacao opera no computador do usuario; nao presume servidor compartilhado. |
| D02 | Imagens podem ser enviadas a IA | Analise visual externa e possivel, conforme provedor escolhido. |
| D03 | Vault dedicado a squad | Nao varrer nem modificar outros vaults. |
| D04 | Entradas manuais | Colar notas e trechos, anexar prints e fornecer transcricoes. |
| D05 | Conhecimento de produtos, projetos e refinamentos | Esses registros sao parte central da base. |
| D06 | Pessoas e fontes de conversa | Manter papeis contextualizados e referencias ao Teams. |
| D07 | Hooks de captura | Incluir no plano e validar por cliente. |
| D08 | Handoffs entre agentes | Preservar continuidade entre Devin CLI, Claude e Copilot, com adaptadores. |
| D09 | Web UI | Oferecer consulta, revisao, acompanhamento e continuidade. |
| D10 | Agenda e priorizacao | Extrair pendencias e organizar o trabalho diario. |
| D11 | Reconhecimento de repeticoes | Propor preferencias e padroes para evitar orientacoes repetidas. |

## Recomendacoes propostas, ajustaveis na implementacao

- Primeiro uso pessoal; compartilhamento multiusuario fica fora da primeira versao.
- Revisao humana antes de publicar conhecimento, responsaveis ou padroes inferidos.
- Arquivos Markdown legiveis sem a aplicacao; metadados minimos e identificadores estaveis.
- Eventos tecnicos fora do vault e anexos fisicos dentro dele.
- Indice reconstruivel, sem banco vetorial no inicio.
- Adaptador manual universal antes de depender de hooks de um cliente.
- Nenhuma exclusao automatica ate haver politica de retencao explicita.

## Escopo funcional

Capturar -> preservar fonte -> propor organizacao -> revisar -> registrar -> recuperar -> executar -> atualizar -> continuar em outro agente.

Inclui notas livres, imagens, transcricoes, resumo de reuniao, acoes, alinhamentos, duvidas, bloqueios, conhecimento, busca, agenda, preferencias e handoffs.

## Fora do escopo inicial

- Importacao automatica de todo o Teams ou acesso automatico a links.
- Sincronizacao bidirecional com Jira ou calendario corporativo.
- Escrita em ferramentas corporativas, envio de mensagens ou publicacao automatica.
- Transferencia automatica de branches, arquivos ou permissoes entre agentes.
- SSO, usuarios compartilhados e hospedagem remota.
- Plugin Obsidian obrigatorio, embeddings e LLM local obrigatorio.

Catalogar um link nao significa acessar seu conteudo. Uma tarefa local pode referenciar um item externo sem substitui-lo como fonte oficial.

## Escolhas pendentes e quando resolve-las

| Escolha | Quando | Evidencia necessaria |
| --- | --- | --- |
| Sistema operacional e ferramentas permitidas | Antes da E1 | Runtime, instalacao, navegador e comandos disponiveis. |
| Stack e persistencia operacional | Antes da E1 | Alternativas permitidas, custo de manutencao, escrita concorrente e testes. |
| Local do vault e pasta operacional | Antes da E1 | Caminhos explicitos e politica de backup/sync. |
| Provedor/modelo de IA e credenciais | Antes da E3 | Endpoint permitido, tipos de dados autorizados, configuracao segura. |
| Envio de transcricoes e textos externos | Antes da E3 | Autorizacao aplicavel; permissao de imagens nao cobre automaticamente todo conteudo. |
| Identidade do usuario e aliases | Antes da E3 | Como reconhecer suas falas e compromissos. |
| Clientes, versoes e hooks reais | Antes da E6 | Documentacao e experimento com payload real. |
| Limites de tamanho, latencia e fila | Antes da E6 | Valores configurados e experimento mensuravel. |
| Retencao de eventos, anexos e sessoes | Antes da E8 | Prazos, excecoes, backup e procedimento de exclusao. |

## Retencao versus aprendizado

Retencao define por quanto tempo guardar registros. Aprendizado detecta recorrencias e propoe orientacoes futuras. Sao modulos diferentes; identificar um padrao nunca autoriza apagar sua evidencia.

## Criterios de sucesso

- Encontrar contexto com fonte sem reexplicar todo o projeto.
- Transformar uma reuniao em resumo e compromissos revisaveis.
- Trabalhar no mesmo conhecimento pelo Obsidian e pela Web UI sem perda de edicoes.
- Continuar em outro agente com objetivo, estado e limites claros.
- Saber por que uma acao foi priorizada.
- Corrigir ou revogar um padrao aprendido.
