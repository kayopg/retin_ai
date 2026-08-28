# Decisões — RetinAI

Registro em ordem cronológica inversa: a decisão mais recente primeiro.

Todas as entradas até aqui vêm de uma sequência contínua de trabalho entre 26 e 27 de
agosto de 2026. Dentro de cada dia, a ordem é a de ocorrência, não de horário registrado.

---

## 2026-08-27 — Linguagem dos documentos compartilhados escrita para quem vai ler

**Status:** Vigente

**Contexto**
Ao preparar a estimativa de esforço para envio ao médico, verificou-se que duas frases
tinham sido escritas presumindo que só o desenvolvedor as leria: "quem trava o cronograma é
a agenda do médico, não a sua" e "o projeto anda no ritmo dele". Verdadeiras e úteis, mas
lidas pelo próprio médico soam como atribuição de culpa.

**Decisão**
Documentos destinados ao médico nomeiam o fator, não a pessoa. O aviso passou a dizer
"quem determina a data são as horas clínicas". Antes de compartilhar qualquer documento,
lê-lo inteiro do ponto de vista do destinatário.

**Alternativas consideradas**
- *Deixar como estava*, por ser factualmente correto. Descartado: a informação sobrevive à reformulação, o desconforto não precisa sobreviver junto.
- *Remover o aviso de gargalo*. Descartado: é a informação mais acionável da página — diz ao médico que concentrar as horas dele no início é o que encurta o prazo.

**Consequências**
Toda página com dois públicos possíveis precisa de uma leitura extra antes de sair. Duas
frases já haviam vazado de contexto interno para documentos destinados ao médico, o que
sugere que revisão focada só em erro técnico não pega esse tipo de problema.

---

## 2026-08-27 — Horas do médico não abatem o pagamento ao desenvolvedor

**Status:** Vigente

**Contexto**
Levantou-se a possibilidade de descontar as 88 horas clínicas do médico contra as 493 horas
de engenharia, e o médico pagar apenas a diferença. A intenção era ser justo com a
contribuição dele.

**Decisão**
As horas do médico não abatem valor em dinheiro. Em relação de prestação de serviço, elas
são insumo do produto que ele está comprando — como em qualquer projeto de software o
cliente dedica tempo a reuniões e validação, sem que isso reduza o preço. Em relação
societária, elas são contribuição de sócio e já estão refletidas na participação.

**Alternativas consideradas**
- *Abater as horas.* Descartado: creditaria a contribuição do médico duas vezes, uma reduzindo o pagamento e outra justificando a participação.
- *Ignorar as horas dele.* Descartado: são 88 horas bloqueantes; sem elas o cronograma para.

**Consequências**
As horas clínicas passam a constar como compromisso com prazo no acordo, não como crédito.
O reconhecimento da contribuição do médico é expresso na participação societária, não no
valor cobrado.

---

## 2026-08-27 — O projeto é feito fora do horário comercial

**Status:** Vigente

**Contexto**
O roadmap da proposta estimava as fases em semanas de calendário, o que só faz sentido para
dedicação integral. O desenvolvedor trabalha em horário comercial em outra empresa.

**Decisão**
A engenharia acontece em 2 a 3 horas por dia útil mais cerca de 4 horas no fim de semana —
entre 14 e 19 horas por semana. A margem sobre a estimativa subiu de 30% para 40%, porque
hora fragmentada rende menos que hora contínua. O piloto enxuto passou de 458 para 493
horas, e o completo de 608 para 655.

**Alternativas consideradas**
- *Manter a margem de 30%.* Descartado: os 30% cobrem erro de estimativa, não o custo de recarregar o contexto do problema em blocos de duas horas à noite.
- *Não declarar a limitação.* Descartado: assumir prazo incompatível com a disponibilidade real gera um acordo que não se cumpre.

**Consequências**
Prazo passa a ser consequência de horas disponíveis, não promessa de data — qualquer
contrato precisa tratá-lo como estimativa, sem multa por atraso. Acima de 19 horas semanais
o ganho desaparece, porque as 88 horas clínicas passam a determinar a data. A sociedade só
faz sentido se existir caminho plausível para dedicação integral no futuro.

---

## 2026-08-27 — Parecer regulatório adiado para antes da primeira venda

**Status:** Vigente
**Supera:** 2026-08-26 — Parecer regulatório contratado na Fase 0

**Contexto**
A documentação estava contraditória: a estimativa de esforço dizia que o parecer não
bloqueia o piloto, enquanto a calculadora de custo o listava como custo único "antes da
Fase 1", somando R$ 13 a 40 mil ao início do projeto.

**Decisão**
Na Fase 0 entra apenas uma consulta curta de enquadramento — algumas horas de especialista
— para confirmar que o piloto pode rodar como uso interno. O parecer completo fica para
quando a primeira venda virar meta concreta. O custo único para chegar ao primeiro paciente
caiu de R$ 13–40 mil para R$ 1,5–4,3 mil, restando o termo de consentimento redigido por
advogado e o registro de domínio.

**Alternativas consideradas**
- *Contratar o parecer completo na Fase 0.* Descartado: o gatilho regulatório é o módulo de análise de imagem, que é a Fase 4 e não existe no piloto. Pagar cinco dígitos por um parecer sobre um módulo que talvez nunca seja construído é gasto antecipado sem retorno.
- *Ignorar o assunto até a venda.* Descartado por duas razões: o parecer leva semanas e não pode ser deixado para o mês da venda; e a central de risco também é software de apoio à decisão clínica, então a leitura de que uso interno não se regulariza é a provável, não uma certeza.

**Consequências**
O dinheiro grande só entra depois que o piloto responder se a ideia funciona. Em
contrapartida, é preciso disciplina para contratar o parecer com antecedência real da
primeira venda, e não quando ela aparecer.

---

## 2026-08-27 — Tarifa de WhatsApp corrigida; não existe desconto para saúde

**Status:** Vigente

**Contexto**
Surgiu a informação de que mensagens de WhatsApp na área da saúde teriam custo menor. A
calculadora de custo usava US$ 0,008 por mensagem e cobrava todas as mensagens enviadas.

**Decisão**
Verificado na documentação oficial da Meta: não existe desconto por área de atuação. O
preço varia por categoria da mensagem, país do destinatário e volume mensal. A tarifa foi
corrigida para US$ 0,0068 (utilidade, Brasil) e o cálculo passou a separar mensagens
cobradas de mensagens gratuitas.

**Alternativas consideradas**
- *Aceitar a informação e aplicar um desconto.* Descartado: não há base na documentação do fornecedor.
- *Descartar a informação como equivocada.* Descartado: havia fundo verdadeiro em dois mecanismos reais — a categoria "utilidade" custa cerca de nove vezes menos que "marketing", e mensagens dentro da janela de atendimento de 24 horas são gratuitas, inclusive modelos de utilidade.

**Consequências**
O modelo de custo passou a contabilizar a janela gratuita, que estava sendo ignorada. Como
o protocolo é feito de perguntas que pedem resposta, parte relevante da conversa cai nessa
janela. Existem ainda faixas de desconto por volume mensal, que reduzem o custo unitário
conforme a operação cresce.

---

## 2026-08-26 — Comercialização escalonada em três etapas

**Status:** Vigente
**Supera:** 2026-08-26 — Comercialização registrada como premissa única

**Contexto**
A pergunta "é para a sua clínica ou para vender a outras?" estava listada como decisão
aberta na proposta, mas já estava decidida. A primeira versão da correção tratou a venda a
órgãos públicos como certeza, o que pesou o documento inteiro para uma etapa ainda
especulativa.

**Decisão**
Três etapas de mercado, cada uma condicionada à anterior. Etapa 1: piloto sem
comercialização, na clínica do médico — comprometida. Etapa 2: venda a clínicas
oftalmológicas particulares — comprometida. Etapa 3: venda a órgãos públicos — hipótese,
não plano.

**Alternativas consideradas**
- *Tratar a Etapa 3 como fase do projeto.* Descartado a pedido: ainda é uma ideia, e decisões que só valem para ela não devem custar prazo hoje.
- *Omitir a Etapa 3.* Descartado: ela muda o desenho de precificação — preço por assento fixo não tem tradução para edital público — e é barato não fechar essa porta.

**Consequências**
A tabela de exigências regulatórias passou a ter uma coluna por etapa, deixando explícito
que a Etapa 1 quase não exige nada. Duas coisas continuam obrigatórias desde já porque são
caras demais para refazer: o isolamento por clínica no banco de dados e a trilha de
auditoria.

---

## 2026-08-26 — Divisão de trabalho em três blocos com dono explícito

**Status:** Vigente

**Contexto**
A seção "O que eu preciso de você" listava seis itens sem dono declarado, sob um título que
dizia "a engenharia é comigo". Além de ambíguo, num documento de sociedade uma lista apenas
do que o outro deve entregar lê como cobrança.

**Decisão**
Três blocos nomeados: o que é do desenvolvedor, o que é do médico, e o que é decisão dos
dois. A decisão sobre o caminho regulatório saiu da coluna do médico — é decisão de
sociedade, não tarefa clínica.

**Alternativas consideradas**
- *Manter a lista única e apenas rotulá-la.* Descartado: não resolveria o problema de tom, só o de clareza.

**Consequências**
A seção passou a se chamar "Divisão de trabalho". O fecho mudou de "sem isso o produto vira
um chatbot genérico" para uma constatação sobre a natureza do trabalho: a parte de
engenharia escala contratando gente, a parte clínica não escala de jeito nenhum.

---

## 2026-08-26 — Marca: disco óptico com arcadas vasculares

**Status:** Vigente

**Contexto**
O símbolo em uso no protótipo era o ícone de olho padrão de biblioteca, o mesmo que aparece
em campo de senha e botão de visualizar. Quatro conceitos foram desenhados a partir do que
o oftalmologista vê no exame.

**Decisão**
Conceito 1 — o disco óptico com as arcadas vasculares emergindo dele, reduzido a três
traços e um círculo. Aplicado no protótipo, na proposta e na apresentação.

**Alternativas consideradas**
- *Escavação* — anel e cúpula, representando a relação escavação/disco do glaucoma. Descartada como principal: significado exclusivo do produto, mas forma comum, presente em centenas de marcas. Registrada como a opção segura se a prioridade mudar.
- *Fenda* — o feixe da lâmpada de fenda cortando a córnea. Descartada: sem contexto pode ser lida como símbolo de proibição ou obturador de câmera.
- *Íris* — estrias radiais em volta da pupila. Descartada: some em tamanho pequeno; exigiria um desenho diferente, e não apenas simplificado, para uso reduzido.
- *Manter o ícone genérico.* Descartado: serve para navegar, não para assinar um produto.

**Consequências**
Duas versões definidas: a completa a partir de 20 px e uma reduzida sem o ramo fino para
tamanhos menores. O ícone genérico de olho permanece no protótipo em dois lugares, como
ícone de interface — marca e ícone de UI são coisas distintas e não devem convergir.

---

## 2026-08-26 — Três paletas de cor como opção, nenhuma adotada

**Status:** Vigente

**Contexto**
A paleta cobalto original foi considerada escura demais, e foram solicitadas alternativas
mais leves em azul claro e verde claro.

**Decisão**
As três paletas foram implementadas e ficam alternáveis no protótipo, com a escolha
guardada no navegador. Cada paleta redefine o conjunto — fundo, superfícies, força das
bordas e cor de marca — porque é o conjunto, e não só a cor de destaque, que define o peso
visual. **Nenhuma foi adotada como definitiva.**

**Alternativas consideradas**
- *Trocar apenas a cor de destaque.* Descartado: o que faz a interface parecer pesada é o fundo e a força das bordas, não a cor de marca isolada.
- *Escolher uma e aplicar.* Não feito: a escolha é do projeto, não da implementação.

**Consequências**
O token de "estável" troca de matiz junto com a marca: na paleta verde a marca é verde e o
sucesso vira azul, para o painel não ficar monocromático e perder a separação de sinal.
Todas as combinações mantêm contraste mínimo de 5,1:1 e separação de matiz de 47 a 61 graus
entre marca e sucesso. Enquanto a escolha não for feita, a proposta e a apresentação
seguem em cobalto.

---

## 2026-08-26 — Repositório em github.com/kayopg/retin_ai

**Status:** Vigente

**Contexto**
O projeto vivia apenas em disco local.

**Decisão**
Versionado em `github.com/kayopg/retin_ai`, branch `main`. O repositório estava vazio, sem
risco de sobrescrever conteúdo.

**Consequências**
O repositório é público. Material de negociação e PDFs gerados ficam fora dele, por
`.gitignore`.

---

## Propostas não confirmadas

As entradas abaixo são recomendações registradas na documentação que nunca foram
confirmadas. Estão aqui para não serem confundidas com decisões.

---

## 2026-08-27 — Escopo enxuto para o piloto

**Status:** Proposta não confirmada

**Contexto**
O roadmap coloca o módulo de atendimento antes do monitoramento. Ao estimar as horas,
verificou-se que ele não é pré-requisito técnico: para acompanhar um pós-operatório basta
saber quem é o paciente, que procedimento fez e quando.

**Proposta**
Levar ao piloto apenas o núcleo de monitoramento — 493 horas, cerca de 7,8 meses a 16 horas
por semana — adiando o prontuário estruturado e o histórico longitudinal.

**Alternativas consideradas**
- *Escopo completo*, como está no roadmap — 655 horas, cerca de 10,1 meses. A favor: nada é refeito e a triagem já nasce com histórico. Contra: adia em meses a única pergunta que o piloto existe para responder.

**Consequências se adotada**
Chega ao primeiro paciente cerca de dois meses antes. Há retrabalho no cadastro, e a
triagem opera sem histórico rico durante o piloto.

---

## 2026-08-27 — Precificação por plataforma mais faixa de pacientes

**Status:** Proposta não confirmada

**Contexto**
A proposta precisava de um modelo de cobrança para clínicas clientes. O custo de servir uma
clínica cresce com pacientes monitorados, não com médicos cadastrados.

**Proposta**
Cenário B — mensalidade base por clínica com usuários à vontade, mais faixa de pacientes em
acompanhamento ativo, com faixas largas.

**Alternativas consideradas**
- *Por médico.* Descartada como recomendação: simples de vender, mas cobra pela coisa errada — o cliente compra paciente acompanhado, não assento. Também não tem tradução para edital público.
- *Por episódio de acompanhamento.* Descartada: alinhamento direto entre preço e valor, mas não cobre doença crônica, que não tem episódio — justamente onde o produto mais previne perda irreversível.
- *Cobrar por mensagem enviada.* Descartada: cobraria o cliente exatamente pela ação que o produto existe para incentivar.

**Consequências se adotada**
As faixas precisam ser largas o bastante para que o médico nunca pense no custo ao decidir
sobre um paciente. A conversa sobre faixa acontece uma vez por ano com a administração da
clínica, nunca no consultório.

---

## 2026-08-26 — Caminho regulatório de apoio à decisão no piloto

**Status:** Proposta não confirmada

**Contexto**
O módulo de análise de imagem pode ser enquadrado como dispositivo médico pela RDC
657/2022.

**Proposta**
Apoio à decisão com validação obrigatória durante o piloto — o sistema marca regiões e dá
grau de confiança, sem emitir conclusão, e nenhum laudo existe sem assinatura médica. O
registro na ANVISA passa a ser necessário antes da primeira venda.

**Alternativas consideradas**
- *Buscar o registro desde o início.* Descartada para o piloto: custo e prazo relevantes para um módulo que é a última fase do plano.

**Consequências se adotada**
O módulo de análise de imagem permanece como última fase, para poder ser adiado sem travar
o produto. Depende de confirmação por parecer não contratado.

---

## 2026-08-26 — Base de conhecimento isolada por clínica na primeira venda

**Status:** Proposta não confirmada

**Contexto**
Um acervo comum entre clínicas é mais valioso — faz o produto melhorar a cada cliente novo
— e é o único diferencial que não se copia. Também esbarra no art. 11, §4º da LGPD e no
papel de operador de dados.

**Proposta**
Começar com acervo isolado por clínica, abrindo o acervo comum apenas com parecer jurídico
e autorização contratual da clínica de origem.

**Alternativas consideradas**
- *Acervo comum desde o início.* Descartada: se der errado juridicamente, não é reversível. Isolado é.

**Consequências se adotada**
O produto perde parte do efeito de rede até que a questão jurídica seja resolvida.
