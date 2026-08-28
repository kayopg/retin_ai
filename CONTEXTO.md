# RetinAI

_Atualizado em: 2026-08-28_

## O que é

Um oftalmologista em especialização identificou um problema na própria prática: entre a
alta e o retorno, ninguém acompanha o paciente. No pós-operatório, o paciente sai com um
frasco de colírio, um curativo e uma explicação rápida — não sabe distinguir o que é
esperado do que é sinal de alarme, executa a técnica errado, e demora a procurar ajuda.
Na doença crônica o problema se inverte: glaucoma e retinopatia não doem, a adesão ao
tratamento cai sem que ninguém perceba, e a descoberta vem na consulta seguinte, meses
depois, com perda já instalada.

O RetinAI se propõe a fechar esse intervalo. Um assistente acompanha o paciente pelo
WhatsApp seguindo o protocolo escrito pelo médico, envia orientações e vídeos no dia
certo do pós-operatório, lê as respostas, e escala para o médico quando algo foge do
previsto. Dentro do consultório, transforma a anotação livre da consulta em prontuário
estruturado, com o histórico do paciente ao lado.

O produto tem quatro módulos definidos pelo médico: (I) atendimento assistido que gera
prontuário estruturado com histórico longitudinal; (II) acompanhamento pós-consulta e
pós-cirurgia por WhatsApp, com orientações, vídeos de técnica e teleconsulta; (III) mapa
de risco que ordena quem precisa de atenção; (IV) base de conhecimento alimentada pelos
próprios médicos, obrigatoriamente anonimizada por exigência de LGPD e sigilo médico.

O destinatário imediato é a clínica do médico envolvido no projeto. O destino declarado é
a venda a outras clínicas oftalmológicas particulares.

## Situação atual

**Nenhuma linha do produto foi escrita.** O que existe hoje é documentação e um protótipo
de interface — material para decidir, não software funcionando.

Existem e estão completos:

- **Proposta de software** (`docs/proposta.html`), 14 seções: problema, quatro módulos,
  duas jornadas de paciente, governança de IA, LGPD e sigilo médico, caminho regulatório,
  arquitetura proposta, roadmap em cinco fases, métricas, riscos, modelo de negócio,
  divisão de trabalho e decisões abertas.
- **Apresentação** (`docs/apresentacao.html`), 24 slides com a mesma proposta em linguagem
  simplificada, para apresentar ao médico.
- **Protótipo navegável** (`prototipo/index.html`), 9 telas clicáveis com dados fictícios.
  Não tem back-end, banco de dados nem integração — é interface para demonstração.
- **Propostas de marca** (`docs/logo.html`), quatro conceitos com prós, contras e
  comportamento em escala.
- **Calculadora de custo operacional** (`docs/custos.html`), com premissas ajustáveis.
- **Estimativa de esforço** (`docs/esforco.html`), 28 pacotes de trabalho estimados
  individualmente.

Está pela metade: a identidade visual. A marca foi escolhida e aplicada; a paleta de cores
não foi definida — existem três opções implementadas e alternáveis no protótipo, nenhuma
adotada como definitiva.

Não foi começado: qualquer implementação. Também não foram escritos os protocolos clínicos,
que são o insumo bloqueante da Fase 0.

## Premissas

- O médico consegue escrever cinco ou seis protocolos clínicos e definir os sinais de alarme por procedimento.
- O paciente responde a mensagens de WhatsApp durante o pós-operatório.
- A percepção do problema é válida: pacientes efetivamente perdem contato com a clínica no intervalo entre a alta e o retorno.
- Software de apoio à decisão de uso interno da própria instituição de saúde tem tratamento regulatório diferente de software distribuído a terceiros. Não foi confirmado por parecer.
- A Etapa 1 (piloto sem comercialização) quase não exige conformidade regulatória. Não foi confirmado por parecer.
- Meta cobra mensagem de WhatsApp por categoria, país e volume mensal — não por setor de atuação. Verificado na documentação oficial da Meta em 2026-08-27.

## Restrições

- **Disponibilidade de engenharia: 14 a 19 horas por semana.** O desenvolvedor trabalha em horário comercial em outra empresa; o projeto é feito em 2 a 3 horas por dia útil mais cerca de 4 horas no fim de semana. Declarado pelo usuário em 2026-08-27.
- **Sem capital para investir.** O desenvolvedor declarou não ter reserva para aportar no projeto. Declarado em 2026-08-27.
- **Disponibilidade clínica: cerca de 2 horas por semana do médico**, estimadas em 88 horas até o piloto. Acima de 19 horas semanais de engenharia, as horas clínicas passam a determinar a data de entrega.
- **LGPD.** Dados de saúde são dado pessoal sensível. A base de conhecimento precisa ser anonimizada; o consentimento para o canal de WhatsApp é separado do consentimento de atendimento.
- **Art. 11, §4º da LGPD** veda comunicação e uso compartilhado de dados de saúde com objetivo de vantagem econômica, o que afeta o desenho da base de conhecimento comum entre clínicas.
- **CFM** exige guarda de prontuário por 20 anos.
- **ANVISA, RDC 657/2022.** O módulo de análise de imagem pode ser enquadrado como dispositivo médico. Origem: legislação; enquadramento não confirmado por parecer.
- **Meta.** A integração oficial do WhatsApp exige CNPJ e verificação de negócio antes de sair do modo de teste. Isso torna a formalização societária uma dependência de cronograma.
- **Mensagens fora da janela de atendimento de 24 h são cobradas.** Utilidade no Brasil custa cerca de US$ 0,0068; dentro da janela, é gratuito.

## Escopo

- Cadastro de paciente com procedimento, data e consentimento registrado.
- Motor de protocolo: agendamento e disparo de mensagens conforme o dia do pós-operatório.
- Integração com a API oficial do WhatsApp, incluindo modelos de mensagem aprovados pela Meta.
- Triagem por IA das respostas do paciente, com detecção de sinal de alarme.
- Cálculo de risco e central de risco ordenada por urgência.
- Hospedagem e entrega de vídeos curtos gravados pelo médico.
- Atendimento assistido com prontuário estruturado por IA e histórico longitudinal.
- Conferência automática entre os achados da consulta e o histórico anterior.
- Assinatura digital de prontuário com validade legal.
- Teleconsulta com registro automático.
- Base de conhecimento anonimizada, alimentada pelos casos da própria clínica.
- Análise de imagem de retina com marcação de achados e grau de confiança.
- Isolamento por clínica no banco de dados desde a primeira linha de código.
- Trilha de auditoria de acessos.

## Fora de escopo

- **Diagnóstico automático.** A IA nunca fecha diagnóstico, prescreve, altera dose ou dá alta. Fronteira definida pelo médico e registrada como princípio de produto.
- **Resposta a pergunta clínica fora do protocolo.** Nesses casos o assistente para de conduzir a conversa e aciona o médico.
- **Envio de laudo, imagem de exame, hipótese diagnóstica ou receita pelo WhatsApp.** A mensagem trafega por servidores de terceiros; esse conteúdo abre dentro do sistema, com autenticação.
- **Identificação do paciente na base de conhecimento.** Idade vira faixa etária e data vira trimestre, porque a combinação de idade exata, data exata e diagnóstico volta a apontar para uma pessoa.
- **Venda a órgãos públicos no horizonte atual.** Registrada como hipótese, não como fase do projeto. Decidido em 2026-08-27.
- **Menu retrátil no protótipo abaixo de 1100 px.** A barra lateral vira faixa fixa de ícones de 64 px. Aceitável em protótipo; seria refeito em produto.
- **Curadoria dos 200 a 300 casos do acervo antes do piloto.** É trabalho de Fase 3 e não bloqueia o piloto.

## Envolvidos

- **Ari Gomes** (Arimanoel de Matos Gomes) — produto e engenharia. Responsável por arquitetura, código, integrações, infraestrutura, medição do piloto e pela condução do parecer regulatório e da assessoria jurídica.
- **Dr. Miguel** — médico oftalmologista em especialização. Origem da percepção do problema e da iniciativa do projeto. Responsável pelos protocolos clínicos, sinais de alarme, vídeos, casos laudados e validação clínica contínua. Sua clínica é o campo de prova do piloto.
- **Meta / WhatsApp Business Platform** — fornecedor do canal de mensagens. Exige verificação de negócio com CNPJ.
- **Anthropic** — fornecedor de modelo de IA. Conta de API pré-paga, sem mensalidade.
- **Consultoria regulatória** — Não definido. Prevista, não contratada.
- **Assessoria jurídica** — Não definido. Prevista, não contratada.
- **Contador** — Não definido. Necessário se houver abertura de CNPJ.

## Ambiente técnico

**O que existe no repositório** são documentos HTML autocontidos, sem etapa de build e sem
dependências além do Google Fonts. Abrir no navegador basta.

- Repositório: `github.com/kayopg/retin_ai`, branch `main`.
- Tipografia: IBM Plex Sans na interface, IBM Plex Mono em dados clínicos e números, Instrument Serif em títulos.
- Tema: três estados — claro, escuro e sistema — resolvidos por tokens CSS.
- Os documentos também estão publicados como artefatos privados no claude.ai. As URLs estão no `README.md`. Artefato nasce privado: compartilhar exige liberar pelo menu da própria página, e republicar não resolve acesso.

**Arquitetura do produto** — proposta na seção 08 de `docs/proposta.html`, nada implementado:
banco relacional com busca vetorial, isolamento por clínica no nível da linha, dois cofres
de dados separados (identificação e acervo anônimo), integração com a API oficial do
WhatsApp Cloud, e modelos de IA para estruturação de prontuário, triagem de resposta e
consulta ao acervo.

**Custo operacional estimado do piloto:** cerca de R$ 280 por mês para 25 pacientes em
acompanhamento, com uma interação a cada dois dias. Detalhamento e premissas ajustáveis em
`docs/custos.html`.

## Próximo passo

Sentar duas horas com o Dr. Miguel e escrever o protocolo de pós-facectomia: o que enviar,
em que dia, e o que fazer com cada resposta possível do paciente. É o insumo que destrava
a Fase 0 e não depende de nenhuma outra decisão estar fechada.

## Em aberto

- **Modelo comercial entre os envolvidos.** Se o projeto será uma sociedade ou uma contratação não está definido. Três estruturas foram mapeadas e existe material de apoio fora deste repositório, deliberadamente. Nenhuma foi escolhida.
- **Paleta de cores definitiva.** Três opções implementadas no protótipo — cobalto, azul claro e verde claro. Nenhuma adotada.
- **Escopo do piloto.** Existem duas versões estimadas: enxuto, só o monitoramento, 493 horas; e completo, incluindo prontuário estruturado, 655 horas. Não decidido.
- **Enquadramento regulatório do módulo de análise de imagem.** Depende de parecer não contratado.
- **Base de conhecimento isolada por clínica ou comum a todas.** Depende de parecer jurídico não contratado.
- **Modelo de precificação do produto** para clínicas clientes. Três cenários descritos na seção 12 da proposta, nenhum escolhido.
- **Qual procedimento entra no piloto.** Não decidido.
- **Google Meet ou sala de vídeo própria** para teleconsulta. Não decidido.
- **Formalização societária.** Não definida — e bloqueia a verificação de negócio na Meta, que por sua vez bloqueia o WhatsApp em produção.
- **Custo real por paciente monitorado.** Só existe estimativa. A medição depende do piloto.
- **Protocolos clínicos, sinais de alarme e vídeos.** Não escritos nem gravados.
