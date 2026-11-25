# TP2 – Interação Humano-Computador (IHC)

<p align="center"><strong>Lab Manager</strong></p>
<p align="center">Sistema de gerenciamento de materiais e agendamentos do Laboratório de Biologia</p>

**Instituição:** Universidade Federal do Amazonas (UFAM) – Instituto de Ciências Exatas e Tecnologia (ICET)  
**Disciplina:** Interação Humano-Computador (IHC)  
**Trabalho:** Trabalho Prático 2 (TP2)  
**Ano:** 2026

## Integrantes

- Emanuel Queiroz
- Manuely da Silva Simões
- Renato Augusto Amazonas Gomes

---

## 1. Apresentação do sistema

O **Lab Manager** é uma proposta de sistema para centralizar a solicitação de materiais e equipamentos, o agendamento de aulas práticas e o acompanhamento de pedidos no Laboratório de Biologia da UFAM.

O projeto busca facilitar a rotina dos professores e da equipe técnica, reduzindo a dispersão de informações entre planilhas, e-mails e WhatsApp. A proposta considera a consulta de disponibilidade de materiais, o prazo mínimo de 48 horas para solicitações, as notificações, o controle de reposições e a consulta de informações dos responsáveis pelo laboratório.

Também são considerados recursos de acessibilidade, como ampliação de textos, ajustes de contraste e navegação por teclado, visando à autonomia dos usuários.

> [!NOTE]
> O sistema encontra-se na etapa de design e prototipação de baixa fidelidade. As funcionalidades descritas representam propostas de interação, e não funcionalidades já implementadas.

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
