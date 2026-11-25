# 1.2. Descrição dos Usuários

O sistema possui três perfis, com responsabilidades e permissões distintas. O acesso às funcionalidades deverá respeitar o perfil autenticado (RNF04).

## Leitor

Membro da comunidade devidamente cadastrado. Consulta o acervo, verifica disponibilidade, reserva obras indisponíveis, acompanha seus empréstimos, reservas e pendências e, por intermédio do bibliotecário, retira obras por empréstimo.

## Bibliotecário

Funcionário responsável pelo atendimento, gerenciamento do acervo e registro de empréstimos, devoluções e renovações. Pode pesquisar o acervo e manter obras e exemplares, conforme as regras RN09 e RN10.

## Administrador

Responsável pela gestão das contas de funcionários e leitores, atribuição de perfis, configurações do sistema e emissão de relatórios gerenciais. Também pode gerenciar o acervo.

## Matriz resumida de permissões

| Funcionalidade | Leitor | Bibliotecário | Administrador |
|---|---:|---:|---:|
| Cadastrar-se e autenticar-se | Sim | Sim | Sim |
| Pesquisar acervo | Sim | Sim | Conforme acesso autenticado |
| Reservar obra e consultar próprio histórico | Sim | Não especificado | Não especificado |
| Registrar empréstimo, devolução e renovação | Não | Sim | Não especificado |
| Gerenciar acervo | Não | Sim | Sim |
| Gerenciar contas e perfis | Não | Não | Sim |
| Gerar relatórios gerenciais | Não | Não | Sim |

> “Não especificado” indica que o documento de requisitos fornecido não define essa permissão; não deve ser interpretado automaticamente como autorização.

## Template para atualização

Para adicionar um perfil, documente: finalidade, responsabilidades, dados que pode consultar ou alterar, operações permitidas e restrições. Mantenha a matriz alinhada com os requisitos de segurança e casos de uso.
