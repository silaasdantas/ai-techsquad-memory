# Continuidade no ambiente corporativo

## Instrucao inicial para a IA

```text
Leia README.md e todos os documentos numerados deste pacote.
Estamos construindo uma memoria pessoal de trabalho sobre uma squad.
O plano e autocontido; nao ha dependencia de acesso ao ai-memory.

Antes de implementar, leia as instrucoes locais e inspecione o ambiente.
Separe decisoes confirmadas, recomendacoes e escolhas pendentes.
Execute primeiro E0 do documento 05. Nao implemente todas as etapas de uma vez.
Nao invente hooks, APIs, regras de negocio, papeis ou permissoes corporativas.
Proponha a menor entrega verificavel e identifique perguntas bloqueadoras.
Instalacoes/dependencias e acoes sensiveis seguem autorizacoes do ambiente.
Preserve arquivos existentes e edicoes feitas no Obsidian.
Use dados ficticios ate confirmar o uso de material real.
Responda em portugues e registre evidencias da validacao.
```

## Preparacao pelo usuario

1. Levar esta pasta completa para o local permitido.
2. Informar local desejado do vault e pasta da aplicacao.
3. Informar ferramentas de IA disponiveis, modalidades e versoes conhecidas.
4. Informar runtime/provedor permitido e regras relevantes de envio de dados.
5. Configurar identidade/aliases para reconhecer suas pendencias.
6. Resolver escolhas bloqueadoras com a IA e autorizar apenas a etapa seguinte.

Nao copiar credenciais para estes documentos. Nao enviar este pacote a servicos externos se isso contrariar regras do ambiente.

## Prompt por etapa

```text
Implemente somente E<N> do documento 05, considerando as decisoes registradas.
Leia o progresso e o handoff anteriores; confira o estado real dos arquivos.
Apresente um plano curto e avance nas tarefas autorizadas e reversiveis.
Pergunte quando faltar uma escolha critica ou autorizacao necessaria.
Use os cenarios relevantes do documento 06 e registre resultados reais.
Ao terminar, atualize progresso, decisoes e handoff de implementacao.
Nao declare concluida uma etapa sem evidencias de seus criterios de aceite.
```

## Arquivos de continuidade a criar no destino

- `IMPLEMENTATION-STATUS.md`: etapa, criterios cumpridos, evidencias, falhas e proximo passo.
- `DECISIONS.md`: escolhas tecnicas, data, motivo, alternativas e impactos.
- `IMPLEMENTATION-HANDOFF.md`: objetivo atual, arquivos, comandos/testes, pendencias e limites.
- `ENVIRONMENT.md`: ferramentas/versoes, caminhos nao secretos e capacidades verificadas.

Estes arquivos podem ficar junto ao plano, fora do vault de conhecimento da squad. Sao sobre construir a ferramenta, nao sobre o trabalho dos produtos.

## Modelo de progresso

```markdown
# Progresso
Etapa: E0
Estado: nao iniciada
Data:

## Criterios demonstrados
- Criterio / evidencia:

## Validacao
- Comando ou cenario:
- Resultado:

## Pendencias bloqueadoras
- Questao / responsavel:

## Proximo passo autorizado
- Acao:
```

## Modelo de handoff de implementacao

```markdown
# Handoff de implementacao
Objetivo:
Etapa:
Agente/sessao:
Repositorio/branch/commit, se aplicavel:

## Concluido e verificado

## Alteracoes locais ainda nao commitadas

## Arquivos relevantes

## Comandos e resultados

## Tentativas e falhas

## Decisoes e limites de autorizacao

## Proximo passo sugerido

## O que verificar antes de continuar
```

## Evolucao do plano

Ao descobrir incompatibilidade, registrar fato e evidencia. Ajustar apenas a etapa afetada e manter o objetivo de uso. Se um cliente nao suportar hooks, documentar fallback manual; nao simular captura inexistente. Alteracoes que mudam escopo, compartilhamento ou envio de dados precisam de decisao explicita.

## Primeiro pedido recomendado

Solicitar E0 e um plano concreto para E1. Depois validar uma nota no Obsidian e na Web UI antes de integrar IA, hooks ou todos os agentes.
