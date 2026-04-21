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
| Sistema Pericial ALPR v4.2 | Perícia veicular | Análise de placas e indícios de adulteração | `# Sistema Pericial ALPR v4.2.md` |
| CYBERSHIELD v4.0 | Segurança digital e privacidade | Hardening, privacidade, threat model e ferramentas | `CYBERSHIELD v4\CYBERSHIELD v4.md` |
| OPSEC SPECIALIST v2.1 | Segurança operacional | Threat model, anonimato defensivo, hardening e operações de risco | `# OPSEC SPECIALIST v2.1.md` |
| OSINT Investigator Forense v2.0 | OSINT investigativo | Planejamento, pivôs, toolkit e relatórios | `OSINT Investigator Forense v2.0\# OSINT Investigator Forense v2.0.md` |
| DARKWEB INVESTIGATOR v4.0 | Investigação em dark web | Fóruns .onion, atribuição, classificação criminal e relatórios | `DARKWEB INVESTIGATOR v4.0\# DARKWEB INVESTIGATOR v4.0.md` |
| CRYPTO INVESTIGATOR v3.1 | Investigação em criptoativos | Rastreamento on-chain e análise patrimonial | `# CRYPTO INVESTIGATOR v3.1 — Sistema de Investigação (Criptoativos).md` |
| TRANSCRIFORENSE v1.2 | Transcrição pericial | Transcrição literal com diarização e timestamps | `TRANSCRIFORENSE v1.2 — Sistema Integrado em Transcrição.md` |
| REDATOR INTELIGENTE 5.0 | Redação e revisão de textos | Revisão, adequação de tom, normas (ABNT/APA) e expansão argumentativa | `# REDATOR INTELIGENTE 5.0.md` |

## Resumo dos assistentes

### 1. Sistema Pericial ALPR v4.2
**Arquivo:** `# Sistema Pericial ALPR v4.2.md`

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

### 2. CYBERSHIELD v4.0
**Arquivo:** `CYBERSHIELD v4\CYBERSHIELD v4.md`

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

 **Importante:** para o assistente funcionar corretamente, carregue também o arquivo de base de conhecimento `CYBERSHIELD v4\CyberShield_Base_de_Conhecimento_Ferramentas.md` no projeto/GEM.

### 3. OPSEC SPECIALIST v2.1
**Arquivo:** `# OPSEC SPECIALIST v2.1.md`

Assistente especializado em **segurança operacional**, com foco em modelo de ameaça, anonimato digital, proteção de dispositivos, eliminação de rastros e orientação proporcional ao risco.

**Resumo:**
- Parte sempre do `threat model` antes de recomendar qualquer ferramenta.
- Escala recomendações conforme o nível de risco e o contexto do usuário.
- Cobre comunicação segura, hardening, gestão de senhas, antiforense defensiva e operações de campo.
- Trabalha com subperfis distintos para público leigo, corporativo, forense e contexto de alto risco.
- Mantém guardrails claros para uso exclusivamente defensivo e legítimo.

**Indicado para:**
- construir modelo de ameaça antes de decidir ferramentas
- orientar anonimato e comunicação segura
- endurecer dispositivos e reduzir rastros digitais
- apoiar contextos corporativos, forenses e operacionais de maior risco

### 4. OSINT Investigator Forense v2.0
**Arquivo:** `OSINT Investigator Forense v2.0\# OSINT Investigator Forense v2.0.md`

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

**Importante:** para o assistente funcionar corretamente, carregue também o arquivo de base de conhecimento `OSINT Investigator Forense v2.0\osint_knowledge_base_v3.md` no projeto/GEM.

### 5. DARKWEB INVESTIGATOR v4.0
**Arquivo:** `DARKWEB INVESTIGATOR v4.0\# DARKWEB INVESTIGATOR v4.0.md`

Assistente especializado em **investigação cibernética focada em deep e dark web**, com ênfase em análise de atividades ilícitas, atribuição, preservação probatória e classificação criminal.

**Resumo:**
- Separa rigorosamente `FATO` de `INFERÊNCIA`, com nível de confiança em toda análise.
- Exige cadeia de custódia e preservação de evidências em cada orientação sensível.
- Organiza a investigação por ações práticas: análise de marketplaces, vínculos, rastreamento de cripto, relatórios e simulações.
- Traz enquadramento legal brasileiro aplicado a crimes recorrentes na dark web.
- Prioriza atribuição, desanonimização e documentação utilizável em contexto investigativo.

**Indicado para:**
- analisar fóruns e marketplaces `.onion`
- classificar criminalmente atividades suspeitas
- mapear vínculos entre atores, carteiras e identificadores
- estruturar relatórios investigativos e treinar com simulações de caso

**Importante:** para o assistente funcionar corretamente, carregue também o arquivo de base de conhecimento `DARKWEB INVESTIGATOR v4.0\DarkWeb_Investigator_Base_de_Conhecimento.md` no projeto/GEM.

### 6. CRYPTO INVESTIGATOR v3.1
**Arquivo:** `# CRYPTO INVESTIGATOR v3.1 — Sistema de Investigação (Criptoativos).md`

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

### 7. TRANSCRIFORENSE v1.2
**Arquivo:** `TRANSCRIFORENSE v1.2 — Sistema Integrado em Transcrição.md`

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

### 8. REDATOR INTELIGENTE 5.0
**Arquivo:** `# REDATOR INTELIGENTE 5.0.md`

Assistente especializado em **revisar, reescrever e adaptar textos** com precisão linguística, clareza comunicativa e adequação ao objetivo, público e canal.

**Resumo:**
- Opera em três modos distintos: LITE, PRO e ENTERPRISE, ajustando o rigor técnico.
- Oferece revisão completa, ajuste de tom, expansão de ideias, resumo, e revisão crítica didática.
- Verifica e ajusta formatação conforme normas técnicas (ABNT, APA, MLA).
- Aplica um rigoroso guardrail de validação de intenção e abstenção inteligente para manter a fidelidade ao sentido original.
- Entrega resultados estruturados com feedback detalhado de alterações.

**Indicado para:**
- correção ortográfica, gramatical e de coesão
- adequação de textos institucionais e acadêmicos a normas específicas
- adaptação de linguagem para diferentes públicos e canais
- expansão de argumentos mantendo a fidelidade à ideia original

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

Estrutura resumida dos arquivos destacados neste README:

```text
.
├── # CRYPTO INVESTIGATOR v3.1 — Sistema de Investigação (Criptoativos).md
├── # OPSEC SPECIALIST v2.1.md
├── # REDATOR INTELIGENTE 5.0.md
├── # Sistema Pericial ALPR v4.2.md
├── CYBERSHIELD v4/
│   ├── CYBERSHIELD v4.md
│   └── CyberShield_Base_de_Conhecimento_Ferramentas.md
├── DARKWEB INVESTIGATOR v4.0/
│   ├── # DARKWEB INVESTIGATOR v4.0.md
│   └── DarkWeb_Investigator_Base_de_Conhecimento.md
├── OSINT Investigator Forense v2.0/
│   ├── # OSINT Investigator Forense v2.0.md
│   └── osint_knowledge_base_v3.md
├── README.md
└── TRANSCRIFORENSE v1.2 — Sistema Integrado em Transcrição.md
```

## Posicionamento do projeto

Este repositório deve ser apresentado como uma coleção de **instruções completas para assistentes especializados**, e não como uma simples lista de prompts. O diferencial do projeto está na profundidade metodológica, na especialização temática e na estrutura operacional de cada assistente.
