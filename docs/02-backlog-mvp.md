# 02. Backlog do MVP | Gestão de Solicitações de Manutenção

## 1. Objetivo

Este documento reúne as histórias de usuário do MVP, com prioridades, critérios de aceitação, regras de negócio e dependências.

A priorização utiliza o método MoSCoW:

- **Must have:** essencial para o funcionamento do MVP.
- **Should have:** importante, mas pode ser adiado.
- **Could have:** melhoria desejável.
- **Won't have now:** fora do escopo inicial.

As prioridades são propostas e deverão ser validadas com o Product Owner (PO).

## 2. Premissas

- **P01:** os funcionários serão identificados individualmente.
- **P02:** as unidades da Vértice estarão cadastradas.
- **P03:** o acesso será controlado conforme os perfis autorizados.
- **P04:** classificação e prioridade serão definidas durante a triagem.
- **P05:** o MVP será acessível por uma interface web, sem aplicativo móvel nativo.
- **P06:** o histórico preservará as movimentações relevantes.
- **P07:** notificações automáticas e integrações não serão necessárias na primeira versão.

## 3. Épico 1 — Registro de solicitações

### US01 — Registrar uma solicitação

**Prioridade:** Must have

**História:** Como solicitante, quero registrar uma solicitação de manutenção para formalizar e acompanhar minha necessidade.

**Critérios de aceitação:**

- O usuário autorizado consegue preencher e enviar a solicitação.
- Os campos obrigatórios são validados antes do envio.
- A descrição do problema, o solicitante e a unidade são registrados.
- O sistema gera um identificador único e registra a data de abertura.
- A solicitação recebe o status inicial **Aberta**.
- Após o registro, o sistema apresenta uma confirmação com o identificador.
- Dados ausentes ou inválidos impedem o envio e são indicados ao usuário.

**Regras relacionadas:** RN01, RN02, RN03, RN04 e RN05.

**Dependências:** identificação do usuário e definição dos campos obrigatórios.

### US02 — Consultar minhas solicitações

**Prioridade:** Must have

**História:** Como solicitante, quero consultar minhas solicitações para acompanhar seu andamento.

**Critérios de aceitação:**

- O usuário visualiza apenas solicitações permitidas pelo seu perfil.
- A lista apresenta identificador, descrição resumida, data de abertura e status.
- É possível abrir os detalhes e localizar uma solicitação pelo identificador.
- O acesso respeita as permissões definidas.

**Regras relacionadas:** RN01, RN02 e RN05.

**Dependências:** US01 e definição das permissões de consulta.

### US03 — Complementar uma solicitação

**Prioridade:** Must have

**História:** Como solicitante, quero complementar uma solicitação quando forem necessárias informações adicionais.

**Critérios de aceitação:**

- O solicitante consegue consultar a solicitação pendente de informações.
- O sistema informa que existe uma complementação necessária, conforme a regra de comunicação definida.
- É possível registrar as informações solicitadas sem perder os dados anteriores.
- A complementação registra data, autor e movimentação no histórico.
- Após a complementação, a solicitação retorna à análise.

**Regras relacionadas:** RN08 e RN09.

**Dependências:** US01, US04 e definição do retorno à triagem.

## 4. Épico 2 — Triagem e direcionamento

### US04 — Analisar uma solicitação

**Prioridade:** Must have

**História:** Como responsável pela triagem, quero analisar as solicitações para verificar se possuem informações suficientes e definir o encaminhamento.

**Critérios de aceitação:**

- O responsável autorizado consulta as solicitações aguardando triagem e seus detalhes.
- É possível indicar se as informações são suficientes.
- Quando faltarem informações, é possível solicitar complementação.
- O status é atualizado conforme a decisão.
- A decisão, o responsável e a data são registrados no histórico.
- O sistema impede transições de status não permitidas.

**Regras relacionadas:** RN05, RN08 e RN09.

**Dependências:** US01 e definição do fluxo de triagem.

### US05 — Classificar e priorizar uma solicitação

**Prioridade:** Must have

**História:** Como responsável pela triagem, quero classificar e priorizar as solicitações para organizar os atendimentos.

**Critérios de aceitação:**

- O responsável seleciona uma categoria e uma prioridade configuradas.
- As categorias e prioridades seguem critérios definidos pelo PO.
- O sistema registra quem definiu ou alterou esses dados.
- A classificação e a prioridade ficam disponíveis nos detalhes.
- Alterações são registradas no histórico.
- Não é presumida classificação automática.

**Regras relacionadas:** RN06 e RN08.

**Dependências:** US04 e validação dos critérios de classificação e prioridade.

### US06 — Direcionar uma solicitação

**Prioridade:** Must have

**História:** Como responsável pela triagem, quero atribuir uma solicitação a uma pessoa ou equipe para definir quem realizará o atendimento.

**Critérios de aceitação:**

- É possível atribuir a solicitação a um responsável ou equipe autorizada.
- O sistema registra a atribuição e sua data.
- O status é atualizado conforme o direcionamento.
- O responsável atual fica visível nos detalhes.
- Novas atribuições preservam o histórico anterior.
- Quando houver controle de cadastro, responsáveis inexistentes ou inativos não poderão ser selecionados.
- É possível identificar solicitações não atribuídas.

**Regras relacionadas:** RN05, RN06 e RN08.

**Dependências:** US04, US05 e definição das equipes e dos responsáveis.

## 5. Épico 3 — Execução do atendimento

### US07 — Consultar a fila de atendimentos

**Prioridade:** Must have

**História:** Como responsável pelo atendimento, quero consultar as solicitações atribuídas a mim ou à minha equipe para organizar os serviços.

**Critérios de aceitação:**

- O responsável visualiza as solicitações sob sua responsabilidade.
- A lista apresenta identificador, descrição resumida, prioridade, data e status.
- É possível consultar os detalhes e identificar solicitações ainda não iniciadas.
- O acesso respeita as permissões do perfil.

**Regras relacionadas:** RN05 e RN06.

**Dependências:** US06 e definição das permissões de consulta.

### US08 — Atualizar o andamento do atendimento

**Prioridade:** Must have

**História:** Como responsável pelo atendimento, quero atualizar o status e registrar observações para manter o andamento da solicitação atualizado.

**Critérios de aceitação:**

- O responsável autorizado consegue iniciar o atendimento.
- Mudanças de status registram autor e data.
- É possível registrar observações e descrever impedimentos.
- As transições respeitam as regras definidas.
- O histórico preserva as movimentações anteriores.
- Uma observação, isoladamente, não conclui a solicitação.

**Regras relacionadas:** RN05 e RN08.

**Dependências:** US06 e definição das transições de status.

### US09 — Concluir uma solicitação

**Prioridade:** Must have

**História:** Como responsável pelo atendimento, quero registrar a conclusão do serviço para formalizar o resultado da manutenção.

**Critérios de aceitação:**

- Somente perfis autorizados podem concluir solicitações.
- É obrigatório registrar o serviço realizado ou a solução aplicada.
- O sistema registra data, responsável e status **Concluída**.
- A conclusão fica disponível nos detalhes e no histórico.
- A reabertura depende de uma regra específica autorizada.

**Regras relacionadas:** RN05, RN07, RN08 e RN10.

**Dependências:** US08 e definição das regras de conclusão.

## 6. Épico 4 — Histórico e gestão

### US10 — Consultar o histórico da solicitação

**Prioridade:** Must have

**História:** Como usuário autorizado, quero consultar o histórico para compreender as movimentações e o resultado do atendimento.

**Critérios de aceitação:**

- O sistema apresenta as movimentações registradas.
- Cada movimentação exibe, quando aplicável, data, autor, tipo de ação e descrição.
- O histórico permite identificar mudanças de status, atribuições, complementações e conclusão.
- Novas movimentações não apagam as anteriores.
- A consulta respeita as permissões do usuário.

**Regras relacionadas:** RN08.

**Dependências:** registro de histórico nas demais funcionalidades.

### US11 — Consultar solicitações para acompanhamento gerencial

**Prioridade:** Should have

**História:** Como gestor, quero consultar solicitações e seus status para acompanhar os atendimentos e identificar demandas pendentes.

**Critérios de aceitação:**

- O gestor consulta solicitações dentro do seu escopo de acesso.
- É possível filtrar por status.
- Filtros por unidade e período poderão ser incluídos conforme validação do PO.
- A lista apresenta registros compatíveis com os filtros.
- O gestor acessa detalhes e histórico conforme suas permissões.
- Perfis somente de leitura não podem alterar dados.

**Regras relacionadas:** RN03, RN05 e RN08.

**Dependências:** US01, US02 e US10.

## 7. Épico 5 — Acesso e integridade

### US12 — Controlar o acesso às funcionalidades

**Prioridade:** Must have

**História:** Como administrador, quero controlar o acesso às funcionalidades para garantir que cada usuário execute apenas ações autorizadas.

**Critérios de aceitação:**

- O sistema identifica o usuário antes de liberar funcionalidades protegidas.
- Registro, triagem, atribuição, atendimento, conclusão e consulta respeitam as permissões.
- Usuários sem autorização não conseguem executar ações restritas.
- O sistema apresenta uma resposta adequada em caso de acesso negado.
- Os perfis e as permissões seguem as definições aprovadas pelo PO.

**Regras relacionadas:** RN10 e regras de acesso a validar.

**Dependências:** definição dos perfis e das permissões.

## 8. Itens fora do MVP

- Notificações automáticas por e-mail ou aplicativo.
- Aplicativo móvel nativo.
- Integrações com compras, estoque ou gestão financeira.
- Gestão de contratos e fornecedores.
- Agendamento automático de equipes.
- Indicadores avançados e relatórios complexos.
- Priorização automática por regras ou inteligência artificial.
- Upload de fotografias e anexos, até validação da necessidade.

## 9. Ordem sugerida de implementação

1. Definir usuários, perfis e permissões.
2. Definir cadastros de unidades, categorias, responsáveis e prioridades.
3. Implementar registro e consulta de solicitações.
4. Implementar triagem, complementação, classificação e direcionamento.
5. Implementar atendimento, observações e conclusão.
6. Garantir o registro e a consulta do histórico.
7. Implementar a consulta gerencial, conforme prioridade aprovada.

A sequência é uma sugestão funcional e deverá considerar a capacidade da equipe, os riscos técnicos e as prioridades do PO.

## 10. Definição de pronto

Uma história será considerada pronta quando:

- Seus critérios de aceitação forem atendidos.
- Os cenários aplicáveis forem testados.
- As regras de negócio e as permissões forem respeitadas.
- Os registros e o histórico estiverem consistentes, quando aplicável.
- A documentação estiver atualizada.
- A funcionalidade tiver sido validada pelos responsáveis definidos.

Esta definição é uma proposta e deverá ser alinhada ao processo de desenvolvimento da equipe.

## 11. Relação com os demais artefatos

- [Modelagem do processo](01-modelagem-processo.md)
- [Validações com o Product Owner](03-validacoes-product-owner.md)
- [Modelagem de dados](04-modelagem-dados.md)

