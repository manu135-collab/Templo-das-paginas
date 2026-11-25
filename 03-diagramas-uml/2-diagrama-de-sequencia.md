# Diagramas de Sequência

Os fluxos seguem o padrão Boundary (Interface) – Control – Entity (Database). O material recebido descreve as interações abaixo; as fontes PlantUML registram esses passos para facilitar a renderização dos diagramas.

## Sequência: cadastrar leitor (Figura 2)

1. Leitor envia dados à interface.
2. Interface valida campos, formato do e-mail e tamanho mínimo da senha e encaminha ao controle.
3. Controle consulta o banco para verificar e-mail existente.
4. Se duplicado, retorna erro; caso contrário, insere o leitor e retorna sucesso.
5. Interface exibe a resposta ao leitor.

```plantuml
@startuml
actor Leitor
boundary Interface
control Control
entity Database
Leitor -> Interface: iniciar cadastro e informar dados
Interface -> Interface: validar campos, e-mail e senha
Interface -> Control: enviar dados validados
Control -> Database: verificar e-mail existente
alt e-mail já cadastrado
  Database --> Control: encontrado
  Control --> Interface: erro de duplicidade
else e-mail disponível
  Database --> Control: não encontrado
  Control -> Database: inserir leitor
  Database --> Control: confirmação
  Control --> Interface: sucesso
end
Interface --> Leitor: exibir resultado
@enduml
```

## Sequência: login (Figura 3)

1. Usuário informa e-mail e senha.
2. Interface verifica preenchimento e aciona o controle.
3. Controle consulta o banco para validar as credenciais.
4. Credenciais válidas liberam acesso e direcionam à tela inicial; inválidas geram erro.

```plantuml
@startuml
actor Usuario as "Usuário"
boundary Interface
control Control
entity Database
Usuario -> Interface: informar e-mail e senha
Interface -> Interface: verificar preenchimento
Interface -> Control: validar credenciais
Control -> Database: consultar credenciais
alt credenciais válidas
  Database --> Control: usuário e perfil válidos
  Control --> Interface: liberar acesso
  Interface --> Usuario: redirecionar à tela inicial
else credenciais inválidas
  Database --> Control: inválidas
  Control --> Interface: retornar erro
  Interface --> Usuario: exibir mensagem de erro
end
@enduml
```

## Sequência: realizar empréstimo (Figura 4)

1. Bibliotecário informa leitor e exemplar na interface.
2. Interface envia solicitação ao controle.
3. Controle consulta situação do leitor, empréstimos ativos, disponibilidade e tipo do exemplar.
4. Se regra não for atendida, retorna motivo; caso contrário, registra empréstimo e atualiza exemplar para “emprestado”.
5. Interface exibe comprovante e data de devolução.

```plantuml
@startuml
actor Bibliotecario as "Bibliotecário"
boundary Interface
control Control
entity Database
Bibliotecario -> Interface: informar leitor e exemplar
Interface -> Control: solicitar empréstimo
Control -> Database: consultar leitor, empréstimos e exemplar
alt regra de negócio não atendida
  Database --> Control: condição inválida
  Control --> Interface: motivo da recusa
  Interface --> Bibliotecario: exibir motivo
else regras atendidas
  Database --> Control: leitor e exemplar elegíveis
  Control -> Database: registrar empréstimo e atualizar exemplar
  Database --> Control: confirmação e prazo
  Control --> Interface: comprovante e data prevista
  Interface --> Bibliotecario: exibir comprovante
end
@enduml
```

## Sequência: logout (Figura 5)

1. Usuário aciona “Encerrar Sessão” na interface.
2. Controle registra log e atualiza o banco.
3. Interface redireciona à tela de login e informa o encerramento.

```plantuml
@startuml
actor Usuario as "Usuário"
boundary Interface
control Control
entity Database
Usuario -> Interface: acionar Encerrar Sessão
Interface -> Control: encerrar sessão
Control -> Database: registrar log e atualizar sessão
Database --> Control: confirmação
Control --> Interface: sessão encerrada
Interface --> Usuario: redirecionar ao login e confirmar
@enduml
```

## Template

```plantuml
@startuml
actor Ator
boundary Interface
control Controle
entity Entidade
Ator -> Interface: [ação]
Interface -> Controle: [solicitação]
Controle -> Entidade: [consulta/alteração]
Entidade --> Controle: [resultado]
Controle --> Interface: [resposta]
Interface --> Ator: [resultado apresentado]
@enduml
```
