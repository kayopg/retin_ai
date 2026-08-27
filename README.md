# RetinAI

Plataforma de apoio médico em oftalmologia: acompanhamento pós-consulta e pós-cirurgia por
WhatsApp, mapeamento de risco clínico, atendimento assistido com prontuário estruturado por IA
e base de conhecimento anonimizada.

## Estrutura

| Caminho | O que é |
| --- | --- |
| `docs/proposta.html` | Proposta de software — problema, módulos, LGPD, regulatório, arquitetura, roadmap, riscos e decisões abertas |
| `docs/apresentacao.html` | Apresentação em 24 slides da mesma proposta, em linguagem simples, para apresentar ao médico |
| `docs/logo.html` | Quatro propostas de logomarca, com prós, contras e comportamento em escala |
| `docs/custos.html` | Calculadora do custo operacional do piloto, com premissas ajustáveis |
| `docs/esforco.html` | Estimativa de horas até o piloto, pacote por pacote, com projeção de calendário |
| `prototipo/index.html` | Protótipo navegável de 9 telas, arquivo único, sem dependências além do Google Fonts |

Todos são HTML autocontidos: basta abrir no navegador.

## Publicados

- Proposta — <https://claude.ai/code/artifact/e4c0ba7f-7134-445e-84a7-ddb296f2f386>
- Apresentação — <https://claude.ai/code/artifact/ef1191c4-9ffa-4d93-b56e-d3940ecb94bd>
- Marca — <https://claude.ai/code/artifact/299cac32-7ecd-43fb-8e55-d102aefabfbd>
- Custos — <https://claude.ai/code/artifact/66545bef-0a89-4e3a-a6b9-c6bfc0865685>
- Esforço — <https://claude.ai/code/artifact/c9a4f255-7e5e-4b92-bc9b-6579ee8e625d>
- Protótipo — <https://claude.ai/code/artifact/ff86657a-da29-4bd1-9e90-6e0635ecfe36>

## Apresentação — atalhos

`←` `→` navega · `S` abre o sumário · `F` tela cheia · `Home` / `End` vão ao começo e ao fim.
No celular, arrastar para o lado troca de slide. O endereço guarda o número do slide
(`…#12`), então dá para mandar um link direto para um ponto específico.

A regra de vocabulário da apresentação: **termo clínico fica preciso** (facectomia, PIO,
escavação, adesão), **termo de tecnologia vira português comum** — o médico é o especialista
de um lado e leigo do outro.

## Protótipo — responsividade

Testado de 320 px a 1920 px, nas 9 telas, sem estouro horizontal. Quatro pontos de quebra:

| Largura | O que muda |
| --- | --- |
| ≤ 1500 px | Colunas laterais dos workspaces encolhem |
| ≤ 1300 px | Coluna de contexto sobe para o topo; grades de 4 viram 2 |
| ≤ 1100 px | Barra lateral vira faixa de ícones de 64 px; workspaces viram coluna única |
| ≤ 720 px | Grades viram coluna única; subtítulo do cabeçalho some |
| ≤ 560 px | Cabeçalho vira só ícones; seletor de cor sai da barra (segue no `Ctrl K`) |

Altura usa `100dvh` com `100vh` de reserva, para o navegador de celular não cortar a barra
inferior quando a barra de endereço recolhe.

**Limite conhecido:** abaixo de 1100 px a barra lateral é uma faixa fixa de ícones — não há
menu retrátil. Em 375 px ela consome 17% da largura. Aceitável em protótipo; num produto de
verdade viraria gaveta.

## Protótipo — telas

Painel · Pacientes · Atendimento · Paciente · Central de risco · Conversas · Exames e imagem ·
Base de conhecimento · Privacidade e LGPD.

Atalhos: `Ctrl K` abre a paleta de comandos; o botão de tema alterna claro/escuro; a barra
lateral recolhe. Todos os dados são fictícios.

## Sistema de design

- **Tipografia** — IBM Plex Sans na interface, IBM Plex Mono em dados clínicos (PIO, AV, scores),
  Instrument Serif nos títulos da proposta e da apresentação.
- **Tema** — três estados (claro, escuro e sistema). O escuro é nativo, não uma inversão:
  sala de exame oftalmológico trabalha com luz baixa.

### Marca

**Disco óptico** — o disco com as arcadas vasculares emergindo dele, reduzido a três traços e um
círculo. A assimetria é anatômica: os vasos saem do disco e arqueiam para um lado só.

Duas versões, definidas como `<symbol>` e coloridas por `currentColor`:

| Símbolo | Quando usar |
| --- | --- |
| `#logo` | A partir de 20 px — completa, com o ramo fino |
| `#logo-sm` | Abaixo de 20 px — sem o ramo fino, traço mais encorpado |

A barra lateral do protótipo usa `#logo-sm` a 20 px. Assinatura: **Retin** em tom de texto,
**AI** na cor de marca, sem espaço nem hífen.

O ícone genérico de olho (`#i-eye`) continua no protótipo, mas só como ícone de interface —
título do visualizador de exames e etapa de conferência da base de conhecimento. Marca e ícone
de UI são coisas diferentes e não devem convergir.

### Paletas

Três opções no protótipo, trocáveis pelo ícone de cores na barra superior (ou pela paleta de
comandos). A escolha fica guardada no navegador. Cada paleta muda o conjunto — fundo, superfícies
e força das bordas — porque é isso, e não só a cor de destaque, que define o peso visual.

| Paleta | Marca (claro / escuro) | Fundo claro | "Estável" |
| --- | --- | --- | --- |
| Cobalto | `#2F5BD8` / `#7C9CFF` | `#EEF1F7` | `#07775F` verde-azulado |
| Azul claro | `#0F72B8` / `#4FB8EE` | `#ECF4FB` | `#0A7A45` verde |
| Verde claro | `#0E7C55` / `#43C98C` | `#EDF5F0` | `#0B62A6` azul |

Crítico, atenção e IA não mudam entre paletas — são sinais semânticos, não identidade.

O "estável" troca de matiz junto com a marca de propósito: na paleta verde a marca é verde,
então o sucesso vira azul para não virar tudo a mesma cor. Todas as combinações mantêm
contraste ≥ 4,5:1 e separação de matiz ≥ 47° entre marca e sucesso. A severidade também é
codificada em **forma** (losango, círculo, quadrado), não só em cor.

## Princípio de produto

A IA opera em três níveis e cada função pertence a exatamente um deles:

1. **Executa sozinha** — logística: envio de conteúdo aprovado, lembretes, coleta de check-in,
   organização de fila, auditoria.
2. **Propõe, o médico decide** — score de risco, rascunho de prontuário, achados em imagem.
   Toda saída carrega confiança, razão e versão do modelo; nada vira registro sem assinatura.
3. **Nunca** — diagnosticar como conclusão, prescrever, alterar dose, dar alta, responder
   pergunta clínica fora do protocolo. Nesses casos a IA para de conduzir e aciona o médico.
