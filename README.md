# Tarefa: Implementar um sistema otimizado de contexto, memória e arquitetura para agentes de IA

Você deve analisar este projeto e implementar uma estrutura de contexto persistente para agentes de IA, priorizando economia de tokens, precisão técnica, rastreabilidade das dependências entre arquivos e continuidade do trabalho entre sessões.

O objetivo NÃO é apenas criar arquivos de documentação. Você deve construir um sistema útil, enxuto, atualizado e integrado às funcionalidades reais do Antigravity.

## 1. Fase inicial: analisar o ambiente

Antes de modificar qualquer arquivo:

1. Inspecione a estrutura do repositório, identificando linguagens, frameworks, módulos, ferramentas de build, testes e configurações existentes.
2. Identifique as instruções já utilizadas pelo projeto, incluindo `AGENTS.md`, arquivos de regras, Skills, configurações de agentes e documentação.
3. Verifique quais mecanismos de regras, memória e Skills são realmente suportados pela versão e pelo ambiente atual do Antigravity.
4. Identifique duplicações, instruções conflitantes e documentação desatualizada.
5. Analise o grafo de dependências do projeto, incluindo imports, exports, chamadas entre módulos, interfaces, contratos de API, schemas e testes.
6. Preserve todas as configurações e instruções úteis já existentes.

Não presuma que diretórios ou recursos específicos são suportados. Consulte a documentação disponível e os arquivos existentes antes de escolher os caminhos e formatos.

Após a análise, prossiga com a implementação sem interromper o trabalho para solicitar autorização para mudanças documentais não destrutivas.

## 2. Criar uma camada de instruções permanentes

Crie ou aperfeiçoe o arquivo de instruções principal na localização apropriada para o ambiente detectado.

Esse arquivo deve conter somente instruções essenciais e de aplicação geral:

- Como investigar o projeto antes de modificar código.
- Como identificar arquivos relacionados e dependências.
- Como evitar refatorações desnecessárias.
- Como preservar contratos e compatibilidade.
- Como executar testes e validar alterações.
- Como utilizar a documentação e a memória persistente.
- Como atualizar a documentação quando houver mudanças relevantes.

Mantenha as instruções concisas. Não inclua grandes exemplos de código, explicações extensas de arquitetura ou regras específicas de todas as tecnologias nesse arquivo.

Não crie instruções globais redundantes caso já exista uma configuração equivalente.

## 3. Construir a documentação arquitetural

Crie uma documentação arquitetural proporcional à complexidade real do projeto.

No mínimo, quando aplicável:

### `docs/architecture.md`

Documente:

- Objetivo e visão geral do sistema.
- Tecnologias e responsabilidades principais.
- Organização arquitetural.
- Fluxos de execução importantes.
- Limites entre módulos.
- Dependências externas relevantes.
- Pontos críticos para manutenção.

### `docs/modules.md`

Crie um mapa de módulos com:

- Nome do módulo ou diretório.
- Responsabilidade.
- Arquivos de entrada e pontos de inicialização.
- Principais dependências.
- Consumidores relevantes.
- Interfaces e contratos expostos.
- Testes associados.

Não liste todos os arquivos indiscriminadamente. Priorize os pontos de entrada, os componentes centrais e as relações que realmente ajudam a navegar no código.

Se o projeto for muito grande, divida a documentação por domínio ou módulo e mantenha um índice central conciso.

Não invente relações entre arquivos. Confirme-as por meio do código, das configurações ou dos testes.

## 4. Criar um sistema de memória técnica persistente

Crie `docs/agent-memory.md` ou adapte uma solução equivalente que já exista.

A memória deve registrar apenas informações relevantes para a continuidade do desenvolvimento:

- Estado atual de funcionalidades importantes.
- Decisões técnicas vigentes.
- Contratos que não podem ser quebrados.
- Problemas conhecidos e evidências.
- Tentativas de solução que já falharam, quando isso evitar retrabalho.
- Testes executados e pendências relevantes.
- Próximos passos de trabalhos incompletos.
- Referências para arquivos e documentos que contêm os detalhes.

Estabeleça regras para manter a memória pequena, precisa e atualizada.

Não transforme a memória em um histórico completo da conversa, um diário de comandos ou uma cópia do código-fonte.

Quando uma informação deixar de ser válida, atualize-a ou remova-a. Diferencie claramente fatos verificados, hipóteses e tarefas pendentes.

O código atual, os testes e os contratos implementados são as fontes de verdade. A memória nunca deve prevalecer sobre evidências verificáveis do repositório.

## 5. Documentar decisões arquiteturais

Crie um diretório de decisões técnicas, preferencialmente `docs/decisions/`, caso ainda não exista uma solução equivalente.

Utilize registros curtos no formato ADR quando uma decisão for suficientemente importante.

Cada registro deve conter:

- Contexto.
- Decisão tomada.
- Justificativa.
- Alternativas consideradas, quando relevantes.
- Consequências e módulos afetados.

Não crie ADRs para cada alteração pequena. Registre decisões que afetem arquitetura, segurança, persistência, contratos, dependências ou manutenção futura.

Nunca invente decisões históricas. Se o motivo original não puder ser comprovado, identifique-o como não documentado.

## 6. Configurar regras específicas por tecnologia

Identifique as tecnologias realmente utilizadas e crie regras especializadas apenas quando forem úteis.

Considere, conforme o projeto:

- Frontend e componentes.
- Backend e APIs.
- Banco de dados e migrations.
- Testes.
- Segurança e autenticação.
- Infraestrutura e deploy.

Utilize ativação por diretório, seleção manual ou decisão do agente, conforme os recursos oficialmente suportados.

As regras especializadas devem ser carregadas somente quando relevantes à tarefa, quando o ambiente permitir esse comportamento.

Não copie as regras globais para cada arquivo especializado.

Cada regra deve conter orientações curtas, verificáveis e relacionadas ao seu domínio.

## 7. Criar Skills reutilizáveis

Se o ambiente suportar Skills, crie inicialmente apenas as seguintes:

### `impact-analysis`

Procedimento para:

- Identificar arquivos envolvidos.
- Rastrear dependências e consumidores.
- Inspecionar contratos e interfaces.
- Estimar o impacto das mudanças.
- Identificar testes necessários.
- Evitar leituras desnecessárias sem ignorar dependências críticas.

### `debug-systematically`

Procedimento para:

- Reproduzir o problema.
- Coletar evidências.
- Localizar a causa raiz.
- Evitar correções especulativas.
- Aplicar a menor correção adequada.
- Validar a solução com testes.

### `finish-task`

Procedimento para:

- Revisar o diff.
- Verificar efeitos colaterais.
- Executar as validações pertinentes.
- Atualizar a memória quando necessário.
- Registrar pendências e resultados reais.

### `safe-database-change`

Crie somente se o projeto possuir persistência ou alterações de schema relevantes.

O procedimento deve avaliar migrations, integridade referencial, constraints, índices, transações, compatibilidade e riscos de operações destrutivas.

Siga o formato e a localização oficialmente suportados pelo Antigravity. Não crie Skills decorativas ou arquivos que o agente não consiga descobrir ou utilizar.

## 8. Preservar as relações entre arquivos

Essa é uma das partes mais importantes da tarefa.

O sistema deve orientar o agente a rastrear as dependências relevantes antes de alterar um arquivo.

Para cada tarefa, o agente deve:

1. Identificar o ponto de entrada.
2. Localizar a implementação envolvida.
3. Verificar quem chama ou importa essa implementação.
4. Verificar contratos, tipos, interfaces e dados compartilhados.
5. Identificar testes e configurações afetados.
6. Expandir a investigação quando surgirem novas dependências relevantes.
7. Resumir o impacto encontrado antes de implementar alterações arriscadas.

Utilize os mecanismos já disponíveis no projeto, como ferramentas de busca, referências da IDE, compilador, testes, análise estática e ferramentas de navegação de código.

Não crie um grafo de dependências manual e gigantesco se ele puder ser derivado do código.

Se um índice automatizado for útil, prefira uma solução determinística, leve e regenerável. Não introduza serviços, bancos de dados ou dependências pesadas apenas para documentar relações que podem ser obtidas de forma mais simples.

## 9. Otimizar o consumo de tokens

Projete o sistema para minimizar o contexto desnecessário.

Adote os seguintes princípios:

- Carregar instruções globais pequenas.
- Consultar documentação especializada sob demanda.
- Ler primeiro os arquivos diretamente envolvidos.
- Expandir a leitura quando houver dependências importantes.
- Evitar repetir informações em múltiplos documentos.
- Evitar despejar arquivos inteiros, logs extensos e resultados de comandos irrelevantes.
- Preferir resumos com referências para a fonte original.
- Dividir tarefas grandes em etapas verificáveis.
- Não reler toda a memória em cada tarefa se apenas parte dela for pertinente.
- Não gerar documentação automática sem utilidade prática.
- Não sacrificar a precisão apenas para reduzir o número de arquivos lidos.

Não prometa uma redução percentual de tokens sem medições reais.

## 10. Criar um protocolo de início e encerramento de tarefas

Documente o seguinte fluxo de trabalho para o agente.

### Ao iniciar uma tarefa

1. Ler as instruções aplicáveis.
2. Consultar a memória técnica relevante.
3. Identificar o objetivo e os critérios de conclusão.
4. Investigar os arquivos e dependências necessários.
5. Confirmar as restrições e os contratos que devem ser preservados.
6. Implementar a solução com o menor escopo adequado.

### Ao encerrar uma tarefa

1. Revisar as alterações realizadas.
2. Executar os testes pertinentes.
3. Registrar os resultados reais.
4. Atualizar a documentação arquitetural caso necessário.
5. Atualizar a memória somente quando houver informação duradoura ou uma pendência importante.
6. Informar os arquivos alterados, as validações realizadas e os riscos restantes.

Evite obrigar o agente a executar todos os passos de forma extensa em tarefas triviais. O rigor deve ser proporcional ao impacto e ao risco.

## 11. Segurança e preservação do repositório

Durante toda a implementação:

- Não altere a lógica de negócio da aplicação.
- Não modifique APIs públicas sem necessidade.
- Não exclua instruções existentes sem avaliar seu conteúdo.
- Não substitua configurações válidas por exemplos genéricos.
- Não execute operações destrutivas.
- Não faça commits ou push sem solicitação.
- Não registre segredos, tokens, credenciais ou dados pessoais na documentação.
- Não adicione dependências apenas por conveniência.
- Não marque verificações como concluídas se não tiver executado as respectivas validações.

Antes de terminar, confira o estado do Git e garanta que as mudanças se limitem à infraestrutura documental e de contexto solicitada.

## 12. Validação final obrigatória

Depois da implementação:

1. Verifique se os arquivos criados estão nos caminhos corretos.
2. Confirme se as regras e Skills seguem os formatos realmente aceitos pelo ambiente.
3. Verifique se não existem instruções duplicadas ou contraditórias.
4. Confira se os caminhos e relações documentados existem no repositório.
5. Verifique se a memória não contém afirmações inventadas.
6. Confirme se a documentação explica como encontrar dependências sem exigir a leitura integral do projeto.
7. Execute as validações apropriadas para os arquivos modificados.
8. Apresente um resumo final com:
   - Arquivos criados e modificados.
   - Estrutura implementada.
   - Mecanismos de economia de contexto utilizados.
   - Como o agente deverá usar a memória e as regras.
   - Validações realizadas e seus resultados.
   - Limitações identificadas.
   - Melhorias futuras que realmente valham a pena.

## Critério de sucesso

A implementação será considerada concluída quando o projeto tiver uma estrutura de contexto coerente, concisa, verificável e utilizável pelo Antigravity, capaz de ajudar o agente a encontrar as informações certas, preservar as relações entre arquivos, retomar decisões importantes e reduzir leituras redundantes sem prejudicar a qualidade das alterações.

Comece analisando o repositório real. Adapte a solução à arquitetura existente e implemente somente o que trouxer benefício comprovável. Não se limite a apresentar um plano: realize as alterações documentais e de configuração necessárias, respeitando as restrições acima.
