# Guia para comecar com Claude e usar a memoria

Este documento complementa o plano e o roteiro 07. Nao pressupoe que hooks, aplicacao ou vault ja estejam implementados. Os prompts de uso diario podem ser exercitados manualmente antes da automacao.

## 1. Preparar a primeira conversa

Abra a copia corporativa deste repositorio no cliente de IA que pode ler arquivos locais. Informe o caminho explicitamente. Se o cliente nao consegue ler arquivos, forneca o conteudo dos documentos; um caminho ou link sozinho nao comprova que foram lidos.

Separe dois objetivos: construir a ferramenta e trabalhar com o conhecimento da squad. Progresso da implementacao fica junto ao planejamento; conteudo da squad fica no vault dedicado, fora do repositorio publico.

Antes de iniciar, tenha estas informacoes quando possivel:

- Caminho do repositorio e local desejado do vault.
- Sistema operacional e ferramentas permitidas.
- Modalidade do Claude e outros clientes usados; versoes quando disponiveis.
- Provedor de IA permitido e limites de envio de texto/transcricoes/imagens.
- Nome e aliases que identificam voce nas reunioes.

Nao e necessario saber tudo antes da primeira conversa: o objetivo da E0 e levantar as lacunas.

## 2. Prompt inicial: descoberta e preparacao

```text
Vamos iniciar a implementacao do Squad Memory neste ambiente corporativo.

Leia as instrucoes locais do repositorio. Depois leia:
- squad-memory-plan/README.md
- todos os documentos de 01 a 09 em squad-memory-plan/

Se algum arquivo nao puder ser lido, diga qual e nao presuma seu conteudo.
Liste os arquivos efetivamente consultados.

Execute apenas E0 do documento 05. Pode fazer inspecoes nao destrutivas
e criar/atualizar os documentos de continuidade; nao instale dependencias,
nao configure hooks e nao implemente a aplicacao nesta etapa.

Objetivo: memoria pessoal sobre uma squad, Web UI e armazenamento locais,
vault Obsidian dedicado, entrada manual de notas/prints/transcricoes,
revisao de propostas, agenda, conhecimento de produtos/projetos/refinamentos,
pessoas/fontes e continuidade entre agentes. Imagens podem ser analisadas
por IA, conforme regras e provedor do ambiente.

Separe fatos verificados, hipoteses, recomendacoes e decisoes pendentes.
Inspecione ferramentas, estrutura e versoes sem ler credenciais.
Nao suponha suporte a hooks pelo nome do cliente.
Pergunte apenas pelas escolhas criticas que bloqueiam E1.
Compare alternativas permitidas e recomende a menor solucao verificavel.

Crie em uma pasta local docs/implementation/, sem dados sensiveis:
ENVIRONMENT.md, DECISIONS.md, IMPLEMENTATION-STATUS.md e
IMPLEMENTATION-HANDOFF.md, conforme o roteiro 07.
Nao coloque esses arquivos no Git publico sem revisao explicita.

Ao terminar, entregue:
1. Ambiente verificado e lacunas.
2. Escolhas necessarias e recomendacao com motivos.
3. Plano concreto para E1 e seus criterios de aceite.
4. Arquivos alterados e verificacoes realizadas.

Nao declare E0 concluida se ainda faltarem escolhas bloqueadoras de E1.
Nao faca commit, push, publicacao ou alteracao externa.
```

## 3. Aprovar escolhas e iniciar uma entrega

Resolva as perguntas da E0 e registre as escolhas antes de usar este prompt. Substitua os campos entre sinais de menor/maior; nao deixe autorizacoes vagas.

```text
As escolhas aprovadas sao:
- Stack: <escolha>
- Vault: <caminho>
- Pasta operacional: <caminho>
- Dependencias autorizadas: <lista ou nenhuma>
- Restricoes adicionais: <restricoes>

Registre essas decisoes. Implemente somente E1 do documento 05.
Leia o estado atual e preserve alteracoes existentes.
Divida a etapa em incrementos pequenos e valide cada fluxo relevante.
Comece com uma nota ficticia de produto legivel no Obsidian,
consultavel na Web UI e encontrada na busca com fonte.

Cubra os criterios de aceite de E1 antes de ampliar o escopo.
Nao antecipe IA, hooks, automacoes ou banco vetorial.
Se uma escolha nova mudar custo, dados ou contrato, exponha o impacto.
Atualize docs/implementation/ com comandos, resultados e pendencias.
Nao faca push nem envie conteudo corporativo ao repositorio publico.
```

Para etapas seguintes, trocar E1 pela etapa autorizada, indicar dependencias e usar os cenarios relevantes do documento 06. Nao autorizar 'construir tudo' antes do primeiro fluxo real.

## 4. Retomar em outra conversa ou agente

```text
Continue a implementacao a partir dos arquivos locais, nao de memoria presumida.
Leia o plano, docs/implementation/ e as instrucoes locais.
Confira o estado real do repositorio e as alteracoes nao commitadas.
Informe a etapa atual, o que esta verificado e as divergencias do handoff.
O proximo passo autorizado e: <acao ou etapa>.
Nao trate uma sugestao no handoff como autorizacao adicional.
Execute apenas esse passo e atualize progresso e handoff ao concluir.
```

## 5. Experimento antes da automacao

Usar um produto ficticio, um projeto, duas pessoas, uma nota de reuniao e um print. Primeiro conferir se o resumo e as acoes fazem sentido. Depois persistir, pesquisar e retomar em outro agente. Nao esperar todos os adaptadores ficarem prontos para aprender com o uso.

Enquanto a ferramenta nao existe, o Claude pode propor Markdown com os modelos do documento 08. Aprovacao e escrita sao passos explicitos; isso nao e equivalente a captura automatica.

## 6. Prompts para o trabalho diario

### Iniciar o dia

```text
Consulte minhas acoes, pendencias e compromissos na data <data e fuso>.
Separe Hoje, Aguardando e A confirmar.
Sugira prioridades pela regra aprovada, explicando o motivo de cada uma.
Considere bloqueios, prazo e dia planejado como coisas diferentes.
Nao invente responsavel, prazo, impacto ou urgencia.
Mostre fontes e conflitos. Nao altere prioridades ou estados sem minha revisao.
```

### Organizar nota bruta ou print

```text
Organize esta entrada sem perder o original:
<conteudo e anexos>
Fonte/link opcional: <referencia>
Contexto conhecido: <produto, projeto, data ou nao definido>

Proponha assuntos e vinculos, resumo, acoes, decisoes e duvidas.
Separe informacao explicita de inferencia.
Cada proposta deve apontar para trecho ou imagem de origem.
Marque ambiguidades para confirmar e leitura visual incompleta.
Nao atribua papeis ou mescle pessoas apenas por nomes semelhantes.
Apresente as propostas antes de atualizar o conhecimento vigente.
```

### Resumir transcricao

```text
Analise a transcricao fornecida e indique sua cobertura real.
Reuniao/data: <informacao conhecida>
Minha identificacao e aliases: <identificacao>

Entregue resumo por assunto/projeto, decisoes, alinhamentos,
minhas acoes, acoes de terceiros, bloqueios e pontos a confirmar.
Distinga sugestao de compromisso e alternativa de decisao tomada.
Inclua evidencia por item e marcador temporal apenas quando existir.
Se a transcricao for longa, processe partes e reconcilie repeticoes.
Nao declare resumo integral se alguma parte faltar ou falhar.
Nao grave propostas como aprovadas.
```

### Preparar refinamento

```text
Prepare o refinamento de <tema> para <produto/projeto>.
Consulte regras vigentes, decisoes, refinamentos relacionados e fontes.
Separe problema, resultado esperado, comportamento, criterios de aceite,
cenarios, dependencias, riscos e perguntas abertas.
Sinalize regras conflitantes ou ainda propostas.
Nao invente comportamento de negocio nem trate criterio sugerido como aprovado.
```

### Atualizar o acompanhamento

```text
Para a acao <ID>, proponha atualizar <estado/prazo/dia planejado>.
Evidencia ou motivo: <informacao>.
Mostre o impacto nas dependencias e na agenda.
Nao altere sistemas externos e nao duplique a acao em outra nota.
```

### Encerrar trabalho e preparar handoff

```text
Prepare o encerramento desta sessao e um handoff para <agente ou nao definido>.
Inclua objetivo, escopo, concluido, tentado, arquivos, fontes,
testes e resultados reais, bloqueios e proximo passo sugerido.
Inclua branch/commit e alteracoes locais quando houver trabalho de codigo.
Separe autorizacoes conhecidas de acoes que ainda dependem de aprovacao.
Indique lacunas da captura. Nao diga que testes passaram sem evidencia.
Mostre propostas de conhecimento separadas do handoff para minha revisao.
```

### Propor um padrao recorrente

```text
Procure orientacoes que repeti em sessoes independentes sobre <escopo>.
Proponha uma preferencia com exemplos, fontes, escopo e excecoes.
Nao conte copias ou retries como evidencias independentes.
Nao transforme frequencia em regra de negocio.
Somente orientacoes aprovadas devem influenciar sessoes futuras.
```

## 7. Habitos de uso recomendados

- Informar projeto/objetivo ao iniciar e link/data quando conhecidos.
- Revisar atribuicao de responsavel, prazo e decisao antes de aprovar.
- Registrar conclusao e bloqueio na acao original.
- Encerrar com handoff quando trocar de agente; lembrar que arquivos nao sao transferidos por memoria.
- Revisar periodicamente Inbox e A confirmar; a frequencia fica a criterio do usuario.
- Manter fontes e atualizar regras substituidas, em vez de acumular versoes contraditorias como vigentes.
- Pedir 'arquivos consultados, lacunas e evidencia' quando uma resposta parecer excessivamente certa.

## 8. Limite do repositorio publico

Este GitHub e para planejamento e, futuramente, codigo/exemplos ficticios revisados. O vault real, transcricoes, prints, pessoas e contexto corporativo ficam em armazenamento permitido separado. Antes do primeiro uso real, configurar exclusoes e confirmar que nenhuma pasta de dados e rastreada. Nao presumir que .gitignore remove arquivos ja commitados.

A publicacao deste guia nao autoriza publicar conhecimento corporativo nem documentos de ambiente. Continuar a implementacao no ambiente corporativo nao exige enviar suas anotacoes para este servidor.
