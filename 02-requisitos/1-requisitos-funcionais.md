# 2.1. Requisitos Funcionais

Os requisitos funcionais descrevem os serviços que o Templo das Páginas deverá oferecer. As prioridades foram mantidas conforme o documento de requisitos fornecido.

| ID | Nome | Descrição | Prioridade |
|---|---|---|---|
| RF01 | Realizar login | Permitir que usuários cadastrados acessem a aplicação por e-mail e senha. | Essencial |
| RF02 | Cadastrar leitor | Permitir o cadastro de novos leitores, registrando dados pessoais e de contato. | Essencial |
| RF03 | Encerrar sessão | Permitir que o usuário encerre sua sessão de forma segura. | Essencial |
| RF04 | Gerenciar acervo | Permitir que bibliotecários cadastrem, editem e removam obras e exemplares. | Essencial |
| RF05 | Pesquisar acervo | Buscar obras por título, autor, assunto ou ISBN e exibir a disponibilidade. | Essencial |
| RF06 | Realizar empréstimo | Registrar empréstimo de exemplar a leitor e informar a data prevista de devolução. | Essencial |
| RF07 | Registrar devolução | Registrar devolução de exemplares e atualizar a respectiva disponibilidade. | Essencial |
| RF08 | Renovar empréstimo | Permitir a renovação de empréstimos ativos, observadas as regras de negócio. | Importante |
| RF09 | Reservar obra | Permitir reserva de obras cujos exemplares estejam todos emprestados. | Importante |
| RF10 | Controlar atrasos | Identificar empréstimos em atraso e aplicar a penalidade prevista. | Importante |
| RF11 | Notificar leitor | Notificar por e-mail sobre vencimentos próximos e disponibilidade de obras reservadas. | Desejável |
| RF12 | Consultar histórico | Permitir ao leitor consultar seus empréstimos, reservas e pendências. | Importante |
| RF13 | Gerenciar usuários | Permitir ao administrador criar, editar e desativar contas de funcionários e leitores. | Importante |
| RF14 | Gerar relatórios | Gerar relatórios de obras mais emprestadas, atrasos e movimentação mensal. | Desejável |

## Template para novos requisitos

| ID | Nome | Descrição verificável | Prioridade | Critérios de aceitação | Caso de uso |
|---|---|---|---|---|---|
| RFXX | [Nome] | O sistema deverá [comportamento observável]. | [Essencial/Importante/Desejável] | [Condições objetivas para validar] | [UCXX] |

**Orientação:** atribua identificador único; descreva comportamento observável; indique ator, condições e resultado esperado nos critérios de aceitação; vincule a regra de negócio e caso de uso aplicáveis. Consulte também as [histórias de usuário](historias-de-usuario.md) e a [matriz de rastreabilidade](02-requisitos/matriz-de-rastreabilidade.md).
