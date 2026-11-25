# 3.3. Diagramas de Atividades

## Atividade: realizar empréstimo (Figura 6)

Fluxo: início → identificar leitor → informar exemplar → verificar cadastro ativo e ausência de pendências (RN05). Se inválido, exibir o motivo da recusa e encerrar; se válido, verificar disponibilidade e se o exemplar pode ser emprestado (RN07). Se indisponível ou de consulta local, exibir o motivo ou sugerir reserva e encerrar; se disponível, verificar o limite de três empréstimos (RN01). Se o limite foi atingido, recusar e encerrar; caso contrário, registrar o empréstimo, calcular a data de devolução (RN02), emitir o comprovante e finalizar.

```mermaid
flowchart TD
  A([Início]) --> B[Identificar leitor]
  B --> B2[Informar exemplar]
  B2 --> C{Cadastro ativo e sem pendências?}
  C -- Não --> D[Exibir motivo da recusa]
  D --> Z([Fim])
  C -- Sim --> F{Exemplar disponível e emprestável?}
  F -- Não --> G[Exibir motivo da recusa ou sugerir reserva]
  G --> Z
  F -- Sim --> H{Abaixo do limite de 3 empréstimos?}
  H -- Não --> I[Exibir motivo da recusa: limite atingido]
  I --> Z
  H -- Sim --> J[Registrar empréstimo]
  J --> J2[Calcular data de devolução]
  J2 --> K[Emitir comprovante]
  K --> Z
```

![Figura 6 – Diagrama de Atividades: Realizar Empréstimo](imagem/atividade%20realizar%20emprestimo.jpeg)

*Figura 6 – Diagrama de Atividades: Realizar Empréstimo.*

## Atividade: login (Figura 7)

Fluxo: início → inserir e-mail e senha → validar dados → credenciais válidas? Se não, exibir mensagem de erro e retornar à inserção; se sim, acessar o sistema → exibir a tela inicial → fim.

```mermaid
flowchart TD
  A([Início]) --> B[Inserir e-mail e senha]
  B --> C[Validar dados]
  C --> D{Credenciais válidas?}
  D -- Não --> E[Exibir mensagem de erro]
  E --> B
  D -- Sim --> F[Acessar sistema]
  F --> G[Exibir tela inicial]
  G --> H([Fim])
```

![Figura 7 – Diagrama de Atividades: Login](imagem/atividade%20login.jpeg)

*Figura 7 – Diagrama de Atividades: Login.*
