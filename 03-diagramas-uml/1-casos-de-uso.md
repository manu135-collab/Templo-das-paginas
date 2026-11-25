# 3.1. Diagramas de Casos de Uso

## Atores e casos de uso

| Ator | Casos de uso |
|---|---|
| Leitor | UC1 Cadastrar; UC2 Logar; UC3 Pesquisar Acervo; UC4 Reservar Obra; UC5 Consultar Histórico; UC8 Encerrar Sessão |
| Bibliotecário | UC2 Logar; UC3 Pesquisar Acervo; UC6 Realizar Empréstimo; UC7 Registrar Devolução; UC8 Encerrar Sessão; UC9 Gerenciar Acervo; UC12 Renovar Empréstimo |
| Administrador | UC2 Logar; UC8 Encerrar Sessão; UC9 Gerenciar Acervo; UC10 Gerenciar Usuários; UC11 Gerar Relatórios |

RF10 (controlar atrasos) e RF11 (notificar leitor) são executados automaticamente: RF10 em rotina diária e durante o UC7; RF11 após a devolução de obra reservada, no UC7.

## Diagrama de casos de uso

![Figura 1 – Diagrama de Casos de Uso do sistema Templo das Páginas](imagem/sistema%20de%20biblioteca%20publica.jpeg)

*Figura 1 – Diagrama de Casos de Uso do sistema Templo das Páginas.*

## Especificação dos casos de uso

### UC1 — Cadastrar
- **Ator principal:** Leitor. **Secundários:** N/A.
- **Resumo:** criar o cadastro do leitor para acesso ao sistema.
- **Pré-condições:** acesso à internet e dados solicitados disponíveis.
- **Pós-condições:** cadastro criado, se os dados forem válidos; usuário redirecionado ao login.
- **Fluxo principal:** 1. Selecionar "Realizar cadastro". 2. Informar nome, documento, e-mail e senha. 3. O sistema valida os dados. 4. O sistema confirma o cadastro. 5. O sistema redireciona ao login.
- **Restrições:** dados inválidos ou e-mail já cadastrado impedem o cadastro (RN06).

### UC2 — Logar
- **Atores:** Leitor, Bibliotecário ou Administrador.
- **Resumo:** autenticar o usuário para acesso à aplicação.
- **Pré-condições:** acesso à internet, cadastro existente e credenciais disponíveis.
- **Pós-condições:** usuário direcionado à tela inicial do seu perfil.
- **Fluxo principal:** 1. Informar e-mail e senha. 2. Acionar o login. 3. O sistema valida as credenciais e o perfil. 4. O sistema libera o acesso.
- **Exceção:** credenciais inválidas não liberam o acesso e geram mensagem de erro.

### UC3 — Pesquisar Acervo
- **Atores:** Leitor ou Bibliotecário.
- **Pré-condição:** usuário autenticado.
- **Pós-condição:** obras encontradas exibidas com a quantidade de exemplares disponíveis.
- **Fluxo principal:** 1. Selecionar "Pesquisar acervo". 2. Informar título, autor, assunto ou ISBN. 3. Solicitar a busca. 4. O sistema consulta o acervo e apresenta os resultados em até 3 segundos (RNF02).
- **Exceções:** termo vazio solicita preenchimento; ausência de resultados gera mensagem clara.

### UC4 — Reservar Obra
- **Ator:** Leitor.
- **Pré-condições:** leitor autenticado e com cadastro ativo; nenhum exemplar disponível.
- **Pós-condição:** reserva registrada na fila da obra.
- **Fluxo principal:** 1. Localizar a obra (UC3). 2. Selecionar "Reservar". 3. Confirmar. 4. O sistema verifica a indisponibilidade, registra a reserva na fila e confirma.
- **Regras/exceções:** havendo exemplar disponível, o leitor é orientado a realizar o empréstimo; disponibilizada a obra, a reserva é retida por 48 horas (RN08); o leitor pode cancelar a reserva.

### UC5 — Consultar Histórico
- **Ator:** Leitor.
- **Pré-condição:** leitor autenticado.
- **Pós-condição:** empréstimos, reservas e pendências do leitor exibidos.
- **Fluxo principal:** 1. Selecionar "Meu histórico". 2. O sistema consulta os dados do usuário autenticado e exibe empréstimos ativos e encerrados, reservas e pendências.
- **Restrições:** o leitor só visualiza os próprios dados; sem registros, é exibida mensagem informativa.

### UC6 — Realizar Empréstimo
- **Ator principal:** Bibliotecário. **Ator secundário:** Leitor.
- **Pré-condições:** bibliotecário autenticado; leitor ativo e sem pendências; exemplar disponível.
- **Pós-condições:** empréstimo registrado, exemplar indisponível e data de devolução informada.
- **Fluxo principal:** 1. Identificar o leitor. 2. Informar o exemplar. 3. Confirmar. 4. O sistema verifica RN01, RN05 e RN07, registra o empréstimo, calcula a data de devolução (RN02) e exibe o comprovante.
- **Exceções:** limite de empréstimos atingido, leitor impedido ou obra de consulta local recusam a operação, com mensagem explicativa.

### UC7 — Registrar Devolução
- **Ator:** Bibliotecário.
- **Pré-condições:** bibliotecário autenticado e exemplar com empréstimo ativo.
- **Pós-condições:** exemplar disponível; eventual penalidade aplicada; próximo leitor notificado, se houver reserva.
- **Fluxo principal:** 1. Informar o exemplar. 2. Confirmar. 3. O sistema localiza o empréstimo, verifica atraso e aplica a RN04, atualiza a disponibilidade e notifica o próximo da fila, se houver reserva.
- **Exceção:** sem empréstimo ativo, a devolução não é registrada.

### UC8 — Encerrar Sessão
- **Atores:** Leitor, Bibliotecário ou Administrador.
- **Pré-condição:** usuário autenticado.
- **Pós-condição:** sessão encerrada.
- **Fluxo principal:** 1. Acionar o logout. 2. O sistema encerra a sessão e redireciona à tela de login.

### UC9 — Gerenciar Acervo
- **Atores:** Bibliotecário ou Administrador.
- **Pré-condição:** usuário autenticado com perfil autorizado.
- **Pós-condição:** acervo atualizado.
- **Fluxo principal:** 1. Selecionar "Gerenciar acervo". 2. Escolher cadastrar, editar ou remover. 3. Informar ou alterar título, autor, ISBN, categoria, tipo e quantidade. 4. Confirmar. 5. O sistema valida, verifica a permissão, grava e confirma.
- **Restrições:** aplicar RN09 e RN10; a remoção exige confirmação.

### UC10 — Gerenciar Usuários
- **Ator:** Administrador.
- **Pré-condição:** administrador autenticado.
- **Pós-condição:** conta criada, alterada ou desativada.
- **Fluxo principal:** 1. Selecionar "Gerenciar usuários". 2. Escolher criar, editar ou desativar. 3. Informar ou alterar dados e perfil. 4. Confirmar. 5. O sistema valida o e-mail único, grava e confirma.
- **Restrições:** aplicar RN06; conta desativada não pode acessar o sistema.

### UC11 — Gerar Relatórios
- **Ator:** Administrador.
- **Pré-condição:** administrador autenticado.
- **Pós-condição:** relatório solicitado exibido.
- **Fluxo principal:** 1. Selecionar "Relatórios". 2. Escolher obras mais emprestadas, atrasos ou movimentação mensal. 3. Informar o período. 4. Solicitar a geração. 5. O sistema consolida os dados e exibe o resultado.
- **Exceções/restrições:** acesso somente a administradores; sem dados no período, é exibida mensagem informativa.

### UC12 — Renovar Empréstimo
- **Ator principal:** Bibliotecário. **Ator secundário:** Leitor.
- **Pré-condições:** bibliotecário autenticado e leitor com empréstimo ativo.
- **Pós-condição:** empréstimo renovado e nova data de devolução informada.
- **Fluxo principal:** 1. Identificar o leitor. 2. Selecionar o empréstimo. 3. Confirmar. 4. O sistema verifica a RN03, registra a renovação, calcula o prazo (RN02) e exibe o comprovante.
- **Exceções:** a renovação é recusada após duas renovações, se houver reserva pendente ou se houver atraso, com o motivo informado.
