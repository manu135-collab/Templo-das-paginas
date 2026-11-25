# 2.2. Requisitos Não Funcionais

Os requisitos não funcionais definem atributos de qualidade e restrições operacionais do sistema.

| ID | Categoria | Descrição | Prioridade |
|---|---|---|---|
| RNF01 | Desempenho | A autenticação deverá ser concluída em até 2 segundos. | Essencial |
| RNF02 | Desempenho | As buscas no acervo deverão retornar resultados em até 3 segundos. | Importante |
| RNF03 | Segurança | Senhas armazenadas por hash criptográfico e comunicação utilizando HTTPS. | Essencial |
| RNF04 | Segurança | Controlar acesso às funcionalidades por perfil (leitor, bibliotecário e administrador). | Essencial |
| RNF05 | Usabilidade | Interface simples e utilizável por pessoas com pouca familiaridade com informática. | Importante |
| RNF06 | Acessibilidade | Observar boas práticas, como contraste adequado e navegação por teclado. | Desejável |
| RNF07 | Compatibilidade | Funcionar nos principais navegadores e em telas móveis, com design responsivo. | Importante |
| RNF08 | Disponibilidade | Permanecer disponível em, no mínimo, 95% do horário de funcionamento da biblioteca. | Importante |
| RNF09 | Manutenibilidade | Código modular e documentado para facilitar a manutenção. | Importante |
| RNF10 | Legal | Tratar dados pessoais em conformidade com a Lei Geral de Proteção de Dados (LGPD). | Essencial |

## Template para novos requisitos não funcionais

| ID | Categoria | Requisito mensurável/verificável | Prioridade | Método de verificação |
|---|---|---|---|---|
| RNFXX | [Categoria] | [Meta ou condição verificável] | [Essencial/Importante/Desejável] | [Teste, inspeção ou análise] |

**Orientação:** prefira limites mensuráveis, indique contexto de medição e método de verificação. Evite expressões subjetivas sem critérios de avaliação.
