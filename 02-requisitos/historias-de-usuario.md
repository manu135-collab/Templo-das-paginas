# Histórias de Usuário

Histórias correspondentes aos 14 requisitos funcionais fornecidos. Estimativas mantidas conforme a especificação original.

| ID | Título | História | Prioridade / estimativa | Critérios de aceitação |
|---|---|---|---|---|
| RF01 | Realizar login | Como usuário, quero acessar o sistema por login para usar suas funcionalidades de forma segura e personalizada. | Essencial / 5 pontos | Informar e-mail e senha válidos; autenticação em até 2 s; credenciais inválidas exibem erro. |
| RF02 | Cadastrar leitor | Como visitante, quero me cadastrar para poder retirar obras por empréstimo e efetuar reservas. | Essencial / 8 pontos | Nome, e-mail, senha e documento são obrigatórios; e-mail duplicado rejeitado (RN06); após cadastro, redirecionar ao login. |
| RF03 | Encerrar sessão | Como usuário, quero encerrar minha sessão para impedir que outra pessoa acesse minha conta no mesmo dispositivo. | Essencial / 3 pontos | Invalidar sessão, redirecionar ao login e registrar a operação em log. |
| RF04 | Gerenciar acervo | Como bibliotecário, quero cadastrar, editar e remover obras e exemplares para manter o acervo atualizado e confiável. | Essencial / 13 pontos | Alterações somente por bibliotecários/administradores (RN09); obra com título, autor, ISBN, categoria, tipo e quantidade; não remover exemplar emprestado (RN10); exigir confirmação de remoção. |
| RF05 | Pesquisar acervo | Como leitor, quero buscar obras por título, autor, assunto ou ISBN para verificar disponibilidade. | Essencial / 8 pontos | Resultados em até 3 s, com quantidade disponível; exibir mensagem clara sem resultados. |
| RF06 | Realizar empréstimo | Como bibliotecário, quero registrar empréstimo para controlar a posse e o prazo de devolução de cada obra. | Essencial / 13 pontos | Validar RN01, RN05 e RN07; calcular data conforme RN02; exemplar passa a “emprestado”. |
| RF07 | Registrar devolução | Como bibliotecário, quero registrar a devolução para disponibilizar a obra e identificar atrasos. | Essencial / 8 pontos | Exemplar volta a disponível; aplicar eventual penalidade (RN04); notificar leitor correspondente se houver reserva. |
| RF08 | Renovar empréstimo | Como bibliotecário, quero renovar empréstimo ativo a pedido do leitor para ampliar o prazo sem nova retirada. | Importante / 5 pontos | Máximo de 2 renovações; recusar com reserva pendente ou atraso (RN03); novo prazo conforme RN02; informar motivo de recusa. |
| RF09 | Reservar obra | Como leitor, quero reservar uma obra emprestada para ser informado quando estiver disponível. | Importante / 8 pontos | Reservar somente sem exemplar disponível; expiração conforme RN08; leitor pode cancelar. |
| RF10 | Controlar atrasos | Como bibliotecário, quero que empréstimos vencidos sejam identificados e penalizados automaticamente. | Importante / 8 pontos | Verificação diária; bloqueio conforme RN04; consulta da lista de atrasos. |
| RF11 | Notificar leitor | Como leitor, quero receber e-mails sobre vencimentos próximos e disponibilidade de reservas. | Desejável / 8 pontos | E-mail de disponibilidade após devolução informa prazo de 48 h (RN08); antecedência do aviso de vencimento será definida com a biblioteca. |
| RF12 | Consultar histórico | Como leitor, quero consultar meus empréstimos, reservas e pendências para acompanhar minha situação na biblioteca. | Importante / 5 pontos | Listar empréstimos ativos e encerrados com datas, reservas e pendências; mostrar apenas dados próprios. |
| RF13 | Gerenciar usuários | Como administrador, quero criar, editar e desativar contas para controlar quem acessa o sistema e com qual perfil. | Importante / 8 pontos | Atribuir perfil; e-mail único (RN06); conta desativada não acessa o sistema. |
| RF14 | Gerar relatórios | Como administrador, quero gerar relatórios de obras mais emprestadas, atrasos e movimentação mensal para apoiar decisões. | Desejável / 8 pontos | Escolher tipo e período; exibir resultado em tela; acesso exclusivo a administrador. |

## Template

**Título:** [Ação / requisito relacionado]  
**ID:** [RFXX]  
**Prioridade / estimativa:** [prioridade] / [pontos]  
**Como** [perfil], **quero** [objetivo], **para** [benefício].

**Critérios de aceitação:**

- Dado [contexto], quando [ação], então [resultado verificável].
- [Regra de negócio ou requisito não funcional relacionado].
