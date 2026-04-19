# Assistentes Personalizados

Coleção de **instruções completas para assistentes especializados** em investigação, perícia, segurança digital, privacidade e análise técnica.

Este repositório não reúne prompts curtos ou genéricos. Cada arquivo foi escrito como uma arquitetura operacional completa, com identidade, escopo, guardrails, protocolos de resposta, formatos de saída e fluxos de trabalho próprios.

> Repositório pensado para uso prático em plataformas que suportam instruções longas, estruturadas e com comportamento mais consistente.

## O que você vai encontrar aqui

- **Papéis bem definidos** para cada assistente.
- **Regras de escopo e confidencialidade** para reduzir desvios de comportamento.
- **Guardrails e protocolos anti-abuso** para manter consistência operacional.
- **Formatos de saída padronizados** para uso prático em contexto profissional.
- **Fluxos operacionais completos** prontos para copiar em ambientes compatíveis.

## Sumário

- [Compatibilidade recomendada](#compatibilidade-recomendada)
- [Importante sobre o ChatGPT](#importante-sobre-o-chatgpt)
- [Uso rápido](#uso-rápido)
- [Catálogo rápido](#catálogo-rápido)
- [Resumo dos assistentes](#resumo-dos-assistentes)
- [Diferenciais deste repositório](#diferenciais-deste-repositório)
- [Para quem é](#para-quem-é)
- [Estrutura do repositório](#estrutura-do-repositório)

## Compatibilidade recomendada

Estas instruções foram pensadas para uso em:

- `GEMs` do Gemini
- `Projects` do Claude

## Importante sobre o ChatGPT

Estas instruções **não funcionam bem no ChatGPT/GPTs** porque os GPTs possuem um limite de aproximadamente **8 mil caracteres** no campo de instruções.

Como estes assistentes foram projetados com prompts longos e detalhados, o conteúdo precisa de um ambiente que aceite instruções extensas com mais fidelidade. Por isso, o uso recomendado é em:

- `Gemini (GEMs)`
- `Claude (Projects)`

## Uso rápido

1. Escolha o assistente desejado.
2. Abra o arquivo `.md` correspondente.
3. Copie o conteúdo completo das instruções.
4. Cole no campo de instruções do seu `GEM` no Gemini ou no `Project` do Claude.
5. Use o arquivo como instrução-base do assistente, sem resumir trechos importantes.
6. Se o assistente mencionar uma base de conhecimento complementar, carregue também esse material no projeto correspondente.

## Catálogo rápido

| Assistente | Área principal | Melhor uso | Arquivo |
|---|---|---|---|
| Sistema Pericial ALPR v4.1 | Perícia veicular | Análise de placas e indícios de adulteração | `Sistema Pericial ALPR v4.1.md` |
| CYBERSHIELD v3.0 | Segurança digital e privacidade | Hardening, privacidade, threat model e ferramentas | `CYBERSHIELD v3.md` |
| OSINT Investigator Forense v1.0 | OSINT investigativo | Planejamento, pivôs, toolkit e relatórios | `OSINT Investigator Forense v1.0.md` |
| CRYPTO INVESTIGATOR v3.0 | Investigação em criptoativos | Rastreamento on-chain e análise patrimonial | `CRYPTO INVESTIGATOR v3.0 — Sistema de Investigação (Criptoativos).md` |
| TRANSCRIFORENSE v1.1 | Transcrição pericial | Transcrição literal com diarização e timestamps | `TRANSCRIFORENSE v1.1 — Sistema Integrado em Transcrição.md` |

## Resumo dos assistentes

### 1. Sistema Pericial ALPR v4.1
**Arquivo:** `Sistema Pericial ALPR v4.1.md`

Assistente pericial voltado para **análise forense de placas veiculares brasileiras** a partir de imagens.

**Resumo:**
- Examina visualmente veículos e placas.
- Identifica caracteres e inconsistências tipográficas.
- Detecta sinais de adulteração física ou digital.
- Trabalha com política rígida de incerteza para evitar conclusões inventadas.
- Gera um laudo estruturado, com foco pericial e linguagem técnica.

**Indicado para:**
- análise de placa em imagens de baixa ou média qualidade
- triagem pericial visual
- apoio a laudos sobre leitura de caracteres e possível fraude

### 2. CYBERSHIELD v3.0
**Arquivo:** `CYBERSHIELD v3.md`

Assistente especializado em **segurança digital, privacidade online e anonimato na internet**.

**Resumo:**
- Organiza recomendações com base nas camadas do modelo `TCP/IP`.
- Ajuda usuários leigos, intermediários e avançados.
- Explica ferramentas de privacidade, hardening, VPN, Tor, DNS seguro, fingerprinting e proteção de dados.
- Trabalha com foco em defesa em profundidade e modelo de ameaça.
- Também contempla privacidade no uso de IA e LLMs.

 **Indicado para:**
 - montar kits de privacidade
 - hardening de navegador, sistema e celular
 - avaliar ferramentas de segurança
 - orientar usuários sobre rastreamento, fingerprinting e proteção de dados

 **Importante:** para o assistente funcionar corretamente, carregue também o arquivo de base de conhecimento `CYBERSHIELD v3\CyberShield_Base_de_Conhecimento_Ferramentas.md` no projeto/GEM.

### 3. OSINT Investigator Forense v1.0
**Arquivo:** `OSINT Investigator Forense v1.0.md`

Assistente voltado para **OSINT aplicado à investigação criminal digital**, com abordagem metodológica e aderência ao contexto investigativo brasileiro.

**Resumo:**
- Estrutura a atuação pelo ciclo de inteligência em 7 fases.
- Separa explicitamente `FATO` de `INFERÊNCIA`.
- Exige respaldo legal para técnicas sensíveis.
- Roteia investigações a partir de identificadores como e-mail, IP, domínio, username, telefone, imagem, cripto e outros.
- Entrega artefatos prontos para colagem em relatórios, diligências, cadeia de custódia e peças investigativas.

**Indicado para:**
- planejamento de investigação OSINT
- mapeamento de pivôs a partir de identificadores
- geração de relatórios estruturados
- apoio técnico a investigadores, peritos e analistas de threat intelligence

**Importante:** para o assistente funcionar corretamente, carregue também o arquivo de base de conhecimento `OSINT Investigator Forense v1.0\osint_knowledge_base_v3.md` no projeto/GEM.

### 4. CRYPTO INVESTIGATOR v3.0
**Arquivo:** `CRYPTO INVESTIGATOR v3.0 — Sistema de Investigação (Criptoativos).md`

Assistente de **investigação forense em criptoativos**, voltado para rastreamento on-chain, análise patrimonial e leitura investigativa de transações em blockchain.

**Resumo:**
- Ensina o investigador a rastrear fluxos de fundos com método.
- Diferencia claramente blockchains `UTXO` e `account-based`.
- Ajuda a identificar a blockchain correta antes da análise.
- Orienta o uso de explorers e ferramentas para coleta de dados verificáveis.
- Estrutura as conclusões para uso em relatórios investigativos.

**Indicado para:**
- rastreamento de carteiras e transações
- análise de movimentação de fundos
- entendimento de bridges, tokens, stablecoins e ecossistemas multi-chain
- apoio a investigações patrimoniais envolvendo criptoativos

### 5. TRANSCRIFORENSE v1.1
**Arquivo:** `TRANSCRIFORENSE v1.1 — Sistema Integrado em Transcrição.md`

Assistente pericial para **transcrição literal de áudio e vídeo com diarização de falantes**.

**Resumo:**
- Produz transcrições fiéis, literais e estruturadas.
- Preserva erros gramaticais, hesitações, interrupções e vícios de linguagem.
- Usa marcação de trechos inaudíveis sem inventar conteúdo.
- Faz diarização rigorosa dos falantes.
- Opera com autoauditoria para reduzir alucinações e corrigir atribuições indevidas.
- Pode atuar em modo de laudo formal ou apoio investigativo.

**Indicado para:**
- transcrição pericial de áudios e vídeos
- organização de falas por interlocutor
- produção de material para laudos e autos
- apoio investigativo com rastreabilidade por timestamps

## Diferenciais deste repositório

- **Instruções completas** — cada arquivo define comportamento, escopo, limites, protocolos e formatos de saída.
- **Especialização real** — os assistentes foram desenhados para funções técnicas específicas, e não para uso genérico.
- **Foco operacional** — o conteúdo prioriza aplicação prática, consistência e respostas utilizáveis no mundo real.
- **Guardrails explícitos** — os prompts incluem regras de recusa, confidencialidade e controle de qualidade.
- **Compatibilidade com ambientes robustos** — o material foi pensado para `GEMs` e `Projects`, onde instruções longas funcionam melhor.

## Para quem é

Este material é especialmente útil para:
- investigadores
- peritos
- analistas de inteligência
- profissionais de segurança digital
- usuários avançados que desejam assistentes altamente especializados

## Estrutura do repositório

```text
.
├── README.md
├── CRYPTO INVESTIGATOR v3.0 — Sistema de Investigação (Criptoativos).md
├── CYBERSHIELD v3.md
├── OSINT Investigator Forense v1.0.md
├── Sistema Pericial ALPR v4.1.md
└── TRANSCRIFORENSE v1.1 — Sistema Integrado em Transcrição.md
```

## Posicionamento do projeto

Este repositório deve ser apresentado como uma coleção de **instruções completas para assistentes especializados**, e não como uma simples lista de prompts. O diferencial do projeto está na profundidade metodológica, na especialização temática e na estrutura operacional de cada assistente.
