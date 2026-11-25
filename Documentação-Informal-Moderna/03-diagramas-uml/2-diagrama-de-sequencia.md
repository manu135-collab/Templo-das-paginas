# 3.2. Diagramas de Sequência

Os fluxos seguem o padrão Boundary (Interface) – Control – Entity (Database).

## Cadastrar leitor

<p align="center">
  <img src="imagem/sequencia%20cadastrar%20leitor.jpeg" alt="Figura 2 – Diagrama de Sequência: Cadastrar Leitor" width="700">
  <br>
  <em>Figura 2 – Diagrama de Sequência: Cadastrar Leitor.</em>
</p>

1. O leitor informa os dados do cadastro na interface.
2. A interface valida os campos obrigatórios; se houver campos inválidos, exibe os erros de validação.
3. Sendo válidos, a interface solicita o cadastro ao controle.
4. O controle consulta o e-mail no banco de dados.
5. Se o e-mail já estiver cadastrado, retorna erro de duplicidade e a interface exibe a mensagem de erro.
6. Se o e-mail estiver disponível, o controle insere os dados do leitor, o banco confirma a inserção e a interface exibe a confirmação do cadastro.

## Logar

<p align="center">
  <img src="imagem/sequencia%20logar.jpeg" alt="Figura 3 – Diagrama de Sequência: Logar" width="800">
  <br>
  <em>Figura 3 – Diagrama de Sequência: Logar.</em>
</p>

1. O usuário informa e-mail e senha.
2. A interface verifica o preenchimento dos campos; se estiverem vazios, exibe a mensagem de preenchimento obrigatório.
3. Estando preenchidos, a interface solicita a autenticação ao controle.
4. O controle consulta as credenciais no banco de dados.
5. Credenciais válidas: o controle confirma a autenticação e o acesso ao sistema é liberado.
6. Credenciais inválidas: o controle retorna a falha e a interface exibe o erro de login.

## Realizar empréstimo

<p align="center">
  <img src="imagem/sequencia%20realizar%20emprestimo.jpeg" alt="Figura 4 – Diagrama de Sequência: Realizar Empréstimo" width="800">
  <br>
  <em>Figura 4 – Diagrama de Sequência: Realizar Empréstimo.</em>
</p>

1. O bibliotecário informa o leitor e o exemplar; a interface valida os campos obrigatórios e solicita o empréstimo ao controle.
2. O controle consulta a situação do leitor no banco de dados.
3. Se o leitor estiver irregular ou não existir, o empréstimo é recusado e o motivo é exibido.
4. Sendo o leitor apto, se o limite de 3 empréstimos foi atingido, o empréstimo é recusado por limite excedido.
5. Se o limite não foi atingido, o controle consulta a disponibilidade e o tipo do exemplar. Se estiver indisponível ou não for permitido o empréstimo, o empréstimo é recusado e o motivo é exibido.
6. Se as regras forem atendidas, o controle registra o empréstimo e a interface exibe o comprovante.

## Encerrar sessão (logout)

<p align="center">
  <img src="imagem/sequencia%20logout.jpeg" alt="Figura 5 – Diagrama de Sequência: Logout" width="650">
  <br>
  <em>Figura 5 – Diagrama de Sequência: Logout.</em>
</p>

1. O usuário aciona "Encerrar Sessão" na interface, que solicita o encerramento ao controle.
2. O controle identifica a sessão, registra o evento e grava o log de logout no banco de dados, atualizando a sessão.
3. O banco confirma a atualização e o controle confirma o encerramento à interface.
4. A interface limpa os dados da sessão e redireciona o usuário para a tela de login.
