# Requisitos de Software (RSW)

Os requisitos de software detalham componentes e implementações que orientam a construção do sistema.

| ID | Descrição | Deriva de |
|---|---|---|
| RSW01 | Implementar tela e serviço de autenticação, hash de senha e controle de sessão (criação, expiração e encerramento). | RS01 |
| RSW02 | Implementar formulário de cadastro, validação dos campos e verificação de e-mail existente no banco de dados. | RS02 |
| RSW03 | Implementar módulo de busca com índices nos campos título, autor, assunto e ISBN. | RS03 |
| RSW04 | Implementar módulo de circulação (empréstimo, devolução e renovação), verificando RN01 a RN05. | RS04 |
| RSW05 | Implementar rotina de reservas (fila e expiração em 48 horas) e envio de e-mails. | RS05 |
| RSW06 | Implementar telas e serviços de cadastro, edição e exclusão de obras, com controle de permissão. | RS06 |
| RSW07 | Implementar tela de histórico, filtrada pelo usuário autenticado. | RS07 |
| RSW08 | Implementar rotina diária para identificar empréstimos vencidos e registrar bloqueio de novos empréstimos conforme RN04. | RS08 |
| RSW09 | Implementar telas e serviços de gestão de contas, desativação lógica e controle de perfil. | RS09 |
| RSW10 | Implementar relatórios com consultas agregadas e filtro por período, restritos ao administrador. | RS10 |

## Template

| ID | Componente/implementação | Requisito de sistema | Regras/qualidade relacionadas | Verificação |
|---|---|---|---|---|
| RSWXX | Implementar [componente e comportamento]. | [RSXX] | [RNXX/RNFXX] | [Teste ou inspeção] |
