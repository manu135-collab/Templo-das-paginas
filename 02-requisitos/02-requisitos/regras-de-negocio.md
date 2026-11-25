# 2.3. Regras de Negócio

As regras abaixo definem condições que devem ser respeitadas durante as operações da biblioteca.

| ID | Regra | Descrição |
|---|---|---|
| RN01 | Limite de empréstimos | Cada leitor poderá manter, simultaneamente, no máximo 3 obras emprestadas. |
| RN02 | Prazo de empréstimo | O prazo padrão de empréstimo é de 14 dias corridos. |
| RN03 | Renovação | O empréstimo poderá ser renovado até 2 vezes, desde que não haja reserva pendente e que o leitor não esteja em atraso. |
| RN04 | Penalidade por atraso | Para cada dia de atraso, o leitor ficará impedido de realizar novos empréstimos por período equivalente. Critério sujeito à validação da biblioteca. |
| RN05 | Cadastro ativo | Somente leitores com cadastro ativo e sem pendências poderão realizar empréstimos. |
| RN06 | E-mail único | Não poderão existir dois cadastros com o mesmo e-mail. |
| RN07 | Obras de consulta | Obras classificadas como “consulta local” não poderão ser emprestadas. |
| RN08 | Validade da reserva | A reserva disponibilizada ao leitor permanecerá retida por 48 horas e será cancelada após esse prazo. |
| RN09 | Permissão sobre o acervo | Somente bibliotecários e administradores poderão alterar o acervo. |
| RN10 | Exemplar emprestado | Exemplar com empréstimo ativo não poderá ser removido do acervo. |

## Template para novas regras

| ID | Regra | Condição | Consequência | Requisitos/casos relacionados |
|---|---|---|---|---|
| RNXX | [Nome curto] | [Quando se aplica] | [Comportamento obrigatório] | [RFXX / UCXX] |

> **Ponto para validação com a biblioteca:** a duração da penalidade de atraso descrita em RN04 foi marcada como sujeita à validação no material de origem.
