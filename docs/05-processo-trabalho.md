# 05. Processo de Trabalho | Análise do Desafio

## 1. Abordagem utilizada

A análise foi conduzida a partir do contexto e dos requisitos apresentados no desafio técnico, buscando transformar um problema operacional em uma proposta funcional de MVP.

O trabalho foi organizado em cinco etapas:

1. Compreensão do problema e dos objetivos de negócio.
2. Identificação dos participantes e do fluxo operacional.
3. Definição das funcionalidades indispensáveis e priorização do backlog.
4. Identificação das lacunas e das decisões que precisam de validação.
5. Modelagem dos dados necessários para suportar o processo.

Essa sequência permitiu estabelecer uma relação entre a necessidade de negócio, o processo proposto, as histórias de usuário e a estrutura de dados.

## 2. Do problema ao backlog

O cenário apresentado indica que as solicitações de manutenção são registradas por diferentes canais, dificultando o acompanhamento, a priorização e a consulta ao histórico.

A partir desse problema, foram identificadas quatro necessidades principais:

- Centralizar o registro das solicitações.
- Organizar a análise e o direcionamento.
- Acompanhar o atendimento até a conclusão.
- Preservar o histórico e oferecer visibilidade gerencial.

Essas necessidades foram traduzidas em etapas de processo e agrupadas em funcionalidades. Em seguida, foram escritas histórias de usuário com critérios de aceitação verificáveis.

A priorização considerou o funcionamento de ponta a ponta. Por esse motivo, registro, triagem, atribuição, atendimento, conclusão e histórico foram tratados como componentes essenciais do MVP.

Consultas gerenciais básicas foram consideradas importantes, enquanto notificações automáticas, integrações e análises avançadas foram mantidas fora do escopo inicial.

## 3. Premissas adotadas

O desafio não define todos os detalhes operacionais da Vértice. Para evitar interromper a análise diante de cada lacuna, foram adotadas premissas explícitas.

As principais foram:

- O solicitante é um funcionário identificado.
- Cada solicitação está vinculada a uma unidade.
- A descrição do problema é obrigatória.
- Existe um responsável autorizado a realizar a triagem.
- A prioridade é definida durante a triagem, sem automação inicialmente.
- Solicitações podem aguardar complementação sem perder seu registro.
- A atribuição e as mudanças de status devem ser rastreáveis.
- A conclusão exige o registro da solução aplicada.
- Os perfis de acesso serão definidos antes da implementação.
- O MVP não depende de integrações externas ou notificações automáticas.

As premissas foram utilizadas para permitir a elaboração da proposta, mas não foram tratadas como regras confirmadas da empresa.

## 4. Definição do escopo do MVP

O escopo foi delimitado considerando o menor conjunto coerente de funcionalidades capaz de resolver o problema central apresentado.

A solução precisa permitir que uma solicitação seja registrada, analisada, direcionada, atendida, concluída e consultada posteriormente.

Funcionalidades que não são necessárias para completar esse fluxo foram adiadas. Essa decisão reduz a complexidade inicial e permite que o produto seja validado antes de receber recursos adicionais.

O escopo também evita propor automações sem regras de negócio conhecidas, como priorização automática, distribuição inteligente de equipes ou notificações com canais ainda não definidos.

## 5. Coerência entre os artefatos

Os artefatos foram elaborados considerando a seguinte relação:

- **Processo BPMN:** representa as etapas, os participantes e as decisões.
- **Backlog:** descreve o comportamento esperado em histórias de usuário e critérios de aceitação.
- **Validações com o Product Owner:** identifica lacunas, premissas e decisões que podem alterar a solução.
- **Modelo de dados:** define as informações necessárias para registrar e acompanhar o processo.
- **README:** apresenta a proposta, delimita o escopo e orienta a avaliação.

A consistência entre esses documentos é importante para reduzir ambiguidades e facilitar a comunicação entre negócio, desenvolvimento e qualidade.

## 6. O que faria em um projeto real

Com acesso aos stakeholders, aprofundaria a descoberta antes de consolidar a especificação.

### Entrevistas e levantamento do processo atual

Conversaria com solicitantes, equipe de manutenção, responsáveis pela triagem e gestores para compreender como as demandas são abertas, priorizadas, atribuídas e concluídas atualmente.

Também investigaria exceções recorrentes, retrabalho, atrasos, solicitações duplicadas e dificuldades de comunicação.

### Validação das necessidades

Confirmaria quais problemas têm maior impacto operacional e quais informações são realmente necessárias no registro. Procuraria distinguir necessidades dos usuários de soluções sugeridas durante as entrevistas.

### Modelagem e validação conjunta

Apresentaria o fluxo proposto aos envolvidos para confirmar participantes, decisões, responsabilidades e exceções. Validaria também os status, as permissões e as regras de transição.

### Refinamento do backlog

Revisaria as histórias com o Product Owner e a equipe técnica, esclarecendo dependências, critérios de aceitação, regras de negócio e cenários alternativos.

### Protótipo e testes de entendimento

Quando útil, criaria wireframes das telas principais para validar a experiência de registro, consulta e acompanhamento antes da implementação.

### Requisitos não funcionais

Levantaria requisitos de segurança, desempenho, disponibilidade, acessibilidade, privacidade, auditoria e integração com outros sistemas.

### Validação incremental

Planejaria a validação das funcionalidades por etapas, com participação dos usuários e critérios objetivos de aceite, incorporando feedback antes de expandir o escopo.

## 7. Limitações da proposta

Esta entrega foi construída a partir das informações disponibilizadas no enunciado. Não foram realizadas entrevistas com usuários reais, validações com o Product Owner ou análises de sistemas existentes da Vértice.

Por isso, os fluxos, os status, as prioridades e a estrutura de dados representam uma proposta inicial, sujeita a refinamento.

O objetivo é apresentar uma solução funcionalmente coerente, com escopo delimitado e requisitos que possam orientar o desenvolvimento e os testes.

## 8. Utilização de Inteligência Artificial

Utilizei ferramentas de inteligência artificial como apoio durante a análise e a elaboração da documentação, auxiliando na organização das informações, no refinamento dos requisitos, na revisão da clareza dos critérios de aceitação e na verificação da consistência entre os artefatos.

As decisões sobre o escopo do MVP, as premissas adotadas, a estrutura do processo e a proposta de modelagem foram avaliadas criticamente ao longo do trabalho. As sugestões geradas foram revisadas e ajustadas conforme o contexto do desafio, mantendo como objetivo a coerência entre as necessidades do negócio, o backlog, o BPMN e o modelo de dados.

Em um projeto real, utilizaria a IA como ferramenta complementar, sem substituir o levantamento com stakeholders, a validação dos requisitos com o Product Owner ou a responsabilidade do analista sobre as especificações entregues.
