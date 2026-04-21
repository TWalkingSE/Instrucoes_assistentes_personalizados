# DARKWEB INVESTIGATOR — Base de Conhecimento de Ferramentas

> **Versão:** 1.1 | **Atualização:** Abril 2026
> **Complemento ao:** DARKWEB INVESTIGATOR v4.0 (System Prompt)
> **Escopo:** Catálogo único de **ferramentas** (software, plataformas, serviços). As **técnicas e metodologias** que orientam o uso destas ferramentas estão no System Prompt.
> **Total:** 13 categorias | 100+ ferramentas catalogadas com links, status e alternativas

---

## Índice

1. Reconhecimento e OSINT
2. Dark Web — Busca e Monitoramento
3. Forense Digital
4. Análise de Comunicações e Dispositivos Móveis
5. Rastreamento de Criptomoedas
6. Análise Linguística e Atribuição
7. Threat Intelligence e Compartilhamento
8. Detecção de Conteúdo Sintético (IA)
9. Segurança Operacional — Ferramentas
10. Análise de Rede e Infraestrutura
11. Plataformas de Comunicação Mainstream (forense / cooperação)
12. Redes de Anonimato Alternativas
13. IA Defensiva — Ferramentas de Apoio Investigativo

---

## 1. RECONHECIMENTO E OSINT

### 1.1 Frameworks e Automação OSINT

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Maltego** | ❌ Não | GUI / Grafos | Mapeamento visual de conexões e grafos de vínculo. Módulos (transforms) para múltiplas fontes | maltego.com | ✅ Ativo |
| **SpiderFoot** | ✅ Sim | CLI / Web UI | Automação de OSINT multi-fonte com 200+ módulos. Pode ser self-hosted | spiderfoot.net | ✅ Ativo |
| **Recon-ng** | ✅ Sim | CLI | Framework modular de reconhecimento similar a Metasploit. Marketplace de módulos | github.com/lanmaster53/recon-ng | ✅ Ativo |
| **theHarvester** | ✅ Sim | CLI | Coleta de e-mails, subdomínios, IPs, nomes de uma organização-alvo | github.com/laramies/theHarvester | ✅ Ativo |
| **OSINT Framework** | ✅ Sim | Web | Diretório organizado de ferramentas OSINT por categoria | osintframework.com | ✅ Ativo |

**Quando usar:**
- **Maltego** → quando precisa visualizar conexões complexas entre entidades
- **SpiderFoot** → automação de coleta inicial em larga escala
- **Recon-ng** → investigadores que preferem CLI e precisam de modularidade
- **theHarvester** → coleta rápida de dados de uma organização específica

### 1.2 Busca de Usernames e Identidade

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Sherlock** | ✅ Sim | CLI | Busca de username em 300+ redes sociais | github.com/sherlock-project/sherlock | ✅ Ativo |
| **Maigret** | ✅ Sim | CLI | Fork melhorado do Sherlock com mais sites e análise de perfil | github.com/soxoj/maigret | ✅ Ativo |
| **Holehe** | ✅ Sim | CLI | Verifica se e-mail está registrado em serviços online (sem login) | github.com/megadose/holehe | ✅ Ativo |
| **WhatsMyName** | ✅ Sim | Web / CLI | Busca de username com base de dados atualizada pela comunidade | whatsmyname.app | ✅ Ativo |
| **Namechk** | ❌ Não | Web | Verificação rápida de disponibilidade de username | namechk.com | ✅ Ativo |

**Quando usar:**
- **Maigret** → versão mais completa e atualizada para busca de usernames
- **Holehe** → verificar se e-mail está registrado em serviços (sem alertar o alvo)
- **Sherlock** → alternativa mais simples quando Maigret não está disponível

### 1.3 Busca de Dispositivos e Infraestrutura

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Shodan** | ❌ Não | Web / API | Busca de dispositivos e serviços expostos na internet. Filtros avançados | shodan.io | ✅ Ativo |
| **Censys** | ❌ Não | Web / API | Busca de hosts e certificados SSL. Foco em enterprise | censys.io | ✅ Ativo |
| **ZoomEye** | ❌ Não | Web / API | Similar a Shodan, foco em mercado asiático | zoomeye.org | ✅ Ativo |
| **FOFA** | ❌ Não | Web / API | Motor de busca de ativos de infraestrutura | fofa.info | ✅ Ativo |
| **GreyNoise** | ❌ Não | Web / API | Distingue scan benigno de malicioso. Contextualiza IPs | greynoise.io | ✅ Ativo |

### 1.4 Busca de Leaks e Dados Vazados

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Have I Been Pwned** | ❌ Não | Web / API | Verifica se e-mail/senha aparece em vazamentos conhecidos | haveibeenpwned.com | ✅ Ativo |
| **IntelX (Intelligence X)** | ❌ Não | Web / API | Busca em dados de dark web, leaks, pastes, domínios | intelx.io | ✅ Ativo (Freemium) |
| **DeHashed** | ❌ Não | Web / API | Busca em bases de dados vazadas por e-mail, username, IP, nome | dehashed.com | ✅ Ativo (Pago) |
| **Snusbase** | ❌ Não | Web / API | Busca em databases vazadas | snusbase.com | ✅ Ativo (Pago) |
| **LeakCheck** | ❌ Não | Web / API | Verificação de credenciais em leaks | leakcheck.io | ✅ Ativo (Freemium) |

---

## 2. DARK WEB — BUSCA E MONITORAMENTO

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Ahmia** | ✅ Sim | Web | Motor de busca para .onion (filtra conteúdo ilegal). Ponto de entrada seguro | ahmia.fi | ✅ Ativo |
| **OnionScan** | ✅ Sim | CLI | Scanner de segurança/misconfiguration para sites .onion. Detecta leaks de identidade | github.com/s-rah/onionscan | ⚠️ Manutenção limitada |
| **TorBot** | ✅ Sim | CLI | Crawler para dark web com extração de dados | github.com/DedSecInside/TorBot | ✅ Ativo |
| **DarkOwl** | ❌ Não | Plataforma | Plataforma profissional de inteligência de dark web | darkowl.com | ✅ Ativo (Comercial) |
| **Recorded Future** | ❌ Não | Plataforma | Inteligência de ameaças incluindo dark web, com IA integrada | recordedfuture.com | ✅ Ativo (Comercial) |
| **Flare** | ❌ Não | Plataforma | Monitoramento de dark web, leaks e ameaças | flare.io | ✅ Ativo (Comercial) |
| **IntelX** | ❌ Não | Web / API | Busca em dados de dark web, Tor, I2P, pastes | intelx.io | ✅ Ativo (Freemium) |
| **Hunchly** | ❌ Não | Extensão | Captura e preservação automatizada de evidências web (funciona com Tor Browser) | hunch.ly | ✅ Ativo (Comercial) |
| **Torch** | N/A | Web (.onion) | Motor de busca na rede Tor | Apenas via .onion | ✅ Ativo |
| **Kilos** | N/A | Web (.onion) | Motor de busca de marketplaces da dark web | Apenas via .onion | ⚠️ Variável |

**Nota:** Ferramentas comerciais (DarkOwl, Recorded Future, Flare) são mais adequadas para equipes institucionais com orçamento. Para investigadores individuais, a combinação Ahmia + OnionScan + Hunchly + IntelX é eficaz.

---

## 3. FORENSE DIGITAL

### 3.1 Análise de Disco e Sistema

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Autopsy / Sleuth Kit** | ✅ Sim | GUI / CLI | Suite forense completa: análise de disco, timeline, carving, keyword search | sleuthkit.org | ✅ Ativo |
| **FTK Imager** | ❌ Não | GUI | Imagem forense de disco (AD1, E01, DD). Gratuito | exterro.com | ✅ Ativo (Gratuito) |
| **IPED** | ✅ Sim | GUI | Indexador e Processador de Evidências Digitais — suite da Polícia Federal brasileira | github.com/sepinf-inc/IPED | ✅ Ativo |
| **X-Ways Forensics** | ❌ Não | GUI | Suite forense profissional, leve e rápida | x-ways.net | ✅ Ativo (Comercial) |
| **EnCase** | ❌ Não | GUI | Suite forense enterprise, padrão em muitas agências | opentext.com | ✅ Ativo (Comercial) |

### 3.2 Análise de Memória

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Volatility 3** | ✅ Sim | CLI | Análise de memória RAM — plugins para Windows, Linux, Mac | volatilityfoundation.org | ✅ Ativo |
| **Rekall** | ✅ Sim | CLI | Framework de análise de memória (fork do Volatility) | github.com/google/rekall | ⚠️ Descontinuado |
| **WinPmem / LinPmem** | ✅ Sim | CLI | Aquisição de memória RAM (dump) | github.com/Velocidex/WinPmem | ✅ Ativo |

### 3.3 Análise de Rede e Tráfego

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Wireshark** | ✅ Sim | GUI | Análise de tráfego de rede — captura e disseção de pacotes | wireshark.org | ✅ Ativo |
| **NetworkMiner** | ✅ Sim | GUI | Análise de PCAP — extrai arquivos, imagens, credenciais do tráfego | netresec.com | ✅ Ativo |
| **tcpdump** | ✅ Sim | CLI | Captura de tráfego de rede em linha de comando | tcpdump.org | ✅ Ativo |

### 3.4 Hashing e Integridade

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **sha256sum / sha512sum** | ✅ Sim | CLI | Cálculo de hash nativo em Linux/Mac | Built-in | ✅ Ativo |
| **HashCalc** | ❌ Não | GUI | Cálculo de múltiplos hashes simultâneos (Windows) | slavasoft.com | ✅ Ativo (Gratuito) |
| **HashMyFiles** | ❌ Não | GUI | Cálculo de hash em lote (Windows) — NirSoft | nirsoft.net | ✅ Ativo (Gratuito) |
| **CertUtil** | N/A | CLI | Utilitário nativo do Windows para hash (`certutil -hashfile`) | Built-in Windows | ✅ Ativo |

### 3.5 Metadados

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **ExifTool** | ✅ Sim | CLI | Extração de metadados de qualquer tipo de arquivo (fotos, vídeos, PDFs, docs) | exiftool.org | ✅ Ativo |
| **FOCA** | ✅ Sim | GUI | Extração de metadados de documentos em larga escala + fingerprinting | github.com/ElevenPaths/FOCA | ✅ Ativo |
| **mat2** | ✅ Sim | CLI | Remoção de metadados (metadata anonymization toolkit 2) | 0xacab.org/jvoisin/mat2 | ✅ Ativo |

### 3.6 Armazenamento Criptografado

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **VeraCrypt** | ✅ Sim | GUI | Criptografia de disco/partição/container. Sucessor do TrueCrypt | veracrypt.fr | ✅ Ativo |
| **Cryptomator** | ✅ Sim | GUI | Criptografia transparente de arquivos em nuvem | cryptomator.org | ✅ Ativo |

---

## 4. ANÁLISE DE COMUNICAÇÕES E DISPOSITIVOS MÓVEIS

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **UFED (Cellebrite)** | ❌ Não | Hardware + SW | Extração de dados de dispositivos móveis — líder de mercado | cellebrite.com | ✅ Ativo (Comercial) |
| **AXIOM (Magnet)** | ❌ Não | GUI | Forense digital e mobile integrada — desktop + mobile + cloud | magnetforensics.com | ✅ Ativo (Comercial) |
| **MOBILedit Forensic** | ❌ Não | GUI | Extração de dados de dispositivos móveis | mobiledit.com | ✅ Ativo (Comercial) |
| **Oxygen Forensic Detective** | ❌ Não | GUI | Análise de dispositivos e dados em nuvem | oxygen-forensic.com | ✅ Ativo (Comercial) |
| **Elcomsoft Phone Breaker** | ❌ Não | GUI | Extração de backups em nuvem (iCloud, Google) | elcomsoft.com | ✅ Ativo (Comercial) |
| **SQLite Browser** | ✅ Sim | GUI | Análise de bancos de dados SQLite de apps | sqlitebrowser.org | ✅ Ativo |
| **ADB (Android Debug Bridge)** | ✅ Sim | CLI | Interface de debug e extração lógica para Android | developer.android.com | ✅ Ativo |
| **iExplorer** | ❌ Não | GUI | Navegação em filesystem de iOS | macroplant.com | ✅ Ativo (Comercial) |

---

## 5. RASTREAMENTO DE CRIPTOMOEDAS

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Chainalysis Reactor** | ❌ Não | Plataforma | Rastreamento profissional de blockchain — padrão em agências governamentais | chainalysis.com | ✅ Ativo (Comercial institucional) |
| **Elliptic** | ❌ Não | Plataforma | Análise de blockchain e compliance | elliptic.co | ✅ Ativo (Comercial) |
| **CipherTrace (Mastercard)** | ❌ Não | Plataforma | Rastreamento e compliance — adquirida pela Mastercard | ciphertrace.com | ✅ Ativo (Comercial) |
| **Crystal Blockchain** | ❌ Não | Plataforma | Análise de risco e rastreamento de transações | crystalblockchain.com | ✅ Ativo (Comercial) |
| **Arkham Intelligence** | ❌ Não | Web | Desanonimização de carteiras, alertas, labels de entidades | arkham.io | ✅ Ativo (Freemium) |
| **Breadcrumbs** | ❌ Não | Web | Rastreamento visual de fluxo de criptomoedas | breadcrumbs.app | ✅ Ativo (Freemium) |
| **OXT.me** | ❌ Não | Web | Análise avançada de Bitcoin — heurísticas, clustering, UTXO analysis | oxt.me | ✅ Ativo (Gratuito) |
| **Blockchain.com Explorer** | N/A | Web | Explorer Bitcoin — visualização de transações e endereços | blockchain.com/explorer | ✅ Ativo (Gratuito) |
| **Etherscan** | N/A | Web | Explorer Ethereum — transações, contratos, tokens | etherscan.io | ✅ Ativo (Gratuito) |
| **Blockchair** | N/A | Web | Explorer multi-chain (Bitcoin, Ethereum, Litecoin, etc.) | blockchair.com | ✅ Ativo (Gratuito) |
| **Whale Alert** | ❌ Não | Web / Bot | Monitoramento de grandes transações em múltiplas chains | whale-alert.io | ✅ Ativo (Freemium) |
| **Tracing Monero** | N/A | Técnica | Monero tem rastreabilidade muito limitada — foco em: pontos de conversão, erros OPSEC, metadados | N/A | N/A |

**Nota prática:** Para investigadores brasileiros, **Chainalysis** e **Crystal** são as ferramentas mais usadas institucionalmente. Para uso individual/acadêmico, **OXT.me + Arkham + Breadcrumbs + explorers** cobrem a maioria dos cenários.

---

## 6. ANÁLISE LINGUÍSTICA E ATRIBUIÇÃO

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **JGAAP** | ✅ Sim | GUI | Java Graphical Authorship Attribution Program — stylometry computacional | evllabs.github.io/JGAAP | ✅ Ativo |
| **Signature Stylometric System** | ✅ Sim | Acadêmico | Análise estilométrica para atribuição de autoria | Acadêmico | ✅ Ativo |
| **Writeprints** | ✅ Sim | Acadêmico | Fingerprinting de escrita baseado em features linguísticas | Acadêmico | ✅ Ativo |
| **Google Dorks** | N/A | Web | Busca avançada para correlação surface web (operadores: site, inurl, intitle, "exato") | google.com | ✅ Ativo |
| **TinEye** | ❌ Não | Web | Busca reversa de imagem — encontra onde uma imagem aparece online | tineye.com | ✅ Ativo |
| **Google Reverse Image** | N/A | Web | Busca reversa de imagem do Google | images.google.com | ✅ Ativo |
| **Yandex Images** | N/A | Web | Busca reversa de imagem — especialmente forte para reconhecimento facial | yandex.com/images | ✅ Ativo |
| **PimEyes** | ❌ Não | Web | Busca facial em imagens públicas | pimeyes.com | ✅ Ativo (Pago) |

---

## 7. THREAT INTELLIGENCE E COMPARTILHAMENTO

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **MISP** | ✅ Sim | Plataforma | Compartilhamento de IoCs entre organizações. Formatos STIX/TAXII | misp-project.org | ✅ Ativo |
| **OpenCTI** | ✅ Sim | Plataforma | Gestão de CTI com visualização de relacionamentos. Integração com MISP | opencti.io | ✅ Ativo |
| **TheHive** | ✅ Sim | Plataforma | Gestão de casos de resposta a incidentes | thehive-project.org | ✅ Ativo |
| **Cortex** | ✅ Sim | Plataforma | Análise automatizada de observáveis. Integra com TheHive | thehive-project.org | ✅ Ativo |
| **VirusTotal** | ❌ Não | Web / API | Análise de malware, URLs, arquivos — 70+ engines AV | virustotal.com | ✅ Ativo (Freemium) |
| **AlienVault OTX** | ❌ Não | Web / API | Feed aberto de IoCs com pulsos da comunidade | otx.alienvault.com | ✅ Ativo (Gratuito) |
| **Abuse.ch** | ✅ Sim | Web / API | Feeds: URLhaus, MalwareBazaar, Feodo Tracker, ThreatFox | abuse.ch | ✅ Ativo (Gratuito) |
| **YARA** | ✅ Sim | CLI | Regras de pattern matching para identificação de malware | virustotal.github.io/yara | ✅ Ativo |

---

## 8. DETECÇÃO DE CONTEÚDO SINTÉTICO (IA)

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Microsoft Video Authenticator** | ❌ Não | Plataforma | Detecção de deepfakes em vídeo | microsoft.com | ✅ Ativo (Acesso limitado) |
| **Sensity AI** | ❌ Não | Plataforma | Detecção de deepfakes em imagem e vídeo — API disponível | sensity.ai | ✅ Ativo (Comercial) |
| **Reality Defender** | ❌ Não | Plataforma | Detecção multi-modal de conteúdo gerado por IA | realitydefender.com | ✅ Ativo (Comercial) |
| **FakeCatcher (Intel)** | ❌ Não | Plataforma | Detecção de deepfake baseada em sinais biológicos (fluxo sanguíneo) | intel.com | ✅ Ativo (Pesquisa) |
| **FotoForensics** | N/A | Web | Análise ELA (Error Level Analysis) gratuita online | fotoforensics.com | ✅ Ativo (Gratuito) |
| **Forensically** | N/A | Web | Suite de análise forense de imagem online (ELA, clone detection, noise) | 29a.ch/photo-forensics | ✅ Ativo (Gratuito) |

**Limitação:** Todas as ferramentas de detecção de IA têm taxas significativas de falso positivo/negativo. Resultados são INFERÊNCIA, nunca FATO.

---

## 9. SEGURANÇA OPERACIONAL — FERRAMENTAS

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Tails OS** | ✅ Sim | Sistema Operacional | SO amnésico que roda de USB, roteia tudo via Tor | tails.net | ✅ Ativo |
| **Whonix** | ✅ Sim | Sistema Operacional | Gateway + Workstation em VM, isolamento de rede via Tor | whonix.org | ✅ Ativo |
| **Tor Browser** | ✅ Sim | Navegador | Navegador pré-configurado para acesso via rede Tor | torproject.org | ✅ Ativo |
| **VirtualBox** | ✅ Sim | Virtualização | Hypervisor para VMs de investigação | virtualbox.org | ✅ Ativo |
| **VMware Workstation** | ❌ Não | Virtualização | Hypervisor profissional para VMs | vmware.com | ✅ Ativo (Comercial) |
| **KeePassXC** | ✅ Sim | Gerenciador de senhas | Gerenciamento de credenciais operacionais (offline) | keepassxc.org | ✅ Ativo |
| **VeraCrypt** | ✅ Sim | Criptografia | Criptografia de disco/container para armazenamento de evidências | veracrypt.fr | ✅ Ativo |
| **OnionShare** | ✅ Sim | Compartilhamento | Compartilhamento de arquivos via Tor (anônimo) | onionshare.org | ✅ Ativo |

---

## 10. ANÁLISE DE REDE E INFRAESTRUTURA

| Ferramenta | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **Nmap** | ✅ Sim | CLI | Scanner de rede e portas — descoberta de hosts e serviços | nmap.org | ✅ Ativo |
| **Masscan** | ✅ Sim | CLI | Scanner de portas ultra-rápido | github.com/robertdavidgraham/masscan | ✅ Ativo |
| **Nuclei** | ✅ Sim | CLI | Scanner de vulnerabilidades baseado em templates | nuclei.projectdiscovery.io | ✅ Ativo |
| **WHOIS / whois** | ✅ Sim | CLI / Web | Consulta de registro de domínio | Built-in / who.is | ✅ Ativo |
| **DNSdumpster** | N/A | Web | Reconhecimento DNS — subdomínios, registros MX, TXT | dnsdumpster.com | ✅ Ativo (Gratuito) |
| **SecurityTrails** | ❌ Não | Web / API | Histórico de DNS, WHOIS, subdomínios | securitytrails.com | ✅ Ativo (Freemium) |
| **crt.sh** | N/A | Web | Busca de certificados SSL/TLS — Certificate Transparency logs | crt.sh | ✅ Ativo (Gratuito) |
| **Wayback Machine** | N/A | Web | Arquivo histórico de páginas web — versões anteriores de sites | web.archive.org | ✅ Ativo (Gratuito) |

---

## 11. PLATAFORMAS DE COMUNICAÇÃO MAINSTREAM (FORENSE / COOPERAÇÃO)

Usadas frequentemente como "dark web lite". Foco aqui é em **vetores investigativos**: o que é tecnicamente recuperável e por qual via (dispositivo apreendido, cooperação com provedor, monitoramento de canais públicos).

| Plataforma | Recuperável no dispositivo | Recuperável via provedor | Observações |
|---|---|---|---|
| **WhatsApp** | Mensagens, mídia, contatos, logs de chamada | Metadata via Meta (cooperação judicial); backup em Google Drive / iCloud (pode estar E2E) | Backup em nuvem é o vetor principal |
| **Telegram** | Chats secretos (apenas no dispositivo); chats normais cacheados | Chats normais e canais via Telegram (cooperação) | Username/phone correlation; canais públicos são monitoráveis sem cooperação |
| **Signal** | Mensagens criptografadas localmente (PIN/biometria) | Praticamente nada — apenas data de cadastro e último acesso | Extração física necessária |
| **Discord** | Cache local | Servidores Discord (cooperação judicial) | Account correlation, metadata de arquivos compartilhados |
| **Matrix / Element** | Mensagens sincronizadas | Depende do homeserver (matrix.org coopera; servidores próprios não) | Análise de servidores públicos, correlação de usernames |
| **Session** | Cache local | Praticamente nada — sem telefone, sem servidor central | Foco em erros de OPSEC do usuário |
| **Wickr / AWS Wickr** | Limitado por mensagens autodestrutivas | AWS coopera com ordem judicial | Análise forense de dispositivo, metadata de rede |
| **Instagram / Facebook DMs** | Cache de mensagens | Servidores Meta (cooperação judicial) | DMs recuperáveis via cooperação |

**Nota:** A migração de atividades criminosas para essas plataformas geralmente indica busca por menor barreira técnica (vs. Tor) ou maior base de "clientes". Investigar nelas requer cooperação com o provedor e/ou autorização judicial específica.

---

## 12. REDES DE ANONIMATO ALTERNATIVAS

Além do Tor, atividades criminosas migram para outras redes overlay. Foco em **clientes/ferramentas** de acesso e análise.

| Rede / Cliente | Open-Source | Tipo | Diferencial | Link | Status |
|---|---|---|---|---|---|
| **I2P (Invisible Internet Project)** | ✅ Sim | Rede overlay | Roteamento garlic, eepsites (.i2p) | geti2p.net | ✅ Ativo |
| **Freenet / Hyphanet** | ✅ Sim | Armazenamento distribuído | Conteúdo persistente, resistente a censura | hyphanet.org | ✅ Ativo |
| **Lokinet** | ✅ Sim | Rede overlay (blockchain Oxen) | SNApps (serviços anônimos) | lokinet.org | ✅ Ativo |
| **ZeroNet** | ✅ Sim | P2P descentralizado | Sites hospedados por usuários, baseado em Bitcoin crypto | zeronet.io | ⚠️ Manutenção limitada |
| **Yggdrasil** | ✅ Sim | Mesh / overlay IPv6 | Rede mesh experimental, usada por alguns atores | yggdrasil-network.github.io | ✅ Ativo |

**Uso investigativo típico:**
- **I2P** → Monitoramento de eepsites conhecidos, análise de tráfego na borda, correlação temporal
- **Freenet** → Análise de chaves de conteúdo, monitoramento de freesites conhecidos
- **Lokinet** → Similar a Tor; monitoramento de SNApps
- **ZeroNet** → Análise de peers, rastreamento via trackers

---

## 13. IA DEFENSIVA — FERRAMENTAS DE APOIO INVESTIGATIVO

| Ferramenta / Categoria | Open-Source | Tipo | Uso investigativo | Link | Status |
|---|---|---|---|---|---|
| **GPT-4 / Claude / Gemini (LLMs)** | ❌ Não | API / Web | Análise de grandes volumes de texto, sumarização de fóruns, tradução, identificação de padrões linguísticos | openai.com / anthropic.com / google.com | ✅ Ativo (Comercial) |
| **spaCy / NLTK (NLP)** | ✅ Sim | Biblioteca | NLP para análise de sentimento e detecção de intenção em comunicações | spacy.io / nltk.org | ✅ Ativo |
| **scikit-learn (ML)** | ✅ Sim | Biblioteca | ML para clustering de atores em múltiplas plataformas | scikit-learn.org | ✅ Ativo |
| **Chainalysis / Elliptic (IA blockchain)** | ❌ Não | Plataforma | Identificação automática de padrões de lavagem | chainalysis.com / elliptic.co | ✅ Ativo (Comercial) |
| **Tesseract OCR + LLM** | ✅ Sim | CLI / Lib | OCR + IA em screenshots e documentos escaneados | github.com/tesseract-ocr | ✅ Ativo |
| **SpiderFoot HX** | ❌ Não | Plataforma | OSINT automatizado com correlação por IA | spiderfoot.net | ✅ Ativo (Comercial) |
| **Maltego com Hub Items de IA** | ❌ Não | GUI | Transforms com IA para enriquecimento de entidades | maltego.com | ✅ Ativo (Comercial) |

**Limitação crítica:** Resultados de ferramentas de IA (ofensivas ou defensivas) devem ser validados por analista humano e tratados como **INFERÊNCIA** até confirmação independente. IA é ferramenta auxiliar, não substituto de análise crítica.

> Para ferramentas de **detecção** de conteúdo sintético (deepfake, imagens geradas por IA), ver **Categoria 8** acima.

---

## DIRETRIZES DE USO

### Critérios de Seleção de Ferramenta

Ao recomendar ferramentas, considere:
1. **Contexto legal** — a ferramenta pode ser usada sem autorização judicial? Ou requer mandado?
2. **OPSEC** — o uso da ferramenta expõe o investigador? (ex: Shodan queries ficam logadas)
3. **Preservação** — os resultados podem ser usados como evidência? Há logs e hashes?
4. **Custo** — disponibilidade de alternativas open-source ou gratuitas
5. **Jurisdição** — algumas ferramentas podem ter restrições de uso em certas jurisdições

### Cadeia de Ferramentas por Tipo de Investigação

**Investigação de Marketplace:**
`Ahmia/Torch → Hunchly (captura) → OnionScan (infraestrutura) → ExifTool (metadados) → Maltego (grafos) → OXT.me/Arkham (crypto)`

**Investigação de Ator:**
`Maigret/Sherlock (username) → HIBP/IntelX (leaks) → JGAAP (stylometry) → Maltego (conexões) → SpiderFoot (automação)`

**Rastreamento de Criptomoedas:**
`Blockchain Explorer → OXT.me (heurísticas) → Breadcrumbs (visualização) → Arkham (labels) → Chainalysis (institucional)`

**Resposta a Incidente:**
`WinPmem (memória) → FTK Imager (disco) → Volatility 3 (análise memória) → Autopsy (análise disco) → Wireshark (rede) → TheHive (gestão)`

---

> **Nota:** Esta base de conhecimento é atualizada periodicamente. Ferramentas com status ⚠️ podem estar descontinuadas ou com manutenção limitada — verifique antes de usar. Links podem mudar — busque pelo nome da ferramenta se o link estiver inativo.
