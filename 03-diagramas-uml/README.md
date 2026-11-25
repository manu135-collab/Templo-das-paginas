# 3. Diagramas UML

Esta pasta reúne as especificações dos casos de uso e os diagramas/fluxos UML informados no documento de requisitos.

## Conteúdo

- [Casos de uso e especificações UC1–UC12](casos-de-uso.md)
- [Diagramas de sequência](sequencia.md)
- [Diagramas de atividades](atividades.md)

## Sobre as figuras

O conteúdo original recebido descreve Figuras 1–7, mas não inclui os arquivos de imagem. Para não inventar diagramas gráficos, esta documentação registra os fluxos fornecidos e disponibiliza fontes Mermaid/PlantUML quando adequadas. As imagens podem ser adicionadas nesta pasta e vinculadas aos documentos.

## Template para documentar um diagrama

```markdown
# [Tipo do diagrama]: [funcionalidade]

**Requisitos relacionados:** [RF/RNF/RN]  
**Atores/participantes:** [perfis ou componentes]

![Descrição acessível do diagrama](caminho/para/figura.ext)

## Fluxo representado
1. [Etapa]

## Regras e exceções
- [Regra/alternativa]
```

Para diagramas novos, mantenha nomes de atores e regras alinhados com os requisitos e especifique claramente as exceções.
