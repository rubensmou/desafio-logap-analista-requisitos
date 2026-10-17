# 01. Modelagem do Processo | Gestão de Solicitações de Manutenção

## 1. Objetivo

Descrever o fluxo de registro, análise, direcionamento, execução e conclusão das solicitações de manutenção da Vértice.

A modelagem considera os participantes, as decisões, as regras de negócio e as principais exceções do MVP. Quando o cenário não define uma regra, ela é tratada como premissa a validar.

## 2. Participantes

| Participante | Responsabilidade |
|---|---|
| Solicitante | Registrar a solicitação e acompanhar seu andamento. |
| Sistema | Registrar os dados, controlar os status e manter o histórico. |
| Responsável pela triagem | Analisar, classificar, priorizar e direcionar as solicitações. |
| Responsável pelo atendimento | Executar o serviço e registrar o resultado. |
| Gestor | Consultar as solicitações e o histórico dos atendimentos. |
| Administrador do sistema | Gerenciar a associação de perfis aos usuários, conforme as permissões autorizadas. |

Os papéis são uma proposta funcional. Uma mesma pessoa poderá exercer mais de uma função, conforme a estrutura da empresa. As permissões de cada perfil deverão ser validadas com o Product Owner (PO).

## 3. Fluxo principal

1. O solicitante identifica uma necessidade de manutenção.
2. Registra a solicitação com a unidade, o local ou item afetado e a descrição do problema.
3. O sistema gera um identificador único, registra a data e define o status inicial.
4. A triagem analisa as informações recebidas.
5. Se faltarem informações, a solicitação retorna ao solicitante para complementação.
6. Com os dados suficientes, a solicitação é classificada e priorizada.
7. A triagem define o responsável ou a equipe de atendimento.
8. O responsável analisa e executa o serviço.
9. Durante o atendimento, registra observações e atualizações de status.
10. Se houver algum impedimento, registra o motivo e atualiza a situação.
11. Após a execução, registra a solução aplicada e conclui a solicitação.
12. O sistema mantém os dados e o histórico para consulta pelos perfis autorizados.

## 4. Decisões do processo

### D1. As informações são suficientes?

- **Sim:** a solicitação segue para classificação e priorização.
- **Não:** retorna ao solicitante para complementação.

**Premissa:** os dados já registrados devem ser preservados durante a complementação.

### D2. A solicitação pode ser direcionada?

- **Sim:** é atribuída a um responsável ou equipe.
- **Não:** permanece em triagem ou recebe o encaminhamento definido.

As regras para rejeição, cancelamento ou pendência deverão ser validadas com o PO.

### D3. O atendimento pode prosseguir?

- **Sim:** o responsável executa o serviço e atualiza o andamento.
- **Não:** registra o impedimento e mantém a solicitação em um status adequado.

As situações de espera por peças, dependência de terceiros e necessidade de aprovação precisam ser validadas.

### D4. O serviço foi concluído?

- **Sim:** o responsável registra o resultado e conclui a solicitação.
- **Não:** a solicitação permanece em atendimento ou em outro status permitido.

## 5. Status propostos para o MVP

| Status | Significado |
|---|---|
| Aberta | Solicitação registrada e aguardando análise. |
| Em triagem | Solicitação em análise e direcionamento. |
| Pendente de informações | Aguardando complementação do solicitante. |
| Atribuída | Responsável ou equipe definidos. |
| Em atendimento | Serviço em execução. |
| Concluída | Serviço realizado e resultado registrado. |
| Cancelada | Solicitação encerrada sem execução, conforme regra autorizada. |

Os status e as transições permitidas são propostas iniciais e deverão ser validados com o PO.

## 6. Regras de negócio

- **RN01:** cada solicitação deve possuir um identificador único.
- **RN02:** cada solicitação deve estar associada a um solicitante.
- **RN03:** cada solicitação deve identificar a unidade relacionada.
- **RN04:** a descrição deve permitir compreender o problema relatado.
- **RN05:** toda solicitação deve possuir um status.
- **RN06:** a classificação, a prioridade e o responsável devem ser registrados quando definidos.
- **RN07:** a conclusão deve conter o resultado do atendimento.
- **RN08:** as mudanças relevantes de status devem ser registradas no histórico.
- **RN09:** solicitações pendentes de informações devem permitir complementação sem perda dos dados anteriores.
- **RN10:** cancelamentos e outros encerramentos devem respeitar regras de autorização.
- **RN11:** o acesso às funcionalidades e aos dados deve respeitar as permissões associadas ao usuário. Ações não autorizadas devem ser bloqueadas sem alterar os dados ou o estado da solicitação.

## 7. Exceções e situações a considerar

- Solicitação com dados incompletos ou duplicados.
- Ausência de equipe disponível.
- Necessidade de informações adicionais.
- Falta de peças ou outros recursos.
- Cancelamento após o registro.
- Reabertura de solicitação concluída.
- Falha ao registrar uma atualização.
- Tentativa de acesso ou execução de ação sem a permissão necessária.
- Tentativa de alteração de dados por usuário inativo ou fora de seu escopo autorizado.

Essas situações exigem regras específicas antes da implementação. O tratamento de duplicidades, reaberturas e falhas ainda não está definido.

## 8. Relação com os demais artefatos

- [Backlog do MVP](02-backlog-mvp.md): histórias de usuário e critérios de aceitação.
- [Validações com o Product Owner](03-validacoes-product-owner.md): questões e regras pendentes de confirmação.
- [Modelagem de dados](04-modelagem-dados.md): entidades e relacionamentos da solução.

## 9. Diagrama BPMN

O diagrama deve representar o fluxo descrito neste documento, com raias para Solicitante, Sistema, Triagem e Responsável pelo Atendimento. O processo deve considerar a verificação de autorização pelo sistema antes da execução de ações protegidas. Quando o acesso for negado, a ação deve ser interrompida sem alteração do estado da solicitação. Essa verificação é transversal ao processo e não exige a repetição de um gateway em cada tarefa, desde que o controle esteja representado ou documentado de forma inequívoca.

Devem ser utilizados eventos de início e fim, tarefas, gateways exclusivos para decisões e fluxos de sequência.

O arquivo do diagrama deverá ser disponibilizado em `diagrams/processo-manutencao.bpmn` ou em outro formato acessível, com um link para visualização.


