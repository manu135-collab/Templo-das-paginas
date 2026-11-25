# 1.2. Descrição dos Usuários

O sistema possui três perfis, com responsabilidades e permissões distintas. O acesso às funcionalidades respeita o perfil autenticado (RNF04).

## Leitor

Membro da comunidade devidamente cadastrado. Consulta o acervo, verifica a disponibilidade das obras, reserva obras cujos exemplares estão todos emprestados e acompanha seus empréstimos, reservas e pendências.

## Bibliotecário

Funcionário responsável pelo atendimento ao público, pelo registro de empréstimos, devoluções e renovações e pela manutenção do acervo. Pode pesquisar o acervo e gerenciar obras e exemplares.

## Administrador

Responsável pela gestão das contas de funcionários e de leitores, pelas configurações do sistema e pela emissão de relatórios gerenciais. Também pode gerenciar o acervo (RN09).

## Permissões por perfil

| Funcionalidade | Caso de uso | Leitor | Bibliotecário | Administrador |
|---|---|:---:|:---:|:---:|
| Cadastrar-se | UC1 | Sim | Não | Não |
| Logar | UC2 | Sim | Sim | Sim |
| Pesquisar acervo | UC3 | Sim | Sim | Não |
| Reservar obra | UC4 | Sim | Não | Não |
| Consultar histórico | UC5 | Sim | Não | Não |
| Realizar empréstimo | UC6 | Não | Sim | Não |
| Registrar devolução | UC7 | Não | Sim | Não |
| Encerrar sessão | UC8 | Sim | Sim | Sim |
| Gerenciar acervo | UC9 | Não | Sim | Sim |
| Gerenciar usuários | UC10 | Não | Não | Sim |
| Gerar relatórios | UC11 | Não | Não | Sim |
| Renovar empréstimo | UC12 | Não | Sim | Não |
