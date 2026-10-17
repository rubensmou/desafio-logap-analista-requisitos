# 03. Pontos para Validação com o Product Owner

## 1. Objetivo

Este documento reúne as principais decisões que precisam ser discutidas com o Product Owner antes ou durante o desenvolvimento do MVP de gestão de solicitações de manutenção da Vértice.

As perguntas foram identificadas a partir das lacunas do cenário apresentado. As propostas registradas nos demais artefatos são premissas de trabalho, não decisões confirmadas pela empresa.

## 2. Pontos prioritários de validação

### VP01 — Quem pode registrar solicitações?

**Pergunta:** Todos os funcionários podem registrar solicitações? Existem restrições por unidade, departamento ou perfil?

**Por que validar:** A resposta define quem terá acesso ao registro e quais informações de identificação precisam ser mantidas.

**Impactos:** Histórias US01, US02 e US12; controle de acesso; entidade Usuário; regras de consulta.

**Premissa adotada:** O solicitante é um funcionário identificado e autorizado.

### VP02 — Quais campos são obrigatórios no registro?

**Pergunta:** Além da descrição, da unidade e do solicitante, quais informações devem ser obrigatórias? Categoria, local, equipamento, nível de urgência, contato ou anexos são necessários?

**Por que validar:** Campos insuficientes podem dificultar a triagem. Campos excessivos podem tornar o registro lento e prejudicar a adesão.

**Impactos:** US01, modelo de dados, validações de formulário e experiência do usuário.

**Premissa adotada:** O MVP exige identificação do solicitante, unidade, descrição e data de abertura.

### VP03 — Como as unidades e os locais serão identificados?

**Pergunta:** As unidades já possuem cadastro corporativo? Será necessário cadastrar prédios, setores, salas, equipamentos ou outros ativos individualmente?

**Por que validar:** A estrutura influencia o formulário de abertura, a classificação das solicitações e os relacionamentos do modelo de dados.

**Impactos:** US01, US05, entidade Unidade e eventual criação de entidades Local ou Ativo.

**Premissa adotada:** Cada solicitação está associada a uma unidade. A identificação detalhada de ativos dependerá da necessidade operacional.

### VP04 — Quais categorias de manutenção serão utilizadas?

**Pergunta:** Quais categorias devem existir, por exemplo, elétrica, hidráulica, mobiliário, equipamentos e infraestrutura? Quem poderá alterá-las?

**Por que validar:** A classificação precisa ser consistente para orientar a triagem e facilitar consultas posteriores.

**Impactos:** US05, modelo de dados, cadastros e filtros.

**Premissa adotada:** As categorias serão definidas ou configuradas conforme uma lista validada pelo Product Owner.

### VP05 — Como a prioridade será definida?

**Pergunta:** A prioridade será manual ou calculada com base em urgência, impacto, risco ou quantidade de pessoas afetadas? Quais níveis serão utilizados?

**Por que validar:** A prioridade influencia a ordem de atendimento e pode gerar conflitos se os critérios não forem claros.

**Impactos:** US05, US06, fluxo de triagem, regras de negócio e possíveis indicadores.

**Premissa adotada:** A prioridade será atribuída durante a triagem. Não foi proposta priorização automática porque o cenário não fornece critérios para isso.

### VP06 — Quem realiza a triagem e o direcionamento?

**Pergunta:** Existe uma equipe central de manutenção ou cada unidade possui seus próprios responsáveis? Quem pode classificar, priorizar e atribuir solicitações?

**Por que validar:** A organização do trabalho determina as raias do processo, os perfis e as regras de atribuição.

**Impactos:** US04, US05, US06 e US12; fluxo BPMN; entidades Usuário e Equipe.

**Premissa adotada:** Um responsável autorizado realiza a triagem e direciona a solicitação.

### VP07 — Quais status e transições são permitidos?

**Pergunta:** Quais estados devem existir? Uma solicitação pode voltar para triagem, ser suspensa, rejeitada, cancelada ou reaberta após a conclusão?

**Por que validar:** O fluxo de status precisa refletir a operação real e impedir encerramentos ou mudanças inconsistentes.

**Impactos:** US03, US04, US08, US09 e US10; BPMN; regras de transição.

**Premissa adotada:** O MVP utiliza os status propostos no documento de processo, sujeitos a confirmação.

### VP08 — Como será tratada a falta de informações?

**Pergunta:** Quem solicita a complementação? O solicitante recebe alguma comunicação? Existe prazo para responder? O que ocorre se não houver resposta?

**Por que validar:** A ausência de regras pode deixar solicitações paradas indefinidamente ou gerar encerramentos inadequados.

**Impactos:** US03, US04, status “Pendente de informações” e histórico.

**Premissa adotada:** A solicitação permanece registrada e pode ser complementada pelo solicitante.

### VP09 — Como será feita a atribuição de responsáveis?

**Pergunta:** A solicitação será atribuída a uma equipe, a uma pessoa ou a ambos? Uma pessoa poderá redistribuir o atendimento?

**Por que validar:** A atribuição influencia a fila de trabalho, as permissões e a rastreabilidade.

**Impactos:** US06, US07, US08, entidades Equipe e Usuário e histórico.

**Premissa adotada:** O sistema registra um responsável ou equipe atual e preserva as alterações de atribuição.

### VP10 — Quais informações são necessárias para concluir um atendimento?

**Pergunta:** É suficiente registrar uma descrição do serviço realizado? São necessários materiais utilizados, tempo de execução, evidências, aprovação do solicitante ou validação de um gestor?

**Por que validar:** Os dados de conclusão definem o que será considerado um atendimento encerrado e a qualidade do histórico.

**Impactos:** US09, US10 e modelo de dados.

**Premissa adotada:** A conclusão exige a descrição da solução aplicada, o responsável e a data.

### VP11 — Quem pode consultar as solicitações e o histórico?

**Pergunta:** O solicitante visualiza apenas suas próprias solicitações? Gestores podem consultar todas as solicitações da unidade? A equipe de manutenção pode consultar demandas de outras unidades?

**Por que validar:** A visibilidade deve equilibrar transparência operacional e restrição de acesso.

**Impactos:** US02, US07, US10, US11 e US12; filtros e regras de autorização.

**Premissa adotada:** A consulta respeita as permissões definidas para cada perfil.

### VP12 — Quais consultas gerenciais são necessárias no MVP?

**Pergunta:** Quais informações os gestores precisam acompanhar? Quantidade por status, unidade, prioridade, período ou tempo de atendimento são suficientes?

**Por que validar:** A necessidade gerencial pode variar entre uma listagem simples e um módulo de relatórios mais complexo.

**Impactos:** US11, filtros, modelo de dados e priorização do escopo.

**Premissa adotada:** O MVP oferece consulta de solicitações com filtros básicos, sem painéis analíticos avançados.

### VP13 — Quais notificações são necessárias?

**Pergunta:** O sistema precisa avisar o solicitante sobre o registro, a complementação, a atribuição ou a conclusão? Qual canal deve ser utilizado?

**Por que validar:** Notificações afetam arquitetura, integrações, custos operacionais e critérios de aceite.

**Impactos:** US03, US06, US09 e requisitos não funcionais.

**Premissa adotada:** As notificações automáticas ficam fora do escopo inicial, podendo ser avaliadas posteriormente.

### VP14 — Como será feito o controle de duplicidade e a reabertura?

**Pergunta:** Como tratar solicitações repetidas para o mesmo problema? Uma solicitação concluída poderá ser reaberta? Quem terá autorização?

**Por que validar:** Essas situações afetam a integridade do histórico e a contagem de atendimentos.

**Impactos:** US01, US09 e US10; regras de negócio e modelo de dados.

**Premissa adotada:** O sistema registra cada solicitação individualmente. Detecção automática de duplicidade e reabertura dependem de regras específicas ainda não definidas.

### VP15 — Existem requisitos não funcionais ou integrações obrigatórias?

**Pergunta:** Há requisitos de segurança, disponibilidade, acessibilidade, desempenho, retenção de dados ou integração com sistemas de autenticação, cadastro ou gestão de ativos?

**Por que validar:** Requisitos não funcionais e integrações podem afetar arquitetura, prazo, custo e viabilidade do MVP.

**Impactos:** US12, arquitetura da solução, modelo de dados e planejamento técnico.

**Premissa adotada:** A proposta se concentra nos requisitos funcionais. Os requisitos não funcionais deverão ser levantados antes do desenvolvimento.

## 3. Premissas adotadas para elaborar a proposta

As premissas abaixo foram utilizadas para permitir que o fluxo e o backlog fossem definidos mesmo sem acesso aos stakeholders:

- PA01: o solicitante é um funcionário identificado e autorizado.
- PA02: a solicitação está vinculada a uma unidade da Vértice.
- PA03: a descrição do problema é obrigatória.
- PA04: existe um responsável autorizado a realizar a triagem.
- PA05: a classificação e a prioridade são definidas durante a triagem.
- PA06: uma solicitação pode aguardar complementação sem perder o registro original.
- PA07: o atendimento é atribuído a uma pessoa ou equipe identificada.
- PA08: a conclusão exige o registro do resultado do serviço.
- PA09: as mudanças relevantes devem permanecer consultáveis no histórico.
- PA10: o MVP não depende de notificações automáticas ou integrações externas para funcionar.
- PA11: os perfis e as permissões serão definidos antes da implementação.
- PA12: as consultas gerenciais serão limitadas às necessidades básicas de acompanhamento.

## 4. Estratégia de validação

Em um projeto real, eu priorizaria as perguntas que podem alterar a estrutura do processo, o escopo e o modelo de dados.

A validação poderia ser conduzida em três etapas:

1. **Descoberta:** entrevistas com solicitantes, responsáveis pela triagem, equipes de manutenção e gestores.
2. **Refinamento:** validação do fluxo, das regras de negócio, dos status, das permissões e dos critérios de aceitação.
3. **Confirmação do MVP:** priorização com o Product Owner, validação dos itens indispensáveis e registro das decisões tomadas.

As respostas seriam documentadas, as premissas confirmadas ou ajustadas e os artefatos atualizados antes do desenvolvimento das funcionalidades afetadas.
