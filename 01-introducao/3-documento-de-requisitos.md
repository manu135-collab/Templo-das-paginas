# Templo das Páginas — Documento de Requisitos

**Universidade Federal do Amazonas (UFAM)**  
**Instituto de Ciências Exatas e Tecnologia (ICET)**  
**Curso:** Engenharia de Software  
**Local:** Itacoatiara/AM  
**Ano:** 2026  
**Responsável pela elaboração:** Manuely da Silva Simões  
**Público-alvo:** colaboradores do projeto, cliente (biblioteca pública), desenvolvedores, responsáveis por qualidade e testes e orientador/professor.

> Documento consolidado a partir do material de requisitos fornecido. Os diagramas UML são descritos em texto; as imagens originais não foram incluídas no material recebido.

## Histórico de alterações

| Versão | Responsável | Data | Alterações |
|---|---|---|---|
| 1.0 | Manuely da Silva Simões | 13/10/2026 | Criação do documento e levantamento de requisitos. |
| 1.1 | Manuely da Silva Simões | 14/10/2026 | Inclusão do diagrama de casos de uso e das especificações. |
| 1.2 | Manuely da Silva Simões | 14/10/2026 | Inclusão dos diagramas de sequência e de atividades. |
| 1.3 | Manuely da Silva Simões | 15/10/2026 | Correções e complementações de casos de uso, histórias, requisitos, rastreabilidade e numeração de tabelas e figuras. |
| 1.4 | Manuely da Silva Simões | 15/10/2026 | Revisão geral. |

## Sumário

1. [Introdução](#1-introdução)
2. [Requisitos gerais](#2-requisitos-gerais)
3. [Histórias de usuário](#3-histórias-de-usuário)
4. [Perspectivas e rastreabilidade](#4-perspectivas-e-rastreabilidade)
5. [Casos de uso](#5-casos-de-uso)
6. [Fluxos UML descritos](#6-fluxos-uml-descritos)

## 1. Introdução

### 1.1 Objetivo e visão geral

Este documento especifica os requisitos do **Templo das Páginas**, sistema destinado à gestão de uma biblioteca pública. O sistema deverá apoiar o cadastro de leitores, o gerenciamento do acervo, a consulta de obras, empréstimos, devoluções, renovações e reservas, o controle de atrasos e a emissão de relatórios gerenciais. Seu objetivo é substituir controles manuais, reduzir erros, agilizar o atendimento e facilitar o acesso público à consulta do acervo.

O documento reúne requisitos funcionais, requisitos não funcionais, regras de negócio, histórias de usuário, requisitos em diferentes níveis de detalhe, matriz de rastreabilidade e especificações dos casos de uso. Esta especificação serve de referência para validação com o cliente, desenvolvimento e elaboração de testes.

### 1.2 Convenções e termos

| Sigla/termo | Significado |
|---|---|
| RF | Requisito funcional |
| RNF | Requisito não funcional |
| RN | Regra de negócio |
| RU | Requisito de usuário |
| RS | Requisito de sistema |
| RSW | Requisito de software |
| UC | Caso de uso (Use Case) |
| Acervo | Conjunto de obras da biblioteca, como livros e periódicos |
| Exemplar | Cópia física de uma obra do acervo |
| Leitor | Pessoa cadastrada que utiliza os serviços da biblioteca |

### 1.3 Usuários do sistema

- **Leitores:** membros da comunidade cadastrados que consultam o acervo, reservam obras e realizam empréstimos.
- **Bibliotecários:** funcionários que atendem leitores, registram empréstimos e devoluções e mantêm o acervo.
- **Administradores:** responsáveis pelas contas de funcionários, configurações do sistema e relatórios.

## 2. Requisitos gerais

### 2.1 Requisitos funcionais

| ID | Nome | Descrição | Prioridade |
|---|---|---|---|
| RF01 | Realizar login | Permitir que usuários cadastrados acessem o sistema usando e-mail e senha. | Essencial |
| RF02 | Cadastrar leitor | Permitir o cadastro de leitores com dados pessoais e de contato. | Essencial |
| RF03 | Encerrar sessão | Permitir que o usuário encerre sua sessão de forma segura. | Essencial |
| RF04 | Gerenciar acervo | Permitir que bibliotecários cadastrem, editem e removam obras e exemplares. | Essencial |
| RF05 | Pesquisar acervo | Buscar obras por título, autor, assunto ou ISBN e exibir a disponibilidade. | Essencial |
| RF06 | Realizar empréstimo | Registrar empréstimo de exemplar a leitor e informar a data prevista de devolução. | Essencial |
| RF07 | Registrar devolução | Registrar devolução e atualizar a disponibilidade do exemplar. | Essencial |
| RF08 | Renovar empréstimo | Permitir a renovação de empréstimos ativos, respeitando as regras de negócio. | Importante |
| RF09 | Reservar obra | Permitir a reserva de obras quando todos os exemplares estiverem emprestados. | Importante |
| RF10 | Controlar atrasos | Identificar empréstimos atrasados e aplicar a penalidade prevista. | Importante |
| RF11 | Notificar leitor | Enviar e-mail sobre vencimentos próximos e disponibilidade de obras reservadas. | Desejável |
| RF12 | Consultar histórico | Permitir que o leitor consulte empréstimos, reservas e pendências próprias. | Importante |
| RF13 | Gerenciar usuários | Permitir que o administrador crie, edite e desative contas de funcionários e leitores. | Importante |
| RF14 | Gerar relatórios | Gerar relatórios de obras mais emprestadas, atrasos e movimentação mensal. | Desejável |

### 2.2 Requisitos não funcionais

| ID | Categoria | Descrição | Prioridade |
|---|---|---|---|
| RNF01 | Desempenho | A autenticação deverá ser concluída em até 2 segundos. | Essencial |
| RNF02 | Desempenho | As buscas no acervo deverão retornar resultados em até 3 segundos. | Importante |
| RNF03 | Segurança | Senhas armazenadas com hash criptográfico e comunicação por HTTPS. | Essencial |
| RNF04 | Segurança | Controlar o acesso às funcionalidades por perfil: leitor, bibliotecário e administrador. | Essencial |
| RNF05 | Usabilidade | Interface simples, utilizável por pessoas com pouca familiaridade com informática. | Importante |
| RNF06 | Acessibilidade | Observar boas práticas, incluindo contraste adequado e navegação por teclado. | Desejável |
| RNF07 | Compatibilidade | Funcionar nos principais navegadores e em telas móveis, com design responsivo. | Importante |
| RNF08 | Disponibilidade | Permanecer disponível em pelo menos 95% do horário de funcionamento da biblioteca. | Importante |
| RNF09 | Manutenibilidade | Código modular e documentado para facilitar a manutenção. | Importante |
| RNF10 | Legal | Tratar dados pessoais em conformidade com a Lei Geral de Proteção de Dados (LGPD). | Essencial |

### 2.3 Regras de negócio

| ID | Regra | Descrição |
|---|---|---|
| RN01 | Limite de empréstimos | Cada leitor poderá manter no máximo 3 obras emprestadas simultaneamente. |
| RN02 | Prazo de empréstimo | O prazo padrão é de 14 dias corridos. |
| RN03 | Renovação | Permitidas até 2 renovações, se não houver reserva pendente nem atraso do leitor. |
| RN04 | Penalidade por atraso | Para cada dia de atraso, o leitor ficará impedido de realizar novos empréstimos por período equivalente. O critério está sujeito à validação da biblioteca. |
| RN05 | Cadastro ativo | Somente leitores com cadastro ativo e sem pendências poderão realizar empréstimos. |
| RN06 | E-mail único | Não poderão existir dois cadastros com o mesmo e-mail. |
| RN07 | Obras de consulta | Obras classificadas como “consulta local” não poderão ser emprestadas. |
| RN08 | Validade da reserva | Uma obra disponibilizada ficará retida para o leitor por 48 horas; depois, a reserva será cancelada. |
| RN09 | Permissão sobre o acervo | Somente bibliotecários e administradores poderão alterar o acervo. |
| RN10 | Exemplar emprestado | Um exemplar com empréstimo ativo não poderá ser removido do acervo. |

## 3. Histórias de usuário

| RF | História | Prioridade / estimativa | Critérios de aceitação |
|---|---|---|---|
| RF01 | Como usuário, quero acessar o sistema por login para usar suas funcionalidades de forma segura e personalizada. | Essencial / 5 pontos | Informar e-mail e senha válidos; autenticar em até 2 s; credenciais inválidas geram mensagem de erro. |
| RF02 | Como visitante, quero me cadastrar para poder retirar obras e fazer reservas. | Essencial / 8 pontos | Preencher nome, e-mail, senha e documento; rejeitar e-mail já cadastrado (RN06); após o cadastro, redirecionar ao login. |
| RF03 | Como usuário, quero encerrar minha sessão para impedir que outra pessoa use minha conta no dispositivo. | Essencial / 3 pontos | Invalidar a sessão, redirecionar ao login e registrar a operação em log. |
| RF04 | Como bibliotecário, quero cadastrar, editar e remover obras e exemplares para manter o acervo atualizado. | Essencial / 13 pontos | Alterações restritas a bibliotecários e administradores (RN09); obra com título, autor, ISBN, categoria, tipo e quantidade; não remover exemplar emprestado (RN10); exigir confirmação de remoção. |
| RF05 | Como leitor, quero buscar por título, autor, assunto ou ISBN para verificar a disponibilidade. | Essencial / 8 pontos | Resultados em até 3 s, com quantidade disponível; exibir mensagem clara quando não houver resultados. |
| RF06 | Como bibliotecário, quero registrar empréstimo para controlar a posse e o prazo de devolução de cada obra. | Essencial / 13 pontos | Validar RN01, RN05 e RN07; calcular devolução automaticamente conforme RN02; alterar o exemplar para “emprestado”. |
| RF07 | Como bibliotecário, quero registrar devolução para disponibilizar a obra e identificar atrasos. | Essencial / 8 pontos | Marcar exemplar como disponível; aplicar eventual penalidade (RN04); notificar o leitor correspondente se houver reserva. |
| RF08 | Como bibliotecário, quero renovar empréstimo ativo a pedido do leitor. | Importante / 5 pontos | Limitar a 2 renovações; recusar se houver reserva pendente ou atraso (RN03); calcular novo prazo conforme RN02; explicar recusas. |
| RF09 | Como leitor, quero reservar uma obra emprestada para ser informado quando estiver disponível. | Importante / 8 pontos | Permitir somente quando não houver exemplar disponível; expirar conforme RN08; permitir cancelamento pelo leitor. |
| RF10 | Como bibliotecário, quero identificar empréstimos vencidos e aplicar penalidades automaticamente. | Importante / 8 pontos | Verificar diariamente empréstimos vencidos; bloquear novos empréstimos conforme RN04; disponibilizar consulta dos atrasos. |
| RF11 | Como leitor, quero receber e-mails sobre vencimentos e disponibilidade de reservas. | Desejável / 8 pontos | Notificar disponibilidade após devolução e informar prazo de 48 h (RN08); antecedência do aviso de vencimento será definida com a biblioteca. |
| RF12 | Como leitor, quero consultar meus empréstimos, reservas e pendências para acompanhar minha situação. | Importante / 5 pontos | Listar empréstimos ativos e encerrados com datas, reservas e pendências; permitir visualização somente dos próprios dados. |
| RF13 | Como administrador, quero criar, editar e desativar contas para controlar acesso e perfis. | Importante / 8 pontos | Permitir perfis leitor, bibliotecário e administrador; e-mail único (RN06); impedir acesso de conta desativada. |
| RF14 | Como administrador, quero gerar relatórios de empréstimos, atrasos e movimentação mensal para apoiar decisões. | Desejável / 8 pontos | Escolher tipo e período, visualizar resultado em tela e restringir acesso a administradores. |

## 4. Perspectivas e rastreabilidade

Os requisitos de usuário (RU), expressos na linguagem do cliente, são detalhados em requisitos de sistema (RS), que por sua vez orientam os requisitos de software (RSW).

### 4.1 Requisitos de usuário

| ID | Descrição | Origem |
|---|---|---|
| RU01 | O usuário necessita acessar o sistema de forma segura. | RF01, RF03 |
| RU02 | O leitor necessita realizar seu cadastro na biblioteca pelo sistema. | RF02 |
| RU03 | O leitor necessita localizar obras e verificar disponibilidade. | RF05 |
| RU04 | O bibliotecário necessita registrar empréstimos, devoluções e renovações com agilidade. | RF06, RF07, RF08 |
| RU05 | O leitor necessita reservar obras indisponíveis e ser informado quando estiverem disponíveis. | RF09, RF11 |
| RU06 | O bibliotecário necessita manter o acervo atualizado. | RF04 |
| RU07 | O leitor necessita acompanhar empréstimos, reservas e pendências. | RF12 |
| RU08 | O bibliotecário necessita que atrasos sejam identificados e penalizados automaticamente. | RF10 |
| RU09 | O administrador necessita gerenciar contas de funcionários e leitores. | RF13 |
| RU10 | O administrador necessita obter relatórios gerenciais sobre o uso da biblioteca. | RF14 |

### 4.2 Requisitos de sistema

| ID | Descrição | Deriva de |
|---|---|---|
| RS01 | Autenticar por e-mail e senha, manter sessão com tempo limite de inatividade e permitir encerramento seguro. | RU01 |
| RS02 | Validar e armazenar dados do leitor, impedindo e-mails duplicados. | RU02 |
| RS03 | Oferecer busca por múltiplos critérios e exibir disponibilidade em tempo real. | RU03 |
| RS04 | Registrar empréstimos, devoluções e renovações aplicando regras de negócio. | RU04 |
| RS05 | Gerenciar fila de reservas por obra e enviar notificações. | RU05 |
| RS06 | Permitir cadastro, consulta, edição e exclusão de obras e exemplares para perfis autorizados. | RU06 |
| RS07 | Exibir ao leitor autenticado seu histórico de empréstimos, reservas e pendências. | RU07 |
| RS08 | Identificar empréstimos vencidos e aplicar a penalidade definida em RN04. | RU08 |
| RS09 | Permitir criação, edição e desativação de contas com atribuição de perfil. | RU09 |
| RS10 | Gerar relatórios de obras mais emprestadas, atrasos e movimentação mensal, filtrados por período. | RU10 |

### 4.3 Requisitos de software

| ID | Descrição | Deriva de |
|---|---|---|
| RSW01 | Implementar tela e serviço de autenticação, hash de senha e controle de criação, expiração e encerramento de sessão. | RS01 |
| RSW02 | Implementar formulário de cadastro, validação de campos e verificação de e-mail no banco de dados. | RS02 |
| RSW03 | Implementar busca com índices para título, autor, assunto e ISBN. | RS03 |
| RSW04 | Implementar circulação (empréstimo, devolução e renovação), verificando RN01 a RN05. | RS04 |
| RSW05 | Implementar fila de reservas, expiração em 48 h e envio de e-mails. | RS05 |
| RSW06 | Implementar telas e serviços de cadastro, edição e exclusão de obras com controle de permissão. | RS06 |
| RSW07 | Implementar histórico filtrado pelo usuário autenticado. | RS07 |
| RSW08 | Implementar rotina diária de identificação de atrasos e bloqueio de novos empréstimos conforme RN04. | RS08 |
| RSW09 | Implementar gestão de contas, desativação lógica e controle de perfil. | RS09 |
| RSW10 | Implementar relatórios com consultas agregadas e filtro por período, restritos a administradores. | RS10 |

### 4.4 Matriz de rastreabilidade

| RF | RU | RS | RSW | Caso de uso / rotina |
|---|---|---|---|---|
| RF01 | RU01 | RS01 | RSW01 | UC2 |
| RF02 | RU02 | RS02 | RSW02 | UC1 |
| RF03 | RU01 | RS01 | RSW01 | UC8 |
| RF04 | RU06 | RS06 | RSW06 | UC9 |
| RF05 | RU03 | RS03 | RSW03 | UC3 |
| RF06 | RU04 | RS04 | RSW04 | UC6 |
| RF07 | RU04 | RS04 | RSW04 | UC7 |
| RF08 | RU04 | RS04 | RSW04 | UC12 |
| RF09 | RU05 | RS05 | RSW05 | UC4 |
| RF10 | RU08 | RS08 | RSW08 | Rotina diária e UC7 |
| RF11 | RU05 | RS05 | RSW05 | Rotina disparada em UC7 |
| RF12 | RU07 | RS07 | RSW07 | UC5 |
| RF13 | RU09 | RS09 | RSW09 | UC10 |
| RF14 | RU10 | RS10 | RSW10 | UC11 |

## 5. Casos de uso

### 5.1 Atores e casos de uso

| Ator | Casos de uso |
|---|---|
| Leitor | UC1 Cadastrar; UC2 Logar; UC3 Pesquisar Acervo; UC4 Reservar Obra; UC5 Consultar Histórico; UC8 Encerrar Sessão. |
| Bibliotecário | UC2 Logar; UC3 Pesquisar Acervo; UC6 Realizar Empréstimo; UC7 Registrar Devolução; UC9 Gerenciar Acervo; UC8 Encerrar Sessão; UC12 Renovar Empréstimo. |
| Administrador | UC2 Logar; UC9 Gerenciar Acervo; UC10 Gerenciar Usuários; UC11 Gerar Relatórios; UC8 Encerrar Sessão. |

RF10 e RF11 são executados automaticamente: o controle de atrasos ocorre em rotina diária e na devolução (UC7); as notificações são disparadas pela devolução de obra reservada (UC7).

### 5.2 Especificações resumidas

#### UC1 — Cadastrar
- **Ator:** leitor. **Pré-condição:** acesso à internet e dados disponíveis. **Pós-condição:** cadastro válido criado e usuário encaminhado ao login.
- **Fluxo:** leitor escolhe “Realizar cadastro” e informa nome, documento, e-mail e senha; sistema valida os dados, cria o cadastro e redireciona ao login.
- **Exceções:** dados inválidos ou e-mail já cadastrado impedem a criação.

#### UC2 — Logar
- **Atores:** leitor, bibliotecário ou administrador. **Pré-condição:** usuário cadastrado e conectado à internet. **Pós-condição:** acesso liberado e redirecionamento para a tela inicial correspondente ao perfil.
- **Fluxo:** usuário informa e-mail e senha; sistema valida as credenciais e o perfil e libera o acesso.
- **Exceção:** credenciais inválidas geram mensagem de erro e não liberam o acesso.

#### UC3 — Pesquisar Acervo
- **Atores:** leitor ou bibliotecário. **Pré-condição:** usuário autenticado. **Pós-condição:** resultados exibidos com quantidade disponível.
- **Fluxo:** selecionar “Pesquisar acervo”, informar título, autor, assunto ou ISBN e solicitar busca; sistema consulta e apresenta resultados em até 3 s (RNF02).
- **Exceções:** termo vazio solicita preenchimento; busca sem resultados apresenta mensagem clara.

#### UC4 — Reservar Obra
- **Ator:** leitor. **Pré-condições:** leitor autenticado e ativo; nenhum exemplar disponível. **Pós-condição:** reserva registrada na fila.
- **Fluxo:** localizar a obra (UC3), escolher “Reservar” e confirmar; sistema verifica indisponibilidade, registra a reserva e confirma.
- **Regras:** se houver exemplar disponível, orientar o leitor a realizar empréstimo; reserva disponibilizada fica retida por 48 h (RN08); leitor pode cancelar.

#### UC5 — Consultar Histórico
- **Ator:** leitor. **Pré-condição:** leitor autenticado. **Pós-condição:** empréstimos, reservas e pendências exibidos.
- **Fluxo:** leitor seleciona “Meu histórico”; sistema consulta os dados do usuário autenticado e exibe empréstimos ativos e encerrados, reservas e pendências.
- **Regra:** leitor só pode visualizar os próprios dados; se não houver registros, exibir mensagem informativa.

#### UC6 — Realizar Empréstimo
- **Ator principal:** bibliotecário; **ator secundário:** leitor. **Pré-condições:** bibliotecário autenticado, leitor ativo e sem pendências, exemplar disponível. **Pós-condição:** empréstimo registrado, exemplar indisponível e data de devolução informada.
- **Fluxo:** bibliotecário identifica leitor e exemplar e confirma; sistema verifica RN01, RN05 e RN07, registra empréstimo, calcula prazo (RN02) e exibe comprovante.
- **Exceções:** limite atingido, leitor impedido ou obra de consulta local recusam a operação com explicação.

#### UC7 — Registrar Devolução
- **Ator:** bibliotecário. **Pré-condições:** bibliotecário autenticado e empréstimo ativo para o exemplar. **Pós-condição:** exemplar disponível; penalidade eventualmente aplicada; próximo leitor notificado se houver reserva.
- **Fluxo:** informar exemplar e confirmar; sistema localiza o empréstimo, verifica atraso e aplica RN04, atualiza disponibilidade e notifica o próximo da fila, quando aplicável.
- **Exceção:** sem empréstimo ativo, a devolução não é registrada.

#### UC8 — Encerrar Sessão
- **Atores:** leitor, bibliotecário ou administrador. **Pré-condição:** usuário autenticado.
- **Fluxo:** usuário aciona logout; sistema encerra a sessão e redireciona à tela de login.

#### UC9 — Gerenciar Acervo
- **Atores:** bibliotecário ou administrador. **Pré-condição:** autenticação com perfil autorizado. **Pós-condição:** acervo atualizado.
- **Fluxo:** selecionar “Gerenciar acervo”, escolher cadastrar/editar/remover, informar ou alterar título, autor, ISBN, categoria, tipo e quantidade e confirmar; sistema valida, verifica permissões, grava e confirma.
- **Regras:** aplicar RN09 e RN10; remoção exige confirmação.

#### UC10 — Gerenciar Usuários
- **Ator:** administrador. **Pré-condição:** administrador autenticado. **Pós-condição:** conta criada, alterada ou desativada.
- **Fluxo:** selecionar “Gerenciar usuários”, escolher criar/editar/desativar, informar dados e perfil e confirmar; sistema valida, verifica unicidade do e-mail, grava e confirma.
- **Regras:** aplicar RN06; conta desativada não pode acessar o sistema.

#### UC11 — Gerar Relatórios
- **Ator:** administrador. **Pré-condição:** administrador autenticado. **Pós-condição:** relatório exibido.
- **Fluxo:** selecionar “Relatórios”, escolher obras mais emprestadas, atrasos ou movimentação mensal, informar período e solicitar geração; sistema consolida os dados e exibe o resultado.
- **Regras:** acesso exclusivo a administradores; informar quando não houver dados no período.

#### UC12 — Renovar Empréstimo
- **Ator principal:** bibliotecário; **ator secundário:** leitor. **Pré-condições:** bibliotecário autenticado e leitor com empréstimo ativo. **Pós-condição:** empréstimo renovado e nova data informada.
- **Fluxo:** identificar leitor, selecionar empréstimo ativo e confirmar; sistema verifica RN03, registra renovação, calcula novo prazo conforme RN02 e exibe comprovante.
- **Exceções:** recusar se atingido o limite de duas renovações, houver reserva pendente ou atraso, explicando o motivo.

## 6. Fluxos UML descritos

Os diagramas de sequência seguem o padrão **Boundary (Interface) – Control – Entity (Database)**.

### 6.1 Sequência: cadastrar leitor

1. Leitor inicia o cadastro e envia dados à interface.
2. Interface valida campos, formato do e-mail e tamanho mínimo da senha e encaminha os dados ao controle.
3. Controle consulta o banco para verificar e-mail existente.
4. Se duplicado, retorna erro; caso contrário, insere o leitor e retorna sucesso.
5. Interface apresenta a resposta ao leitor.

### 6.2 Sequência: login

1. Usuário informa e-mail e senha na interface.
2. Interface verifica preenchimento e aciona o controle.
3. Controle consulta o banco para validar as credenciais.
4. Credenciais válidas liberam o acesso e redirecionam à tela inicial; inválidas geram erro.

### 6.3 Sequência: realizar empréstimo

1. Bibliotecário informa leitor e exemplar na interface.
2. Interface envia solicitação ao controle.
3. Controle consulta situação do leitor, quantidade de empréstimos ativos, disponibilidade e tipo do exemplar.
4. Se alguma regra falhar, retorna o motivo; caso contrário, registra o empréstimo e marca o exemplar como emprestado.
5. Interface exibe comprovante e data de devolução.

### 6.4 Sequência: logout

1. Usuário aciona “Encerrar Sessão” na interface.
2. Controle registra o log da operação e atualiza o banco.
3. Interface redireciona à tela de login e informa o encerramento.

### 6.5 Atividade: realizar empréstimo

Início → identificar leitor → verificar cadastro ativo e ausência de pendências. Se inválido, exibir motivo e encerrar; caso válido, informar exemplar → verificar disponibilidade e permissão para empréstimo. Se inválido, sugerir reserva e encerrar; caso válido, verificar limite de três empréstimos. Se o limite foi atingido, recusar e encerrar; caso contrário, registrar empréstimo, calcular devolução, emitir comprovante e finalizar.

### 6.6 Atividade: login

Início → inserir e-mail e senha → validar dados → credenciais válidas? Se não, exibir erro e retornar à inserção; se sim, acessar o sistema → exibir tela inicial → fim.
