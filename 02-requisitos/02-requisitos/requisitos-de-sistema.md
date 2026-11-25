# Requisitos de Sistema (RS)

Os requisitos de sistema detalham os serviços e comportamentos necessários para atender aos requisitos de usuário.

| ID | Descrição | Deriva de |
|---|---|---|
| RS01 | Autenticar usuários por e-mail e senha, manter sessão com tempo limite de inatividade e permitir encerramento seguro. | RU01 |
| RS02 | Validar e armazenar dados do leitor, impedindo duplicidade de e-mails. | RU02 |
| RS03 | Oferecer busca por múltiplos critérios e exibir disponibilidade em tempo real. | RU03 |
| RS04 | Registrar empréstimos, devoluções e renovações, aplicando as regras de negócio. | RU04 |
| RS05 | Gerenciar fila de reservas por obra e enviar notificações. | RU05 |
| RS06 | Permitir cadastro, consulta, edição e exclusão de obras e exemplares, restritos a perfis autorizados. | RU06 |
| RS07 | Exibir ao leitor autenticado o histórico de seus empréstimos, reservas e pendências. | RU07 |
| RS08 | Identificar empréstimos vencidos e aplicar a penalidade prevista na RN04. | RU08 |
| RS09 | Permitir criação, edição e desativação de contas com atribuição de perfil. | RU09 |
| RS10 | Gerar relatórios de obras mais emprestadas, atrasos e movimentação mensal, com filtro por período. | RU10 |

## Template

| ID | Comportamento do sistema | Entradas/condições | Resultado esperado | Deriva de (RU) | Regras relacionadas |
|---|---|---|---|---|---|
| RSXX | O sistema deverá [comportamento]. | [Condições] | [Resultado verificável] | [RUXX] | [RNXX] |
