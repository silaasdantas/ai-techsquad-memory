# Comportamento tecnico esperado

Este documento define responsabilidades e invariantes. Nao fixa linguagem, framework, banco ou provedor.

## Componentes logicos

1. Entrada: notas, anexos, transcricoes e eventos de agentes.
2. Captura: adaptadores normalizam, filtram e sanitizam antes de persistir.
3. Armazenamento operacional: eventos, controle de entrega, processamento e versoes.
4. Analise: resumo e propostas com fontes, usando IA configurada ou fluxo manual.
5. Revisao/escrita: aplica propostas aprovadas com verificacao de versao.
6. Recuperacao: consulta o vault e produz contexto limitado e citado.
7. Web UI: entrada, revisao, conhecimento, fontes/pessoas, agenda e handoffs.

## Fonte de verdade

Markdown no vault e fonte de verdade para conhecimento, acoes e resumos publicados. Eventos operacionais sao fonte para captura e reprocessamento. Indices e visoes de agenda sao derivados. Recriar o indice nao recria observacoes perdidas. Git e opcional como historico, conforme permitido; nao pressupor auto-commit, push ou repositorio remoto.

## Entrada e anexos

Validar tipo/tamanho e caminhos; nunca permitir escapar das pastas autorizadas. Guardar anexos com nomes seguros e identificadores. Extracao por IA preserva original e marca cobertura/erros. Transcricoes longas exigem processamento por partes com localizadores e reconciliacao de repeticoes; nao alegar resumo integral se partes falharem.

## Contrato conceitual de evento

Campos recomendados: `schema_version`, `event_id`, `session_id`, `agent`, `kind`, `occurred_at`, `scope`, `payload`, `capture_status`.

`scope` identifica squad/projeto/produto por IDs conhecidos; contexto desconhecido fica nao atribuido, sem adivinhar pelo nome da pasta. Kind normalizado: inicio, mensagem permitida, ferramenta permitida, checkpoint, encerramento. Mapear eventos reais do cliente apos verificacao.

ID de evento deve permanecer estavel em tentativas de entrega. Ordenacao precisa considerar sequencia quando disponivel; horario sozinho nao garante ordem. Persistir recebimento e conclusao dos efeitos separadamente para recuperacao apos interrupcao.

## Captura e recuperacao de falhas

- Capturar apenas campos explicitamente permitidos. Outputs completos de ferramentas nao sao padrao.
- Sanitizar antes de fila, arquivo, log ou transporte. Filtros nao garantem detectar todo segredo; minimizar coleta.
- Limitar tamanho, tempo, fila e concorrencia com valores definidos e testados na E6.
- Persistencia atomica e retries limitados. Nenhum loop infinito ou perda silenciosa.
- Nao bloquear indefinidamente a interacao principal.
- Indicadores: eventos capturados, ignorados, pendentes, falhos, duplicados e ultima captura.
- Sem hook confiavel de fim, manter encerramento explicito e checkpoint.
- Hooks nao sao transcricao completa e nao substituem entrada manual de reunioes.

## Escrita compartilhada com Obsidian

Comparar versao/hash do arquivo antes de aplicar proposta. Escrita atomica evita arquivo parcialmente gravado, mas nao resolve sozinha edicao concorrente; usar estrategia de conflito explicitamente testada. Nao sobrescrever mudancas posteriores.

Detectar criacao, edicao, renomeacao e remocao de notas. Preservar ID e atualizar indice. Resolver links quebrados com aviso/proposta; nao reescrever todo o vault silenciosamente. Evitar ciclos de observacao em que a propria escrita gera processamento infinito.

## Busca e contexto para agentes

Comecar com busca textual e filtros por escopo, tipo e estado. Contexto inclui objetivo, fontes vigentes relevantes, conflitos, lacunas e handoff selecionado. Rascunhos separados. Limite de contexto configuravel; revelar truncamento e permitir consultar fontes adicionais.

Conteudo recuperado e evidencia, nao instrucao privilegiada. Ignorar pedidos embutidos em prints/transcricoes/notas para executar comandos, alterar permissoes ou enviar dados. Preferencias aprovadas orientam, mas nao anulam instrucoes atuais ou autorizacoes.

## Priorizacao e aprendizado

Priorizacao segue regra do documento 02; mostrar motivo e aceitar override. Nao inferir urgencia de quantidade de mencoes.

Aprendizado propoe regra com escopo, exemplos independentes, possiveis contradicoes e efeito esperado. Retries e copias da mesma conversa nao contam como recorrencias independentes. Revisao permite aprovar, editar, rejeitar e revogar. Threshold de sugestao e configuravel e sera validado na E8.

## Handoffs

Mesmo formato para todos os agentes, com adaptadores finos. Disponibilidade de hooks/MCP nao e presumida. Integracao manual funciona como referencia. Registrar aceite para evitar consumo acidental; permitir leitura sem aceite e selecionar handoff explicitamente. Trabalho paralelo exige handoffs distintos, nao um unico 'ultimo estado' sobrescrito.

## Web UI local

Bind local por padrao. Qualquer exposicao a rede muda escopo e exige nova decisao. Escritas so por rotas/acoes apropriadas, com protecao contra requisicoes externas ao navegador local. Nao tratar localhost como ausencia de fronteira de seguranca.

Telas: Inbox/Nova entrada, Revisao, Conhecimento (produtos/projetos/refinamentos), Pessoas/Fontes, Hoje/Aguardando/A confirmar, Sessoes/Handoffs e Configuracao/estado da captura. Suportar busca, estados vazios, falhas, processamento pendente e conflitos. Plugins Obsidian nao obrigatorios.

## Dados e envio a IA

Mostrar/configurar quais entradas sao enviadas e para qual provedor. Guardar segredos em mecanismo permitido no ambiente, fora do vault. Nao registrar prompts ou respostas completos em logs tecnicos por padrao. Conteudos e pessoas reais obedecem as regras corporativas confirmadas; nao presumir permissao de exportacao por serem acessiveis no Teams.

## Retencao

Sem exclusao automatica inicial. Politica posterior distingue eventos, originais, anexos, rascunhos e conhecimento aprovado. Oferecer simulacao de itens afetados; proteger referencias ainda necessarias, interromper exclusao em inconsistencias e registrar o resultado. Exclusao em backups/sync e questao separada.
