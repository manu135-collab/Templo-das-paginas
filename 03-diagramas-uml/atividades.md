# Diagramas de Atividades

## Atividade: realizar empréstimo (Figura 6)

Fluxo especificado no documento fornecido: início → identificar leitor → verificar cadastro ativo e ausência de pendências. Se inválido, exibir motivo e encerrar; se válido, informar exemplar → verificar disponibilidade e se pode ser emprestado. Se indisponível ou de consulta local, sugerir reserva e encerrar; se disponível, verificar limite de três empréstimos. Se o limite foi atingido, recusar e encerrar; caso contrário, registrar empréstimo, calcular devolução, emitir comprovante e finalizar.

```mermaid
flowchart TD
  A([Início]) --> B[Identificar leitor]
  B --> C{Cadastro ativo e sem pendências?}
  C -- Não --> D[Exibir motivo]
  D --> Z([Fim])
  C -- Sim --> E[Informar exemplar]
  E --> F{Disponível e emprestável?}
  F -- Não --> G[Sugerir reserva]
  G --> Z
  F -- Sim --> H{Abaixo do limite de 3 empréstimos?}
  H -- Não --> I[Recusar empréstimo]
  I --> Z
  H -- Sim --> J[Registrar empréstimo e calcular devolução]
  J --> K[Emitir comprovante]
  K --> Z
```

## Atividade: login (Figura 7)

Início → inserir e-mail e senha → validar dados → credenciais válidas? Se não, exibir erro e retornar à inserção; se sim, acessar sistema → exibir tela inicial → fim.

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

## Template de atividade

```mermaid
flowchart TD
  A([Início]) --> B[Atividade]
  B --> C{Condição?}
  C -- Sim --> D[Fluxo principal]
  C -- Não --> E[Alternativa ou erro]
  D --> Z([Fim])
  E --> Z
```

Ao adicionar um fluxo, identifique claramente início/fim, decisões, alternativas, erros e requisitos/regras relacionados. Os diagramas de atividade acima são representações textuais dos fluxos descritos, não imagens das figuras originais.
