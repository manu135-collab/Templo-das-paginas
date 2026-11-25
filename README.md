# TP2 – Interação Humano-Computador (IHC)

<p align="center"><strong>Templo das Páginas</strong></p>
<p align="center">Sistema de gerenciamento de uma biblioteca pública</p>

**Instituição:** Universidade Federal do Amazonas (UFAM) – Instituto de Ciências Exatas e Tecnologia (ICET)  
**Disciplina:** Engenharia de Requisitos 
**Trabalho:** Documentação Informal Moderna 
**Ano:** 2026

## Integrantes

- Emanuel Queiroz
- Manuely da Silva Simões
- Renato Augusto Amazonas Gomes

---

## 1. Apresentação do sistema

O **Templo das Páginas** é um sistema destinado à gestão de uma biblioteca pública. Ele
possibilita o cadastro de leitores, o gerenciamento do acervo, a consulta de obras e o registro
de empréstimos, devoluções, renovações e reservas, além do controle de atrasos e da emissão
de relatórios gerenciais. O sistema tem por objetivo substituir os controles manuais (fichas e
planilhas), reduzir a ocorrência de erros, tornar o atendimento mais ágil e oferecer ao público
acesso facilitado à consulta do acervo.

---
## 2. Sumário

### 📁 Introdução

| Documento | Descrição |
|---|---|
| 📄 [1.1 – Descrição Geral do Software](01-introducao/1-descricao-geral-do-software.md) | Apresenta a visão geral, os objetivos e o escopo do sistema Templo das Páginas. |
| 📄 [1.2 – Descrição dos Usuários](01-introducao/2-descricao-dos-usuarios.md) | Descreve os perfis de usuários que interagem com o sistema e suas necessidades. |

### 📁 Requisitos Gerais do Software

| Documento | Descrição |
|---|---|
| 📄 [2.1 – Requisitos Funcionais](02-requisitos/funcionais.md) | Especifica as funcionalidades e os serviços oferecidos pelo sistema. |
| 📄 [2.2 – Requisitos Não Funcionais](02-requisitos/nao-funcionais.md) | Define critérios de qualidade e restrições do sistema, como segurança, desempenho e usabilidade. |
| 📄 [2.3 – Regras de Negócio](02-requisitos/02-requisitos/regras-de-negocio.md) | Reúne as regras e políticas que orientam as operações da biblioteca. |

### 📁 Diagramas UML

| Documento | Descrição |
|---|---|
| 📄 [3.1 – Diagramas de Casos de Uso](03-diagramas-uml/casos-de-uso.md) | Apresenta os casos de uso e as interações dos atores com o sistema. |
| 📄 [3.2 – Diagramas de Sequência](03-diagramas-uml/sequencia.md) | Representa a troca de mensagens entre atores e componentes ao longo dos cenários. |
| 📄 [3.3 – Diagramas de Atividades](03-diagramas-uml/atividades.md) | Representa os fluxos de atividades dos principais processos do sistema. |

## 3. Organização do repositório

```text
📁 Templo-das-paginas/
├── README.md
├── 📁 01-introducao/
│   ├── 1-descricao-geral-do-software.md
│   └── 2-descricao-dos-usuarios.md
├── 📁 02-requisitos/
│   ├── funcionais.md
│   ├── nao-funcionais.md
│   └── 📁 02-requisitos/
│       └── regras-de-negocio.md
└── 📁 03-diagramas-uml/
    ├── casos-de-uso.md
    ├── sequencia.md
    └── atividades.md
```
