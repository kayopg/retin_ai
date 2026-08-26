# RetinAI

Plataforma de apoio médico em oftalmologia: acompanhamento pós-consulta e pós-cirurgia por
WhatsApp, mapeamento de risco clínico, atendimento assistido com prontuário estruturado por IA
e base de conhecimento anonimizada.

## Estrutura

| Caminho | O que é |
| --- | --- |
| `docs/proposta.html` | Proposta de software — problema, módulos, LGPD, regulatório, arquitetura, roadmap, riscos e decisões abertas |
| `prototipo/index.html` | Protótipo navegável de 9 telas, arquivo único, sem dependências além do Google Fonts |

Ambos são HTML autocontidos: basta abrir no navegador.

## Publicados

- Proposta — <https://claude.ai/code/artifact/e4c0ba7f-7134-445e-84a7-ddb296f2f386>
- Protótipo — <https://claude.ai/code/artifact/ff86657a-da29-4bd1-9e90-6e0635ecfe36>

## Protótipo — telas

Painel · Pacientes · Atendimento · Paciente · Central de risco · Conversas · Exames e imagem ·
Base de conhecimento · Privacidade e LGPD.

Atalhos: `Ctrl K` abre a paleta de comandos; o botão de tema alterna claro/escuro; a barra
lateral recolhe. Todos os dados são fictícios.

## Sistema de design

- **Cor** — cobalto `#2F5BD8` sobre neutros de viés frio (`#EEF1F7` claro / `#080D1A` escuro).
  Sinais semânticos separados da cor de marca: crítico `#C33449`, atenção `#9C6206`,
  estável `#07775F`, IA `#6141C2`.
- **Tipografia** — IBM Plex Sans na interface, IBM Plex Mono em dados clínicos (PIO, AV, scores),
  Instrument Serif nos títulos da proposta.
- **Tema** — três estados (claro, escuro e sistema). O escuro é nativo, não uma inversão:
  sala de exame oftalmológico trabalha com luz baixa.

## Princípio de produto

A IA opera em três níveis e cada função pertence a exatamente um deles:

1. **Executa sozinha** — logística: envio de conteúdo aprovado, lembretes, coleta de check-in,
   organização de fila, auditoria.
2. **Propõe, o médico decide** — score de risco, rascunho de prontuário, achados em imagem.
   Toda saída carrega confiança, razão e versão do modelo; nada vira registro sem assinatura.
3. **Nunca** — diagnosticar como conclusão, prescrever, alterar dose, dar alta, responder
   pergunta clínica fora do protocolo. Nesses casos a IA para de conduzir e aciona o médico.
