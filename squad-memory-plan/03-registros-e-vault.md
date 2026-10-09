# Registros e vault

## Estrutura proposta

```text
squad-vault/
  00-Inbox/
  01-Squad/
  02-Produtos/
  03-Projetos/
  04-Refinamentos/
  05-Pessoas/
  06-Reunioes/
  07-Decisoes/
  08-Padroes/
  09-Acompanhamento/
  10-Sessoes-Handoffs/
  Anexos/
  Templates/
```

A aplicacao possui uma pasta operacional separada para eventos, fila, indice e configuracao nao secreta. Sua localizacao sera definida no ambiente corporativo. Credenciais nunca entram no vault, nos prompts ou em eventos.

## Convencoes

- Identificador estavel por registro; caminho e titulo podem mudar.
- Nomes de arquivo portaveis e sem caracteres invalidos no sistema de destino.
- Propriedades em YAML e corpo em Markdown; usar parser, nao substituicoes textuais improvisadas.
- Links Obsidian para navegacao e IDs para relacionamentos operacionais.
- Usar caminhos relativos para anexos e links; evitar nomes ambiguos entre pastas.
- Datas de eventos com fuso; datas de prazo/planejamento como data local explicita.
- Metadados desconhecidos sao preservados.
- 'Nao definido' nao e equivalente a vazio inferido, falso ou data atual.

## Campos comuns recomendados

`id`, `tipo`, `titulo`, `estado`, `criado_em`, `atualizado_em`, `fontes`, `produtos`, `projetos`, `pessoas`, `tags`.

Nao exigir todos os campos em notas livres. Conhecimento publicado requer origem verificavel ou declaracao explicita do usuario como fonte. Fonte pode ser nota original, trecho, sessao, imagem ou link com localizador.

## Registros

| Tipo | Campos/conteudo especificos |
| --- | --- |
| Entrada | Original, anexos, origem, data conhecida, estado de processamento. |
| Produto | Objetivo, usuarios, capacidades, regras, glossario, integracoes, restricoes. |
| Projeto | Objetivo, escopo, produtos afetados, entregas, riscos, dependencias, referencias externas. |
| Refinamento | Problema, comportamento, criterios de aceite, cenarios, decisoes e perguntas. |
| Pessoa | Nome, aliases confirmados, referencias e participacoes contextualizadas. |
| Fonte de conversa | Tipo, nome, URL opcional, participantes conhecidos, assuntos, data. |
| Reuniao | Data, participantes, resumo, alinhamentos, decisoes, transcricao e localizadores. |
| Decisao | Contexto, escolha, alternativas, justificativa, impacto, status e decisao substituida. |
| Padrao/preferencia | Instrucao, escopo, evidencias, aprovacao, vigencia e revogacao. |
| Acao | Descricao, responsavel, prazo, dia planejado, impacto, dependencias, estado e fonte. |
| Sessao | Agente, objetivo, escopo, inicio/fim, resumo, cobertura da captura e pendencias. |
| Handoff | Sessao origem, objetivo, estado real, evidencias, proximo passo, limites e aceite. |

## Relacionamentos

Produto possui projetos/refinamentos; projeto pode afetar varios produtos. Pessoa participa de projetos com um papel e periodo/contexto, sem presumir um cargo global. Acao pode depender de outra acao ou de resposta externa. Decisao substitui outra decisao. Handoff referencia sessao e fontes.

Uma pessoa mencionada nao vira responsavel. Nomes parecidos nao sao mesclados automaticamente. Papel 'arquiteto' deve ter fonte; participacao numa reuniao nao prova propriedade de um projeto.

## Estados

- Entrada: recebida -> em processamento -> aguardando revisao -> organizada; falha permite nova tentativa.
- Proposta: pendente -> aprovada / rejeitada; edicao gera nova versao da proposta antes de aprovar.
- Conhecimento: rascunho -> vigente -> substituido / arquivado.
- Acao: a confirmar -> aberta -> em andamento -> concluida; aberta/em andamento podem ir para bloqueada, aguardando ou cancelada; reabertura explicita permitida.
- Handoff: rascunho -> disponivel -> aceito -> concluido; pode ser cancelado ou substituido; aceite identifica agente/sessao destino.

'Aguardando revisao' e 'vigente' nunca sao intercambiaveis. Historico registra mudancas de estado, origem e ator humano/agente.

## Fontes e evidencia

Guardar o que foi fornecido, nao presumir transcricao integral. Cada derivado referencia ID da fonte e localizador: paragrafo, trecho, marcador temporal existente ou anexo. Registrar trechos omitidos/truncamento. Links externos podem ficar inacessiveis; consulta deve mostrar essa limitacao.

## Handoff minimo

Objetivo; escopo; concluido/tentado; arquivos/artefatos; testes e resultados; bloqueios; proximo passo sugerido; autorizacoes conhecidas e pendentes; contexto Git quando aplicavel; origem e data. Nao incluir credenciais. Nao tratar resumo como prova de que um teste passou.
