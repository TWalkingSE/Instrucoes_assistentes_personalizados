# 🔍 BASE DE CONHECIMENTO OSINT — INVESTIGAÇÃO CRIMINAL DIGITAL
**Versão:** 3.0 | **Atualizado:** 2026 | **Uso:** Exclusivo para investigações legais e éticas

> ⚠️ **AVISO LEGAL GERAL:** Todo conteúdo desta base destina-se exclusivamente a profissionais de segurança pública, investigação criminal, perícia digital, Ministério Público, Poder Judiciário, advocacia, pesquisa acadêmica e profissionais de cibersegurança corporativa. O uso inadequado, sem autorização judicial ou legal pertinente, pode configurar crime. Respeite sempre a legislação vigente (LGPD, Marco Civil da Internet, Código Penal, Lei 12.965/2014, Lei 12.850/2013, Lei 13.709/2018, Lei 14.063/2020).

> 🛑 **AVISO CRÍTICO SOBRE PAINÉIS CLANDESTINOS:** Painéis de consulta que operam sem CNPJ regular, sem contrato com fontes oficiais e sem base legal para tratamento de dados **NÃO são listados** nesta base — mesmo para fins investigativos. A sua alimentação de dados vem, tipicamente, de:
> - Vazamentos (data breaches) de bases públicas e privadas
> - Acesso indevido a sistemas governamentais (Infoseg, Detran, Receita, CAF, CNIS)
> - Receptação de dados (art. 180 CP) e violação do art. 154-A CP
> - Vínculo com organizações criminosas (Lei 12.850/2013)
>
> **O uso de tais painéis por agente público pode configurar:** violação da LGPD, abuso de autoridade (Lei 13.869/2019), prevaricação (art. 319 CP), corrupção passiva (art. 317 CP), organização criminosa e produção de prova ilícita (art. 157 CPP). Há precedentes de operações (ex: *Data Call*, *Datasan*, Operações MPF/CGU) com alvos em agentes públicos que usaram painéis clandestinos, ainda que sob alegação de "finalidade investigativa". 
>
> A **seção 27** traz ferramentas e técnicas para **investigar e reprimir** operadores desses painéis — que é o enfoque adequado ao trabalho de polícia judiciária especializada em cibercrime.

---

## ÍNDICE GERAL

1. [E-mail](#1-e-mail)
2. [Número de Telefone, CPF e CNPJ](#2-número-de-telefone-cpf-e-cnpj)
3. [Endereço IP](#3-endereço-ip)
4. [Domínio e Infraestrutura Web](#4-domínio-e-infraestrutura-web)
5. [Usernames e Identidades Digitais](#5-usernames-e-identidades-digitais)
6. [Imagens e Vídeos (IMINT)](#6-imagens-e-vídeos-imint)
7. [Geolocalização e GEOINT](#7-geolocalização-e-geoint)
8. [Redes Sociais (SOCMINT)](#8-redes-sociais-socmint)
9. [Criptoativos e Investigação Financeira](#9-criptoativos-e-investigação-financeira)
10. [Metadados (EXIF e Documentos)](#10-metadados-exif-e-documentos)
11. [Dark Web e Deep Web](#11-dark-web-e-deep-web)
12. [Favicons como Identificadores](#12-favicons-como-identificadores)
13. [Veículos, Placas e Transporte](#13-veículos-placas-e-transporte)
14. [Documentos, Registros e Vazamentos](#14-documentos-registros-e-vazamentos)
15. [Infraestrutura de Rede e Threat Intel](#15-infraestrutura-de-rede-e-threat-intel)
16. [Patrimônio e Bens](#16-patrimônio-e-bens)
17. [HUMINT Digital](#17-humint-digital)
18. [Linux e Ferramentas CLI para OSINT](#18-linux-e-ferramentas-cli-para-osint)
19. [OPSEC — Segurança Operacional](#19-opsec--segurança-operacional)
20. [IA Aplicada ao OSINT (incluindo LLMs Locais)](#20-ia-aplicada-ao-osint-incluindo-llms-locais)
21. [Scraping, Crawling e Automação](#21-scraping-crawling-e-automação)
22. [Análise e Visualização de Dados](#22-análise-e-visualização-de-dados)
23. [Frameworks, Metodologias e Referências](#23-frameworks-metodologias-e-referências)
24. [Tipologias de Cibercrime e Investigação Temática](#24-tipologias-de-cibercrime-e-investigação-temática) 🆕
25. [Integração com o Processo Penal e Cadeia de Custódia](#25-integração-com-o-processo-penal-e-cadeia-de-custódia) 🆕
26. [Ferramentas Dual-Use — Aviso Ético e Jurídico](#26-ferramentas-dual-use--aviso-ético-e-jurídico) 🆕
27. [Investigação de Painéis Clandestinos (do lado da persecução penal)](#27-investigação-de-painéis-clandestinos-do-lado-da-persecução-penal) 🆕
28. [Cooperação Internacional em Cibercrime](#28-cooperação-internacional-em-cibercrime) 🆕

---

## 1. E-MAIL

### 1.1 Estrutura e Análise de Cabeçalho

**Campos críticos do cabeçalho de e-mail:**

| Campo | Função Investigativa |
|---|---|
| `Received` | Rota do e-mail; o registro mais antigo contém o IP de origem |
| `From` | Pode ser falsificado (spoofing) |
| `Return-Path` | Geralmente revela o verdadeiro remetente |
| `Reply-To` | Se diferente do `From`, possível indicador de engano |
| `Message-ID` | Identificador único gerado pelo servidor de origem |
| `Authentication-Results` | Resultado de SPF, DKIM e DMARC |
| `X-Originating-IP` | IP direto do remetente (nem sempre presente) |
| `X-Mailer` | Client de e-mail utilizado |
| `MIME-Version` | Versão do protocolo; útil em análise forense |
| `Sender` | Responsável pelo envio quando diferente do `From` |
| `ARC-Seal` / `ARC-Message-Signature` | Autenticidade da cadeia de encaminhamento |
| `BIMI-Location` | URL do logotipo BIMI — identifica domínio legítimo |
| `DKIM-Signature` | Assinatura criptográfica do domínio |
| `List-Unsubscribe` | Revela infraestrutura de mass-mail |
| `X-Spam-Score` / `X-Spam-Status` | Pontuação anti-spam |
| `Thread-Topic` / `Thread-Index` | Agrupamento de conversas (Outlook/Exchange) |
| `X-Microsoft-Antispam-Mailbox-Delivery` | Roteamento Microsoft 365 |
| `X-MS-Exchange-Organization-*` | Dados organizacionais Exchange |
| `X-Google-Smtp-Source` | Origem em infraestrutura Google |
| `X-Forwarded-For` / `X-Forwarded-Host` | Cadeia de proxies |

**Técnica para extração de IP:**
1. Copie o cabeçalho completo (opção "Ver original" ou "Show original")
2. Cole em uma das ferramentas de análise abaixo
3. Localize o campo `Received: from` mais antigo (mais abaixo na lista)
4. Extraia o IP entre colchetes `[xxx.xxx.xxx.xxx]`
5. Consulte o IP nas ferramentas de geolocalização e WHOIS
6. Correlacione com timestamp e SPF/DKIM para confirmar autenticidade

### 1.2 Ferramentas de Análise de Cabeçalho

| Ferramenta | URL | Observação |
|---|---|---|
| MXToolbox | https://mxtoolbox.com/EmailHeaders.aspx | Análise visual completa |
| Google Apps Toolbox | https://toolbox.googleapps.com/apps/messageheader/ | Oficial do Google |
| Mail Header Analyzer | https://mailheader.org/ | Interface simples |
| WhatIsMyIPAddress | https://whatismyipaddress.com/trace-email | Trace de e-mail |
| Trustifi | https://trustifi.com/email-analyzer/ | Análise avançada |
| DNSChecker | https://dnschecker.org/email-header-analyzer.php | Multi-função |
| Azure Email Header Analyzer | https://mha.azurewebsites.net/ | Desenvolvido pela Microsoft |
| EmailHeader.net | https://emailheader.net/ | Alternativa simples |
| IP2Location Header Analyzer | https://www.ip2location.com/free/email-header-analyzer | Com geo integrado |
| Mailtrap Header Analyzer | https://mailtrap.io/blog/email-header-analyzer/ | Gratuito |
| GoDaddy Email Header Tool | https://www.godaddy.com/help/investigate-an-email-header-2064 | Básico |
| SPF Surveyor (dmarcian) | https://dmarcian.com/spf-survey/ | Auditoria de SPF |
| DKIM Validator | https://dkimvalidator.com/ | Validação de assinatura |

### 1.3 Verificação e Validação de E-mail

| Ferramenta | URL | Tipo |
|---|---|---|
| EmailHippo | https://tools.emailhippo.com/ | Valida se e-mail existe |
| EmailRep | https://emailrep.io/ | Reputação + histórico |
| Hunter.io Verifier | https://hunter.io/email-verifier | Valida endereço |
| Email-Checker | https://email-checker.net/ | Verificação simples |
| Defastra | https://defastra.com/ | Risco + análise |
| NeverBounce | https://neverbounce.com/ | Verificação em bulk |
| MailboxValidator | https://www.mailboxvalidator.com/ | API disponível |
| Skymem | https://www.skymem.info/ | Busca indexada |
| Verifalia | https://verifalia.com/ | Verificação profissional |
| Abstract API | https://www.abstractapi.com/email-validation | API REST |
| ZeroBounce | https://www.zerobounce.net/ | Enriquecimento de dados |
| Kickbox | https://kickbox.com/ | Validação em tempo real |
| Bouncer | https://www.usebouncer.com/ | Anti-fraude de e-mail |
| Clearout | https://clearout.io/ | API + dashboard |
| Snov.io Email Verifier | https://snov.io/email-verifier | Gratuita até 50/dia |
| Prowl | https://prowl.lupovis.io/ | Análise de reputação |
| Truemail | https://truemail.io/ | Validação múltipla |
| Proofy | https://proofy.io/ | Bulk checker |

### 1.4 Pesquisa por E-mail (OSINT)

| Ferramenta | URL | Tipo |
|---|---|---|
| Epieos | https://epieos.com/ | Gratuita — cruza dados |
| OSINT Industries | https://osint.industries/ | Paga (gov. gratuito) |
| Spokeo | https://www.spokeo.com/ | Paga |
| Huntter.is | https://www.huntter.is/ | Paga |
| IntelligenceX | https://intelx.io/ | Paga — dark web incluso |
| Holehe (Linux) | https://github.com/megadose/holehe | Checa cadastros em +120 sites |
| SocialScan (Linux) | https://github.com/iojw/socialscan | E-mail + username |
| GHunt (Linux) | https://github.com/mxrch/GHunt | OSINT em contas Google |
| H8mail (Linux) | https://github.com/khast3x/h8mail | Cruza com breaches |
| Infoga (Linux) | https://github.com/The404Hacking/Infoga | Coleta info de e-mails |
| theHarvester | https://github.com/laramies/theHarvester | Coleta e-mails de domínios |
| EmailFinder | https://github.com/Josue87/EmailFinder | Enumeração de e-mails |
| MOSINT | https://github.com/alpkeskin/mosint | Automated email OSINT |
| ReverseMX | https://reversemx.io/ | MX reverso por e-mail |
| Castrick Clues | https://castrickclues.com/ | OSINT agregador |
| Email2PhoneNumber | https://github.com/martinvigo/email2phonenumber | Tenta recuperar fone |
| ScyllaHide (scylla.sh) | https://scylla.sh/ | Busca em breaches |
| AnyWho | https://www.anywho.com/ | Pesquisa reversa (EUA) |
| That'sThem Email | https://thatsthem.com/reverse-email-lookup | Gratuita (EUA) |
| Skymem Domain Search | https://www.skymem.info/ | E-mails por domínio |

### 1.5 Verificação de Vínculos com Plataformas

**Técnica: Simulação de PIX**
Ao cadastrar o e-mail como chave PIX em um banco digital, o sistema pode revelar o nome associado ao titular. Procedimento com autorização legal.

**Técnica: Recuperação de senha**
Ao inserir o e-mail na opção "Esqueci minha senha" de plataformas como Google, Apple, Microsoft, LinkedIn — o sistema mascara o número de telefone vinculado, revelando dígitos parciais. Ideal para triangulação com outros fragmentos.

**Técnica: Página do Facebook**
Criar uma página no Facebook e adicionar o e-mail como administrador — se o Facebook reconhecer o endereço, pode revelar o perfil vinculado.

**Técnica: Apple ID**
Em appleid.apple.com, a tentativa de login com um e-mail informa se há conta Apple associada.

**Técnica: Outlook/Microsoft Account**
O mesmo vale para login.live.com — também revela se o e-mail é uma conta Microsoft.

**Técnica: Adobe Creative Cloud**
O login em adobe.com revela se o e-mail tem conta Adobe (útil para investigações envolvendo profissionais gráficos).

**Técnica: Netflix/Spotify/Outros**
Páginas de login de grandes plataformas revelam (ou mascaram) dados úteis em recuperação de senha.

> ⚠️ **Atenção:** Essas técnicas devem ser registradas como diligência investigativa, documentadas com print e hash, e realizadas em ambiente OPSEC segregado. Não gerar interação ativa com o alvo (não clicar em recuperação de senha se gerar e-mail/SMS para o alvo).

### 1.6 Verificação de Vazamentos

| Ferramenta | URL | Tipo |
|---|---|---|
| HaveIBeenPwned | https://haveibeenpwned.com/ | Gratuita |
| Firefox Monitor | https://monitor.firefox.com/ | Gratuita |
| DeHashed | https://www.dehashed.com/ | Paga |
| IntelX | https://intelx.io/ | Paga |
| Breach Directory | https://breachdirectory.org/ | Semi-gratuita |
| AmIBreached | https://amibreached.com/ | Gratuita |
| Leak-Lookup | https://leak-lookup.com/ | Paga |
| LeakIX | https://leakix.net/ | Foco em servidores expostos |
| SnusBase | https://snusbase.com/ | Paga |
| Proxynova | https://www.proxynova.com/tools/comb | Combo lists |
| Scylla.sh | https://scylla.sh/ | Gratuita — grandes breaches |
| LeakPeek | https://leakpeek.com/ | Paga |
| BreachForums Alternatives | (variados) | Monitorar via intel — não acessar sem autorização |
| RaidForums Archive | (variados) | Arquivo histórico |
| LeakBase | https://leakbase.cc/ | Paga |
| Inoitsu | https://www.inoitsu.com/ | Breach risk scoring |
| XposedOrNot | https://xposedornot.com/ | Gratuita |
| PSBDMP (pastes) | https://psbdmp.ws/ | Arquivo de pastes vazados |
| WeLeakInfo (sucessores) | (variados) | Monitorar via intel formal |
| Leaked.zone | https://leaked.zone/ | Paga |

> ⚠️ **Para agentes públicos:** Sempre prefira HaveIBeenPwned, IntelX com conta institucional e DeHashed com conta corporativa. **Nunca** faça download de combolists de fóruns clandestinos para "uso investigativo" — isso caracteriza receptação de dados (art. 180 CP) e violação de LGPD. Dados de breach podem ser requisitados formalmente via MLAT ou via acordo com provedores internacionais.

### 1.7 Domínio e WHOIS por E-mail

| Ferramenta | URL | Função |
|---|---|---|
| Whoxy | https://www.whoxy.com/ | WHOIS reverso por e-mail |
| DomainTools | https://whois.domaintools.com/ | Histórico + owner |
| Registros associados | https://viewdns.info/reversewhois/ | Domínios pelo e-mail |
| WhoisXML Reverse | https://reverse-whois.whoisxmlapi.com/ | API + web |
| Whoisology | https://whoisology.com/ | Banco histórico |
| DNSlytics Reverse | https://dnslytics.com/reverse-whois | Paga |

### 1.8 E-mail em Plataformas Específicas

| Plataforma | Técnica | Link |
|---|---|---|
| Skype | Busca por e-mail | https://www.vedbex.com/email2skype |
| Google Account | GHunt | https://github.com/mxrch/GHunt |
| Apple ID | Tentativa de login parcial | https://iforgot.apple.com/ |
| Gravatar | Avatar universal | https://en.gravatar.com/site/check/ |
| Pastebin | Dork: `site:pastebin.com "email@dominio.com"` | — |
| GitHub | Dork: `"email@dominio.com" in:file` | GitHub Search |
| Telegram | WhatAPI (não oficial) | Via bots de lookup — com cautela |
| Discord | Discord.id | https://discord.id/ |
| Steam | SteamID Finder | https://steamid.io/ |
| Slack Enum | `email_check` na API de times públicos | Limitado |

### 1.9 Ferramentas Avançadas (Pagas)

| Ferramenta | URL | Observação |
|---|---|---|
| Lampyre | https://lampyre.io/ | OSINT visual + timeline |
| Maltego + Social Links | https://www.maltego.com/ | Grafo de conexões |
| Pipl | https://pipl.com/ | Busca por pessoa |
| SpiderFoot | https://github.com/smicallef/spiderfoot | Open-source, automação |
| Recon-ng | https://github.com/lanmaster53/recon-ng | Framework modular |
| OSINT Industries | https://osint.industries/ | Extensa cobertura |
| IRBIS (Social Links) | https://irbis.espysys.com/ | Plataforma profissional |
| Skopenow | https://www.skopenow.com/ | Investigações comerciais |
| Babel X | https://www.babelstreet.com/ | Análise multilíngue |
| Cobwebs | https://cobwebs.com/ | WEBINT |
| Voyager Labs | https://voyagerlabs.co/ | Análise social |

---

## 2. NÚMERO DE TELEFONE, CPF E CNPJ

### 2.1 Telefone — Identificação e Pesquisa

#### 2.1.1 Verificação do Número

| Ferramenta | URL | Função |
|---|---|---|
| ABRTELECOM | https://consultanumero.abrtelecom.com.br | Operadora oficial (Anatel) |
| NumVerify | https://numverify.com/ | Valida + tipo (VOIP/fixo/móvel) |
| PhoneInfoga | https://github.com/sundowndev/phoneinfoga | OSINT de telefones |
| TrueCaller | https://www.truecaller.com/ | Nome + operadora |
| DonoDoZap | https://donodozap.com/ | WhatsApp — nome e foto |
| Epieos | https://epieos.com/ | Cruza com outros dados |
| MySmsBox | https://mysmsbox.ru/ | Busca russa para BR |
| Sync.me | https://sync.me/ | Identificador de chamadas |
| CallerID Test | https://calleridtest.com/ | Identifica nome associado |
| OSINT Industries | https://osint.industries/ | Paga (gov. gratuito) |
| Eyecon | https://eyecon-app.com/ | App de identificação |
| Hiya | https://www.hiya.com/ | Reputação de chamadas |
| Showcaller | https://www.showcaller.com/ | Alternativo ao Truecaller |
| Whoscall | https://whoscall.com/ | Global com foco em Ásia |
| OpenCNAM | https://www.opencnam.com/ | Nome associado (CNAM) |
| FreeCarrierLookup | https://freecarrierlookup.com/ | Operadora (EUA/global) |
| Twilio Lookup API | https://www.twilio.com/lookup | Comercial, confiável |
| Numlookup | https://www.numlookup.com/ | Gratuita |
| Spydialer | https://www.spydialer.com/ | Identificador reverso |
| BeenVerified Phone | https://www.beenverified.com/ | Paga (EUA) |
| CocoFinder | https://cocofinder.com/ | Paga (EUA) |
| Consulta Anatel (oficial) | https://sistemas.anatel.gov.br/ | Portabilidade numérica |
| Portabilidade ABR | https://consultanumero.abrtelecom.com.br | Operadora atual |

#### 2.1.2 Verificação de VOIP

| Ferramenta | URL |
|---|---|
| NumVerify | https://numverify.com/ |
| TeleSeer | https://www.teleseer.com/ |
| PhoneInfoga | https://github.com/sundowndev/phoneinfoga |
| HLR Lookup | https://hlrlookup.com/ |
| Maltego + LoginSoft OSINT | Via Transform Hub |
| IPQualityScore | https://www.ipqualityscore.com/free-ip-lookup-proxy-vpn-test |
| HLR-Lookups | https://www.hlr-lookups.com/ |
| TextMagic HLR | https://www.textmagic.com/free-tools/hlr-phone-number-lookup | Verificação de status |
| Phoneva | https://phoneva.com/ | OSINT de telefone |
| CallerAPI | https://callerapi.com/ | API comercial |

**Indicadores de VOIP:**
- Blocos de numeração atribuídos a operadoras 100% VOIP (ex: Voys, Aircall, 55Voip)
- Incapacidade de receber SMS A2P em plataformas bancárias
- Latência anormal em chamadas
- Ausência em bases HLR convencionais

#### 2.1.3 Técnica: Simulação de PIX
Ao cadastrar o número como chave PIX em um banco digital (com autorização legal), o sistema pode revelar nome completo e instituição financeira do titular. **Atenção:** registro de auditoria fica na instituição — documentar o procedimento.

#### 2.1.4 Técnica: WhatsApp Web
Via WhatsApp Web, é possível verificar foto de perfil, status e "visto por último" de um número alvo sem adicioná-lo, preservando sigilo operacional. Usar conta operacional descartável, nunca conta pessoal.

#### 2.1.5 Técnica: Telegram
Adicionar o número como contato em conta operacional revela se há conta Telegram, username (se público) e foto de perfil. Documentar via print com timestamp.

#### 2.1.6 Técnica: Google Contacts + Google Photos
Adicionar o número como contato em conta Google operacional pode, dependendo de configurações do alvo, revelar foto de perfil Google.

#### 2.1.7 Painéis de Consulta **LEGÍTIMOS** (CNPJ regular + contrato com bureaus)

> ✅ Estes painéis operam com CNPJ regular, contratos de fornecimento com bureaus (Serasa, Boa Vista, Quod) ou bases públicas (Receita, SERPRO). Sempre exija contrato escrito e verifique o CNPJ antes de contratar.

| Serviço | URL |
|---|---|
| SisMix | https://sismix.com.br/ |
| Brasil Consultas | https://brasilconsultas.com.br/ |
| CheckTudo | https://www.checktudo.com.br/ |
| GigaDados | https://www.gigadados.com.br/ |
| MegaConsultas | https://megaconsultas.com.br/ |
| Credilink | https://www.credilink.com.br/ |
| Fênix Consultas | https://fenixconsultas.com.br/ |
| CATTA | https://www.catta.com.br/ |
| PROCOB | https://www.procob.com/ |
| UGGLE | https://www.uggle.com.br/ |
| ASSECC | https://www.assecc.com.br/ |
| Buscas Consultas | https://buscaconsultas.com.br/ |
| SERPRO Datavalid | https://www.datavalid.com.br/ | Oficial — convênio |
| Serasa Experian | https://www.serasaexperian.com.br/ | Bureau nacional |
| Boa Vista (Equifax) | https://www.boavistaservicos.com.br/ | Bureau nacional |
| Quod | https://www.quod.com.br/ | Bureau nacional |
| SPC Brasil | https://www.spcbrasil.org.br/ | Cadastros |
| BigDataCorp | https://bigdatacorp.com.br/ | Enriquecimento corporativo |

> 🛑 **Painéis clandestinos não são listados nesta base.** Ver seção 27 para investigar operadores desses painéis.

### 2.2 CPF — Pesquisa e Verificação

| Ferramenta | URL | Função |
|---|---|---|
| Receita Federal | https://www.cpf.receita.fazenda.gov.br/Consultacpf/ | Situação cadastral |
| CadastroPre | https://cadastropre.com.br/ | Linhas ativas por CPF |
| SrWatson | https://srwatson.io/ | Pesquisa agregada |
| RedeCNPJ | https://www.redecnpj.com.br/ | Vínculos societários |
| SINTEGRA | http://www.sintegra.gov.br/ | Inscrição estadual |
| Portal da Transparência | https://www.portaltransparencia.gov.br/pessoa | Servidor público + CPF parcial |
| CEIS/CNEP | https://www.portaltransparencia.gov.br/sancoes | Sanções administrativas |
| eProc/TJRJ, TJSP, etc. | Sites dos tribunais | Processos por CPF |
| Consulta Processual (CNJ) | https://www.cnj.jus.br/consulta-publica/ | Unificada |
| TSE — Filiação Partidária | https://www.tse.jus.br/eleitor/filiacao-partidaria | Por nome |
| CPF-CNPJ.com | https://www.cpfcnpj.com.br/ | Validadores |

**Técnicas legítimas para cruzamento de CPF:**
- Via ofício ao INSS (CNIS) — vínculos empregatícios
- Via ofício ao BACEN (SISBACEN CCS) — contas bancárias
- Via ofício à Receita (CAF, DITR, DIRPF) — declarações
- Via ofício ao SERPRO — Datavalid autenticação facial
- Via ofício ao TSE — situação eleitoral
- Via SINESP Infoseg (acesso regulado por credenciamento institucional)

### 2.3 CNPJ — Pesquisa e Análise

| Ferramenta | URL | Função |
|---|---|---|
| Receita Federal CNPJ | https://solucoes.receita.fazenda.gov.br/servicos/cnpjreva/cnpjreva_solicitacao.asp | Dados cadastrais |
| RedeCNPJ | https://www.redecnpj.com.br/rede/ | Grafo de sócios |
| CNPJ.biz | https://cnpj.biz/ | Dados completos |
| Jusbrasil Empresas | https://www.jusbrasil.com.br/busca | Processos e dados |
| QSA (Quadro Societário) | Via CNPJ.biz | Sócios e participações |
| Brasil.io | https://brasil.io/datasets/ | Dados abertos do governo |
| Econodata | https://www.econodata.com.br/ | Empresas e porte |
| Consulta Sócios | https://consultasocios.com.br/ | Vínculos societários |
| Speedio | https://speedio.com.br/ | B2B intel |
| Cortex Intelligence | https://www.cortex-intelligence.com/ | Dados empresariais |
| Casa dos Dados | https://casadosdados.com.br/ | Grátis com consulta aberta |
| OpenCorporates | https://opencorporates.com/ | Empresas globais |
| TJ Oficial (cada estado) | Site oficial | Processos por CNPJ |
| CNPJ.ws | https://www.cnpj.ws/ | API RESTful gratuita |
| Minha Receita | https://minhareceita.org/ | API da Receita |
| JUCESP / JUCERJA / etc. | Juntas Comerciais | Atos constitutivos |
| OffshoreLeaks (ICIJ) | https://offshoreleaks.icij.org/ | Paraísos fiscais |
| Panama/Pandora Papers | Base ICIJ | Offshore |
| SIAPE Transparência | https://transparencia.gov.br/servidores | Servidores federais |

### 2.4 IMEI — Dispositivos Móveis

| Ferramenta | URL | Função |
|---|---|---|
| Consulta Aparelho | https://consultaaparelhoimpedido.com.br/ | Verificar furto/roubo |
| IMEI.info | https://www.imei.info/ | Modelo e fabricante |
| IMEI24 | https://imei24.com/ | Dados do dispositivo |
| IMEICheck | https://imeicheck.com/ | Verificação completa |
| IMEI Pro | https://imeipro.info/ | Dados de operadora |
| DeviceAtlas | https://deviceatlas.com/ | Dados técnicos do dispositivo |
| CEABS / Proteste IMEI | https://www.celularseguro.gov.br/ | Plataforma oficial MJSP |
| Celular Seguro (MJSP) | https://www.gov.br/mj/pt-br/assuntos/noticias/celular-seguro | App oficial |
| Anatel IMEI | https://www.gov.br/anatel/pt-br | Homologação |
| Swappa IMEI Check | https://swappa.com/esn/check | Verifica por operadora (EUA) |
| ChipMunk IMEI | https://imei.org/ | Consulta internacional |
| FMiPhone Status | https://www.iphoneimei.info/free | Apple iCloud lock |
| Samsung IMEI | https://www.samsung.com/global/ | Informações oficiais |

**Procedimentos formais:**
- Bloqueio pela Anatel (via operadora) e pelo Celular Seguro (MJSP)
- Pedido via ofício à Anatel para histórico de IMEI
- Via operadora: último IMSI associado ao IMEI, última ERB conectada, duplas SIM
- Para crimes: Operação *Carrefour* / *Mão de Ouro* — padrões conhecidos de reset de IMEI

### 2.5 Validadores e Geradores Úteis para Investigação

| Ferramenta | URL | Uso |
|---|---|---|
| Validar CPF/CNPJ | https://www.4devs.com.br/validador_cpf | Confirmar se dígitos são válidos |
| Validador Matemático de CPF | Algoritmo público | Verificar integridade |
| CEP — Correios | https://buscacepinterno.correios.com.br/ | Endereços por CEP |
| CEP API (ViaCEP) | https://viacep.com.br/ | JSON gratuito |
| CEP API (BrasilAPI) | https://brasilapi.com.br/ | Múltiplas APIs |
| Receita WS | https://www.receitaws.com.br/ | CNPJ via API |

### 2.6 Pesquisa por Nome (Brasil)

| Ferramenta | URL | Função |
|---|---|---|
| Jusbrasil Pessoas | https://www.jusbrasil.com.br/ | Processos por nome |
| LinkedIn Search | `site:linkedin.com/in "nome"` | Profissional |
| Escavador | https://www.escavador.com/ | Processos + currículo |
| JusBrasil Processos | — | Agregador jurídico |
| Portal da Transparência | https://www.portaltransparencia.gov.br/pessoa | Servidor público |
| Plataforma Lattes | http://lattes.cnpq.br/ | Pesquisador / acadêmico |
| Tribunais Eleitorais | TSE/TRE | Candidatos, filiações |
| Google Dorks | `"Nome Completo" site:gov.br` | Oficiais |
| OAB | https://cna.oab.org.br/ | Advogados |
| CFM / CRM | https://portal.cfm.org.br/ | Médicos |
| CREA / CAU | Conselhos regionais | Engenheiros/arquitetos |
| CRC / CRO / CRP / CRF | Conselhos regionais | Demais profissionais |

---

## 3. ENDEREÇO IP

### 3.1 Geolocalização e Identificação

| Ferramenta | URL | Função |
|---|---|---|
| IPInfo | https://ipinfo.io/ | Geo + ASN + proxy |
| MaxMind GeoIP | https://www.maxmind.com/en/geoip-demo | Geolocalização comercial |
| IP-API | https://ip-api.com/ | API gratuita |
| IPQualityScore | https://www.ipqualityscore.com/ | Fraude + VPN + proxy |
| WhatIsMyIPAddress | https://whatismyipaddress.com/ | Interface simples |
| BGP.he.net | https://bgp.he.net/ | ASN + roteamento |
| IPFingerprints | https://www.ipfingerprints.com/ | Geolocalização visual |
| MYIP.ms | https://myip.ms/ | Provedor + histórico |
| Registro.br WHOIS | https://registro.br/tecnologia/ferramentas/whois/ | IPs brasileiros |
| InfByIP | https://pt.infobyip.com/ | Bulk lookup |
| Shodan | https://www.shodan.io/ | Dispositivos expostos no IP |
| Censys | https://censys.io/ | Inventário de ativos |
| CriminalIP | https://www.criminalip.io/ | Threat intel por IP |
| GreyNoise | https://www.greynoise.io/ | Ruído de internet |
| AbuseIPDB | https://www.abuseipdb.com/ | Reputação e histórico |
| Spamhaus | https://www.spamhaus.org/lookup/ | Blacklist |
| DNSLYTICS | https://dnslytics.com/ | Análise DNS + IP |
| IP2Location | https://www.ip2location.com/ | Geo + tipo |
| IPGeolocation.io | https://ipgeolocation.io/ | API REST |
| KeyCDN IP Tools | https://tools.keycdn.com/geo | Suite gratuita |
| DB-IP | https://db-ip.com/ | Base atualizada diária |
| IPAPI.co | https://ipapi.co/ | API simples |
| Team Cymru IP/ASN | https://www.team-cymru.com/ip-asn-mapping | Institucional |
| Hurricane Electric BGP | https://bgp.he.net/ | BGP toolkit |
| PeeringDB | https://www.peeringdb.com/ | Trocas de tráfego |
| RIPEstat | https://stat.ripe.net/ | RIPE NCC — Europa |
| LACNIC WHOIS | https://www.lacnic.net/ | América Latina |
| ARIN WHOIS | https://www.arin.net/ | América do Norte |
| APNIC WHOIS | https://www.apnic.net/ | Ásia-Pacífico |
| AFRINIC WHOIS | https://www.afrinic.net/ | África |
| SpurDB | https://spur.us/ | Detecção VPN/proxy avançada |
| BinaryEdge | https://www.binaryedge.io/ | Attack surface |
| Netlas | https://netlas.io/ | Alternativa Shodan/Censys |
| CrimeFlare (histórico) | — | Bypass de Cloudflare (por IP histórico) |
| IP Void | https://www.ipvoid.com/ | Multi-blacklist |
| Robtex | https://www.robtex.com/ | Relacionamentos |
| IPQualityScore VPN Lookup | https://www.ipqualityscore.com/vpn-ip-address-check | Detecção VPN |

### 3.2 Identificação de VPN, TOR e Proxy

| Ferramenta | URL |
|---|---|
| IPQualityScore | https://www.ipqualityscore.com/ |
| CriminalIP | https://www.criminalip.io/ |
| DarkTracer | https://darktracer.io/ |
| Tor Exit Nodes | https://metrics.torproject.org/exonerator.html |
| VPNAPI.io | https://vpnapi.io/vpn-detection |
| IP2Proxy | https://www.ip2proxy.com/ |
| ProxyCheck | https://proxycheck.io/ |
| GetIPIntel | https://getipintel.net/ |
| TorNodes (DAN) | https://www.dan.me.uk/tornodes |
| IntelligenceX VPN/Tor | https://intelx.io/ |
| SpurDB | https://spur.us/ |
| Moonshot ExchangePoint | https://moonshotvpn.tools/ |
| ShodanTor Query | `tag:tor` no Shodan |
| RelayStatus (Tor) | https://metrics.torproject.org/rs.html |

### 3.3 IP Reverso — Domínios no Mesmo IP

| Ferramenta | URL |
|---|---|
| ReverseIP | https://reverseip.domaintools.com/ |
| ViewDNS | https://viewdns.info/reverseip/ |
| HackerTarget | https://hackertarget.com/reverse-ip-lookup/ |
| DNSlytics | https://dnslytics.com/reverse-ip |
| SecurityTrails | https://securitytrails.com/ |
| Shodan | `ip:xxx.xxx.xxx.xxx` |
| Bing Dork | `ip:xxx.xxx.xxx.xxx` |
| Netlas Reverse IP | https://app.netlas.io/ |
| Spyse (Netlas) | https://netlas.io/ |
| Rapid7 Sonar | https://opendata.rapid7.com/ |
| Fofa Reverse IP | https://fofa.info/ |
| ZoomEye | https://www.zoomeye.org/ |
| Yougetsignal | https://www.yougetsignal.com/tools/web-sites-on-web-server/ |

### 3.4 Investigação de Infraestrutura

| Ferramenta | URL | Função |
|---|---|---|
| Shodan | https://www.shodan.io/ | Dispositivos e serviços expostos |
| Censys | https://censys.io/ | Inventário TLS + portas |
| FOFA | https://fofa.info/ | Alternativa ao Shodan (chinês) |
| ZoomEye | https://www.zoomeye.org/ | Cyberspace search engine |
| BinaryEdge | https://www.binaryedge.io/ | Attack surface |
| Onyphe | https://www.onyphe.io/ | Passive DNS + threat intel |
| Leakix | https://leakix.net/ | Dados e servidores expostos |
| Netlas | https://netlas.io/ | Alternativa moderna |
| Hunter.how | https://hunter.how/ | Busca em código |
| Quake (360) | https://quake.360.cn/ | Alternativa chinesa |
| Criminal IP | https://www.criminalip.io/ | Threat intel focada |
| PulseDive | https://pulsedive.com/ | Free tier generoso |
| Rapid7 Open Data | https://opendata.rapid7.com/ | Sonar datasets |
| Scans.io | https://scans.io/ | Dumps de varredura |

### 3.5 CGNAT e Porta Lógica de Origem

> **Conceito:** Com CGNAT, múltiplos usuários compartilham o mesmo IP público. Para identificar o usuário específico, é necessário também obter a **porta lógica de origem** e o **timestamp exato** em UTC. Muitos provedores locais não armazenam essa informação — verifique via ofício administrativo conforme Marco Civil da Internet (art. 13 a 15).

**Passos para investigação com CGNAT:**
1. Identificar o IP e timestamp do evento (preferencialmente em UTC)
2. Oficiar o provedor de aplicação (plataforma onde ocorreu o crime) solicitando: IP público, IP privado (se aplicável), porta de origem, timestamp UTC, user-agent, device fingerprint
3. Oficiar o provedor de conexão (ISP) com esses dados completos
4. O ISP consegue identificar o assinante com IP + porta + timestamp (CGNAT translation log)
5. Documentar cada etapa na cadeia de custódia

**ISPs brasileiros e CGNAT (observações gerais):**
- Grandes operadoras (Claro/NET, Vivo/Telefônica, TIM, Oi) geralmente mantêm logs CGNAT por 6 meses (conforme MCI)
- Provedores regionais/pequenos podem ter retenção menor — prioridade em ofícios urgentes
- Considerar NAT444 e dual-stack IPv4/IPv6 (IPv6 nativo dispensa CGNAT)

**Referências técnicas:**
- RFC 6888 (CGN behavioral requirements)
- RFC 7422 (Deterministic CGN)
- Resolução Anatel nº 614/2013 (registro de conexão)

### 3.6 DNSBL — Blacklists de IP

| Ferramenta | URL |
|---|---|
| MXToolbox Blacklist | https://mxtoolbox.com/blacklists.aspx |
| MultiRBL | https://multirbl.valli.org/ |
| Spamhaus | https://www.spamhaus.org/lookup/ |
| Barracuda | https://www.barracudacentral.org/lookups |
| SORBS | https://www.sorbs.net/ |
| SpamCop | https://www.spamcop.net/ |
| DNSBL.info | https://www.dnsbl.info/ |
| HetrixTools | https://hetrixtools.com/blacklist-check/ |

### 3.7 Passive DNS e Histórico de Resoluções

| Ferramenta | URL | Função |
|---|---|---|
| Circl.lu Passive DNS | https://www.circl.lu/services/passive-dns/ | Gratuito com registro |
| Farsight DNSDB | https://www.farsightsecurity.com/ | Comercial |
| SecurityTrails | https://securitytrails.com/ | Histórico completo |
| Mnemonic PassiveDNS | https://passivedns.mnemonic.no/ | Comunidade |
| RiskIQ / PassiveTotal | https://community.riskiq.com/ | Comunidade Microsoft |
| ZETAlytics | https://zetalytics.com/ | Comercial |
| VirusTotal Passive DNS | https://www.virustotal.com/ | Por IP/domínio |
| DomainTools Iris | https://www.domaintools.com/products/iris-investigate/ | Comercial |

### 3.8 ASN — Análise de Autonomous System

| Ferramenta | URL | Função |
|---|---|---|
| Hurricane Electric | https://bgp.he.net/ | Explorador BGP |
| PeeringDB | https://www.peeringdb.com/ | Trocas e contatos |
| RIPEstat ASN | https://stat.ripe.net/ | Análise avançada |
| BGPView | https://bgpview.io/ | UI simples |
| ASRank (CAIDA) | https://asrank.caida.org/ | Ranking global |
| NIC.BR LG | https://lg.ix.br/ | Looking Glass |
| Cymru Bogon Reference | https://www.team-cymru.com/bogon-reference | IPs inválidos |

---

## 4. DOMÍNIO E INFRAESTRUTURA WEB

### 4.1 WHOIS e Registro

| Ferramenta | URL | Observação |
|---|---|---|
| Registro.br | https://registro.br/tecnologia/ferramentas/whois/ | Domínios .br |
| ICANN Lookup | https://lookup.icann.org/ | Global |
| Who.is | https://who.is/ | Interface amigável |
| Whois.com | https://www.whois.com/ | Completo |
| DomainTools | https://whois.domaintools.com/ | Histórico + pivô |
| Whoxy | https://www.whoxy.com/ | Reverso por e-mail/nome |
| ReverseWhois | https://www.reversewhois.io/ | Busca por owner |
| Synapsint | https://www.synapsint.com/ | Multipivô |
| Robtex | https://www.robtex.com/ | DNS + IP |
| IANA WHOIS | https://www.iana.org/whois | Autoridade máxima |
| NetworkSolutions | https://www.networksolutions.com/domains/whois | Alternativa |
| Whoisology | https://whoisology.com/ | Banco histórico |
| DotDB | https://dotdb.com/ | Base de domínios |
| CentralOps | https://centralops.net/co/ | Multi-ferramenta |
| Hunter.how | https://hunter.how/ | Busca em código-fonte |
| DomainIQ | https://www.domainiq.com/ | WHOIS + reputação |
| JsonWHOIS | https://jsonwhois.com/ | API |
| WhoisXML | https://www.whoisxmlapi.com/ | API comercial |
| DNSlytics Owner Search | https://dnslytics.com/domain | Enriquecido |
| whois.ds (plataforma) | https://whois.ds/ | Unificado |
| WhoDoesThat | https://whodoesthat.com/ | Reverso por registrant |
| Snov.io Domain Search | https://snov.io/domain-search | E-mails + registrante |

### 4.2 DNS e Registros

| Ferramenta | URL | Função |
|---|---|---|
| DNSDumpster | https://dnsdumpster.com/ | Mapa DNS visual |
| MXToolbox DNS | https://mxtoolbox.com/DnsLookup.aspx | Todos os tipos de registro |
| ViewDNS | https://viewdns.info/ | Multi-consulta |
| SecurityTrails | https://securitytrails.com/ | DNS histórico |
| PassiveDNS (CIRCL) | https://www.circl.lu/services/passive-dns/ | Passivo |
| HackerTarget DNS | https://hackertarget.com/dns-lookup/ | Gratuito |
| DNSTwist | https://dnstwist.it/ | Domínios semelhantes (phishing) |
| DNSHistory | https://dnshistory.org/ | Histórico DNS |
| CompleteDNS | https://completedns.com/dns-history/ | Histórico de mudanças |
| DNSGrep (Rapid7) | https://scans.io/ | Dump de resoluções |
| intoDNS | https://intodns.com/ | Auditoria DNS |
| Google Public DNS | https://dns.google/ | Resolver |
| Cloudflare 1.1.1.1 Debug | https://1.1.1.1/help | Debug rápido |
| NSLookup.io | https://www.nslookup.io/ | Interface moderna |
| DNSChecker | https://dnschecker.org/ | Propagação global |
| Linux: `dig` | Linha de comando | Consulta nativa |
| Linux: `nslookup` | Linha de comando | Consulta interativa |
| Linux: `host` | Linha de comando | Simplificado |
| Linux: `dnsx` | https://github.com/projectdiscovery/dnsx | Toolkit avançado |

### 4.3 Hospedagem e Servidor

| Ferramenta | URL |
|---|---|
| HostingChecker | https://hostingchecker.com/ |
| WhoHostsThis | https://www.who-hosts-this.com/ |
| Digital.com | https://digital.com/who-is-hosting-this/ |
| Synapsint | https://www.synapsint.com/ |
| AdminKit | https://adminkit.net/traceroute.aspx |
| HostAdvice Host Detector | https://hostadvice.com/tools/web-host-lookup/ |
| Netcraft SiteReport | https://sitereport.netcraft.com/ |
| IsItWP Hosting Checker | https://www.isitwp.com/whos-hosting/ |

### 4.4 Tecnologias e Código-Fonte

| Ferramenta | URL | Função |
|---|---|---|
| BuiltWith | https://builtwith.com/ | Stack tecnológico |
| Wappalyzer | https://www.wappalyzer.com/ | Plugin + site |
| WhatCMS | https://whatcms.org/ | CMS identificador |
| PublicWWW | https://publicwww.com/ | Busca em código-fonte |
| Hunter.how | https://hunter.how/ | Indexação de código |
| Shodan | https://www.shodan.io/ | Cabeçalhos HTTP |
| WebTech | https://github.com/ShielderSec/webtech | Alternativa ao Wappalyzer |
| Whatruns | https://www.whatruns.com/ | Extensão + site |
| Retire.js | https://retirejs.github.io/retire.js/ | JavaScript vulnerável |
| Netcraft | https://toolbar.netcraft.com/ | Reputação + tech |
| NerdyData | https://www.nerdydata.com/ | Busca em código em massa |
| Full Hunt | https://fullhunt.io/ | Attack surface |
| CRT Search Code | https://crt.sh/ | Certificados como pivô |

**Identificadores no código-fonte:**

| Identificador | Prefixo | Uso |
|---|---|---|
| Google Analytics | `UA-`, `G-` | Pivô entre sites |
| Google AdSense | `pub-` | Proprietário do site |
| Google Tag Manager | `GTM-` | Rastreamento |
| Facebook Pixel | `fbq('init', '` | ID do anunciante |
| Yandex Metrica | `ym(` | Proprietário |
| Microsoft Clarity | `clarity.ms` | ID de projeto |
| Hotjar | `hjid` | ID da conta |
| Mixpanel | `mixpanel.init(` | Token |
| Matomo/Piwik | `matomo.js` | Servidor próprio |
| Adobe Analytics | `s_account` | Report suite |
| Disqus | `disqus_shortname` | Conta Disqus |
| PayPal Button | `hosted_button_id` | Conta PayPal |
| Stripe | `pk_live_`, `pk_test_` | Chave pública |
| Segment | `analytics.load(` | Write key |
| reCAPTCHA | `data-sitekey` | Chave do site |
| Cloudflare Turnstile | `sitekey` | ID |
| Intercom | `app_id` | Conta Intercom |

### 4.5 Histórico e Cache

| Ferramenta | URL |
|---|---|
| Wayback Machine | https://archive.org/ |
| Archive.today | https://archive.ph/ |
| CachedView | https://cachedview.com/ |
| CachedPage | https://cachedpage.co/ |
| Google Cache | `cache:url` no Google |
| Timetravel | https://timetravel.mementoweb.org/ |
| Wayback Machine API | https://archive.org/help/wayback_api.php |
| UK Web Archive | https://www.webarchive.org.uk/ |
| Perma.cc (Harvard) | https://perma.cc/ | Preservação legal |
| Conifer (ex-Webrecorder) | https://conifer.rhizome.org/ |
| PageFreezer | https://www.pagefreezer.com/ | Preservação jurídica |
| Screenshots.com | https://www.screenshots.com/ |
| ArchiveBox | https://archivebox.io/ | Self-hosted |

### 4.6 Verificação de Segurança e Phishing

| Ferramenta | URL |
|---|---|
| VirusTotal | https://www.virustotal.com/ |
| URLScan | https://urlscan.io/ |
| DNSTwist | https://dnstwist.it/ |
| PhishTank | https://phishtank.org/ |
| SiteConfiável | https://www.siteconfiavel.com.br/ |
| AbuseIPDB | https://www.abuseipdb.com/ |
| Google SafeBrowsing | https://safebrowsing.google.com/safebrowsing/report_phish/ |
| Sucuri SiteCheck | https://sitecheck.sucuri.net/ |
| IsItPhishing | https://isitphishing.ai/ |
| PhishStats | https://phishstats.info/ |
| OpenPhish | https://openphish.com/ |
| URLhaus | https://urlhaus.abuse.ch/ |
| Joe Sandbox URL | https://www.joesandbox.com/ |
| AnyRun (URL) | https://any.run/ |
| Hybrid Analysis URL | https://www.hybrid-analysis.com/ |
| Kaspersky Threat Intel Portal | https://opentip.kaspersky.com/ |
| Talos Intelligence | https://talosintelligence.com/ |
| Quttera | https://www.quttera.com/ |
| Netcraft Takedown | https://www.netcraft.com/ |
| SafeBrowsing Lookup API | Google API | Integração |
| Bitdefender TrafficLight | https://trafficlight.bitdefender.com/ |
| CheckPhish.ai | https://checkphish.ai/ |

### 4.7 Cloudflare e Bypass (técnicas legítimas de descoberta de origem)

| Ferramenta | URL | Técnica |
|---|---|---|
| CloudFlare IP Range | https://www.cloudflare.com/pt-br/ips/ | Lista de IPs CF |
| SecurityTrails | https://securitytrails.com/ | Histórico DNS antes do CF |
| Shodan | `ssl.cert.subject.cn:dominio.com` | Certificado TLS |
| CrimeFlare (legacy) | — | Bypass CF (histórico) |
| ViewDNS History | https://viewdns.info/iphistory/ | IP histórico |
| SUIP | https://suip.biz/?act=iscloudflare | Detecta CF |
| CloudFail | https://github.com/m0rtem/CloudFail | Automação |
| CloudUnflare | https://github.com/jaynakrani/cloudunflare | Subdominio discovery |
| Censys Cert Search | https://search.censys.io/ | Por CN/SAN |
| CrimeScan | https://www.criminalip.io/ | Attack surface |
| DNSdb (Farsight) | — | Passive histórico |

> ⚠️ **Nota:** Bypass de WAF/proxy é legítimo em investigações para **identificar o servidor de origem** de serviços criminosos (phishing, carding, CSAM). Não confundir com "bypass de proteção" de sites legítimos (isso violaria termos de serviço e pode configurar invasão).

### 4.8 Certificados SSL/TLS

| Ferramenta | URL |
|---|---|
| crt.sh | https://crt.sh/ |
| Censys | https://search.censys.io/ |
| SSLLabs | https://www.ssllabs.com/ssltest/ |
| Cert Spotter | https://sslmate.com/certspotter/ |
| Censys Certs | https://search.censys.io/certificates |
| Google CT Log | https://crt.sh/?q=&caid= |
| CertStream (live) | https://certstream.calidog.io/ |
| Facebook CT Monitor | https://developers.facebook.com/tools/ct/ |
| CertDB | https://certdb.com/ |
| Merklemap | https://www.merklemap.com/ |
| Entrust CT Search | https://ui.ctsearch.entrust.com/ |

### 4.9 Subdomínios — Descoberta

| Ferramenta | URL | Tipo |
|---|---|---|
| Subfinder | https://github.com/projectdiscovery/subfinder | CLI |
| Amass | https://github.com/owasp-amass/amass | CLI completo |
| assetfinder | https://github.com/tomnomnom/assetfinder | CLI rápido |
| chaos-client | https://github.com/projectdiscovery/chaos-client | ProjectDiscovery |
| crt.sh (dork) | `%.dominio.com` | Web |
| HackerTarget | https://hackertarget.com/find-dns-host-records/ | Web |
| Certspotter | https://sslmate.com/certspotter/api | API |
| VirusTotal Subdomains | https://www.virustotal.com/ | Domain relations |
| SecurityTrails | https://securitytrails.com/ | Comercial |
| Shodan | `hostname:dominio.com` | Paga |
| GitHub Dork | `"dominio.com"` in repos | Manual |
| DNS Brute-force | wordlists + dnsx | CLI |
| FindSubdomains | https://findsubdomains.com/ | Web |
| Sublist3r | https://github.com/aboul3la/Sublist3r | CLI Python |

### 4.10 Google Dorks para Domínios

```
site:dominio.com                    # Tudo indexado
site:dominio.com filetype:pdf       # PDFs expostos
site:dominio.com inurl:admin        # Painéis admin
site:dominio.com intext:"password"  # Senhas expostas
site:dominio.com ext:sql            # Bancos de dados
inurl:dominio.com intitle:index.of  # Directory listing
link:dominio.com                    # Backlinks
"UA-XXXXXXXX" -site:dominio.com     # Outros sites com mesmo Analytics
site:dominio.com inurl:wp-content   # WordPress
site:dominio.com inurl:"/.git"      # Git exposto
site:dominio.com intitle:"phpinfo()" # Info PHP
site:dominio.com intitle:"swagger"  # API docs
site:dominio.com intitle:"Login" OR intitle:"Sign In" # Páginas auth
site:dominio.com ext:env OR ext:log OR ext:bak # Arquivos sensíveis
```

---


## 5. USERNAMES E IDENTIDADES DIGITAIS

### 5.1 Busca por Username na Web

| Ferramenta | URL | Cobertura |
|---|---|---|
| Sherlock | https://github.com/sherlock-project/sherlock | +300 sites |
| WhatsMyName | https://whatsmyname.app/ | Visual + extenso |
| Maigret | https://github.com/soxoj/maigret | +2500 sites |
| Blackbird | https://github.com/p1ngul1n0/blackbird | Rápido |
| SocialScan | https://github.com/iojw/socialscan | E-mail + user |
| Investigo | https://github.com/tdh8316/Investigo | Go lang |
| Pyosint | https://github.com/d8rkmind/Pyosint | Python |
| Social Analyzer | https://github.com/qeeqbox/social-analyzer | Multi-thread |
| UserSearch | https://usersearch.org/ | Web |
| CheckUsernames | https://checkusernames.com/ | Web |
| KnowEm | https://knowem.com/ | Marcas + usuários |
| NameCheckr | https://www.namecheckr.com/ | Web |
| InstantUsername | https://instantusername.com/ | Web |
| Namevine | https://namevine.com/ | Web |
| Social-Searcher | https://www.social-searcher.com/ | Posts públicos |
| Snoop Project | https://github.com/snooppr/snoop | Ex-URSS + global |
| Thorndyke | https://github.com/markusbackstrom/thorndyke | Ruby |
| WhatsMyUsername | https://github.com/WebBreacher/WhatsMyName | Source do whatsmyname |
| NameRec | https://github.com/HA71/Namechk | Enum massivo |
| Profil3r | https://github.com/Rog3rSm1th/Profil3r | OSINT person |
| Recon OS | https://reconos.io/ | Web agregadora |
| UserProbe | https://userprobe.com/ | Web |
| NameCheckup | https://namecheckup.com/ | Web |
| CheckName | https://check-name.com/ | Web |
| Sawek (Checkusername) | https://checkuser.org/ | Web |

### 5.2 Correlação de Identidades

**Técnicas de pivô por username:**
1. Buscar o mesmo username em múltiplas plataformas
2. Analisar bio, foto de perfil e links cruzados
3. Buscar o username entre aspas no Google: `"username_alvo"`
4. Verificar variações: `username_`, `_username`, `username123`
5. Analisar histórico via Wayback Machine
6. Extrair hash de imagem de perfil e reversar em outras redes
7. Comparar estilo de escrita (stylometry) entre contas suspeitas
8. Verificar timestamps de posts (fuso horário do alvo)
9. Analisar padrões de hashtags e amigos em comum

**Google Dorks por username:**
```
"username" site:reddit.com
"username" site:github.com
"username" site:twitter.com
"username" -site:twitter.com -site:instagram.com
inurl:"/username" (plataforma)
"username" site:medium.com
"username" site:dev.to
"username" filetype:pdf
"username" AND ("nome" OR "cidade")
```

### 5.3 Identidades em Fóruns e Comunidades

| Plataforma | Técnica de Busca |
|---|---|
| Reddit | `site:reddit.com "username"` ou reddit.com/user/USERNAME |
| GitHub | `https://github.com/username` + API |
| Stack Overflow | Busca direta no perfil |
| Telegram | Bots: @SangMata_BOT, @TgScanRobot |
| Discord | Servidores de lookup (com cautela legal) |
| 4chan / 8chan / 8kun | Arquivo: https://archived.moe/ |
| Pastebin | `site:pastebin.com "username"` |
| HackForums | Busca interna |
| Dread (dark) | Apenas com OPSEC + autorização |
| Exploit.in | Monitoramento via intel |
| XSS.is | Monitoramento via intel |
| DuckDuckGo Forums | `site:duckduckgo.com "username"` |
| Steam | https://steamcommunity.com/id/USERNAME/ |
| Roblox | Roblox.com/users/ID |
| Xbox Live | https://xboxgamertag.com/ |
| PSN | https://psnprofiles.com/ |
| Epic Games | Fortnite tracker |
| Minecraft | https://namemc.com/ |
| Twitch | https://www.twitch.tv/USERNAME |

### 5.4 Análise de Atividade e Padrões

| Ferramenta | URL | Função |
|---|---|---|
| Tinfoleak | https://github.com/vaguileradiaz/tinfoleak | Padrões de atividade (Twitter) |
| Sleep Tracker (Twitter) | Via Tweetdeck + análise | Fuso horário |
| SocialBearing | https://socialbearing.com/ | Twitter analytics |
| Reddit User Analytics | https://www.redditinvestigator.com/ | Perfil Reddit |
| GitHub Activity | API + graph | Horários de commits |
| InstAnalytics | — | Padrões Instagram |

---

## 6. IMAGENS E VÍDEOS (IMINT)

### 6.1 Pré-processamento de Imagens

| Necessidade | Ferramenta | URL |
|---|---|---|
| Extrair frame de vídeo | VLC / FFmpeg | Locais |
| Melhorar qualidade | LetsEnhance | https://letsenhance.io/ |
| Melhorar qualidade | PicWish | https://picwish.com/ |
| Melhorar qualidade | UpscaleMedia | https://www.upscale.media/ |
| Melhorar qualidade | Topaz Gigapixel | https://www.topazlabs.com/ |
| Melhorar qualidade | Real-ESRGAN (local) | https://github.com/xinntao/Real-ESRGAN |
| Remover fundo | Remove.bg | https://www.remove.bg/ |
| Remover fundo | Pixlr | https://pixlr.com/ |
| Remover fundo | BRIA (HF) | https://huggingface.co/briaai/RMBG-1.4 |
| Remover objeto | Cleanup.pictures | https://cleanup.pictures/ |
| Remover objeto | Inpaint-web | https://www.inpaint-web.com/ |
| Remover marca d'água | WatermarkRemover | https://www.watermarkremover.io/ |
| Desfocagem reversa | SmartDeblur | http://smartdeblur.net/ |
| Desfocagem reversa | ImageJ + plugin | https://imagej.nih.gov/ |
| Análise forense | FotoForensics | https://fotoforensics.com/ |
| Análise de JPG | JPEGSnoop | https://jpegsnoop.softonic.com.br/ |
| ELA (Error Level Analysis) | https://fotoforensics.com/ | Detectar edição |
| Clone Detection | Forensically | https://29a.ch/photo-forensics/ |
| Noise Analysis | Forensically | https://29a.ch/photo-forensics/ |
| Deblur (stable) | https://deblur.app/ | Online |
| OCR (Tesseract) | https://github.com/tesseract-ocr/tesseract | CLI |
| OCR online | https://www.onlineocr.net/ | Web |
| OCR (PaddleOCR) | https://github.com/PaddlePaddle/PaddleOCR | Open source |
| OCR (docTR / OnnxTR) | https://github.com/mindee/doctr | Por deep learning |

### 6.2 Busca Reversa de Imagem

| Ferramenta | URL | Especialidade |
|---|---|---|
| Google Images | https://images.google.com/ | Indexação global |
| Google Lens | https://lens.google.com/ | Mobile + desktop |
| Yandex Images | https://yandex.com/images/ | Melhor para rostos |
| Bing Images | https://www.bing.com/?scope=images | Alternativo |
| TinEye | https://tineye.com/ | Correspondência exata |
| PimEyes | https://pimeyes.com/ | Reconhecimento facial (pago) |
| FaceCheck.id | https://facecheck.id/ | Facial em redes sociais |
| Search4Faces | https://search4faces.com/ | Redes sociais russas |
| Reverse Image Search | https://www.reverse-image-search.org/ | Multi-motor |
| Duplichecker | https://www.duplichecker.com/ | Multi-busca |
| Jimpl | https://jimpl.com/ | Metadados + busca |
| RootAbout | https://rootabout.com/ | Alternativo |
| ImgOps | https://imgops.com/ | Hub de ferramentas |
| KarmaDecay | http://karmadecay.com/ | Busca no Reddit |
| Imgur | https://imgur.com/ | Tags e usuários |
| ImageIdentify | https://www.imageidentify.com/ | Classificação por IA |
| Lenso.ai | https://lenso.ai/ | Busca reversa IA |
| Labnol Reverse Search | https://labnol.org/reverse/ | Agregador |
| Photutorial Reverse | https://photutorial.com/tools/ | Agregador |
| SauceNAO | https://saucenao.com/ | Anime/manga/art |
| IQDB | https://iqdb.org/ | Anime focused |
| Ascii2D | https://ascii2d.net/ | Japonês (manga) |
| Google Photos Reverse (SerpAPI) | https://serpapi.com/ | API comercial |
| Social Catfish | https://socialcatfish.com/ | Reverse por pessoa |

> ⚠️ **Ética e reconhecimento facial:** Ferramentas como PimEyes, FaceCheck.id e Clearview (policial) usam raspagem massiva de fotos públicas. O uso por agente público exige:
> - Autorização judicial/administrativa específica em investigações
> - Observância da LGPD (bases legais do art. 7º e 11)
> - Documentação robusta em cadeia de custódia
> - Conhecimento de que resultados podem gerar falsos positivos — **nunca basear prisão ou identificação formal apenas em match facial**
> Ver seção 26.

### 6.3 Reconhecimento e Comparação Facial

| Ferramenta | URL | Observação |
|---|---|---|
| Face++ | https://www.faceplusplus.com/ | API profissional |
| MxFace | https://mxface.ai/face-comparing | Comparação direta |
| FaceComparison | https://facecomparison.toolpie.com/ | Online gratuito |
| Pictriev | http://www.pictriev.com/ | Análise de semelhança |
| Kairos | https://www.kairos.com/ | API comercial |
| AWS Rekognition | https://aws.amazon.com/rekognition/ | Escala empresarial |
| Azure Face API | https://azure.microsoft.com/en-us/services/cognitive-services/face/ | Microsoft |
| BetaFace | https://www.betafaceapi.com/ | API gratuita |
| DeepFace (open-source) | https://github.com/serengil/deepface | Biblioteca Python |
| InsightFace | https://github.com/deepinsight/insightface | Biblioteca open-source |
| CompreFace | https://github.com/exadel-inc/CompreFace | Self-hosted |
| FaceNet | https://github.com/davidsandberg/facenet | Research |
| OpenCV Face | https://opencv.org/ | Biblioteca |
| ArcFace | https://arxiv.org/abs/1801.07698 | SOTA em research |

> ⚠️ O reconhecimento facial está sujeito a restrições legais em diversas jurisdições. Use apenas com autorização judicial e registros adequados. **No Brasil**, já há discussões sobre banimento em espaços públicos e normativas como as do Decreto 10.046/2019 e a ADI sobre videomonitoramento com reconhecimento facial. Ver guidance da ANPD.

### 6.4 Metadados EXIF de Imagens

| Ferramenta | URL / Comando |
|---|---|
| ExifTool | `exiftool imagem.jpg` (Linux/Windows) |
| FotoForensics | https://fotoforensics.com/ |
| ImgOps | https://imgops.com/ |
| ViewExifData | http://www.viewexifdata.com/ |
| ExifData | https://exifdata.com/ |
| Pic2Map | https://www.pic2map.com/ |
| Metadata2Go | https://www.metadata2go.com/ |
| OnlineExifViewer | https://onlineexifviewer.com/ |
| Verexif | https://www.verexif.com/ |
| Thexifer | https://www.thexifer.net/ |
| StolenCameraFinder | https://www.stolencamerafinder.com/ |
| Jimpl | https://jimpl.com/ |
| Metapicz | http://metapicz.com/ |
| Exif Pilot | https://www.colorpilot.com/exif.html |
| Extract Metadata (web) | https://www.extractmetadata.com/ |

**Dados extraíveis de EXIF:**
- Coordenadas GPS (latitude/longitude)
- Data e hora da captura
- Modelo e fabricante da câmera/celular
- Software de edição utilizado
- Orientação e configurações da câmera
- Número de série do dispositivo (em alguns casos)
- Owner/Copyright
- Lens used
- ISO, shutter speed, aperture
- Flash usage
- Software/firmware version
- Color profile

### 6.5 Detecção de Deepfake e Manipulação

| Ferramenta | URL |
|---|---|
| Photo Forensics | https://29a.ch/photo-forensics/ |
| FaceForensics++ | http://www.faceforensics.com/ |
| Deepware Scanner | https://deepware.ai/ |
| Hive Moderation | https://hivemoderation.com/ai-generated-content-detection |
| Illuminarty | https://illuminarty.ai/ |
| AI or Not | https://www.aiornot.com/ |
| InVID / WeVerify | https://weverify.eu/ |
| Sensity AI | https://sensity.ai/ |
| Intel FakeCatcher | https://www.intel.com/ | PPG analysis |
| Optic AI or Not | https://aiornot.com/ |
| Maybe's AI Art Detector | https://huggingface.co/spaces/umm-maybe/AI-image-detector |
| Duckduckgoose | https://www.duckduckgoose.ai/ |
| Reality Defender | https://www.realitydefender.com/ |
| DeepFake-o-meter (UB) | https://zinc.cse.buffalo.edu/ | Research |
| Content Credentials (C2PA) | https://c2pa.org/ | Autenticação |
| Truepic | https://truepic.com/ | Autenticação de captura |

### 6.6 Esteganografia

| Ferramenta | URL / Comando | Função |
|---|---|---|
| Steghide | `steghide extract -sf imagem.jpg` | Extrai dados ocultos |
| Hexed.it | https://hexed.it/ | Inspeção hexadecimal |
| Stegsolve | Java app | Análise de camadas |
| zsteg | `zsteg imagem.png` | Análise de PNG/BMP |
| OpenStego | https://www.openstego.com/ | Open-source |
| Aperisolve | https://www.aperisolve.com/ | Multi-análise online |
| Stegoveritas | https://github.com/bannsec/stegoVeritas | Automático |
| Outguess | https://github.com/resurrecting-open-source-projects/outguess | JPEG |
| Foremost | https://github.com/korczis/foremost | File carving |
| Binwalk | https://github.com/ReFirmLabs/binwalk | Firmware + arquivos embutidos |
| StegOnline | https://stegonline.georgeom.net/ | Web |
| DeepSound | http://jpinsoft.net/deepsound/ | Áudio |
| StegDetect | — | Detecção |

### 6.7 Análise de Vídeo

| Ferramenta | URL | Função |
|---|---|---|
| FFmpeg | https://ffmpeg.org/ | Multi-uso CLI |
| InVID Verification Plugin | https://www.invid-project.eu/tools-and-services/invid-verification-plugin/ | Browser extension |
| YouTube DataViewer | https://citizenevidence.amnestyusa.org/ | Hora real de upload |
| Montage | https://montage.meedan.com/ | Colaborativo |
| Checkmate (Meedan) | https://meedan.com/check/ | Verificação |
| ffprobe | FFmpeg suite | Metadados de vídeo |
| Exiftool (vídeo) | `exiftool video.mp4` | Metadados |
| MediaInfo | https://mediaarea.net/en/MediaInfo | Detalhes técnicos |
| ShotDeck | https://shotdeck.com/ | Bibliotecário de frames (cinema) |
| Video Forensic Analysis | https://video.forensafe.com/ | Análise forense |
| Amped Authenticate | https://ampedsoftware.com/authenticate | Perícia profissional |
| Reality Defender Video | https://www.realitydefender.com/ | Deepfake vídeo |

### 6.8 OSINT em Imagens AI-Generated

| Ferramenta | URL | Função |
|---|---|---|
| SDXL Detector | Hugging Face | Stable Diffusion |
| Maybe's AI Detector | https://huggingface.co/spaces/umm-maybe/AI-image-detector | Multi-model |
| Illuminarty | https://illuminarty.ai/ | Comercial |
| AI Image Detector (Huggingface) | https://huggingface.co/organizations/detect-ai | Vários |
| C2PA Verify | https://contentcredentials.org/verify | Padrão aberto |
| Imagen Detector (Google) | — | Interno Google |

---


## 7. GEOLOCALIZAÇÃO E GEOINT

### 7.1 Ferramentas de Geolocalização

| Ferramenta | URL | Função |
|---|---|---|
| Google Earth | https://earth.google.com/ | Visualização 3D |
| Google Maps | https://maps.google.com/ | Street View + satélite |
| Bing Maps | https://www.bing.com/maps | Alternativa |
| Yandex Maps | https://yandex.com/maps/ | Boa cobertura Europa/CIS |
| OpenStreetMap | https://www.openstreetmap.org/ | Dados abertos |
| ArcGIS | https://www.arcgis.com/ | Profissional |
| Mapillary | https://www.mapillary.com/ | Fotos em nível de rua colaborativas |
| KartaView | https://kartaview.org/ | Alternativa ao Street View |
| What3Words | https://what3words.com/ | Localização em 3 palavras |
| Wikimapia | http://wikimapia.org/ | Locais com descrição colaborativa |
| Overpass Turbo | https://overpass-turbo.eu/ | Consulta OSM avançada |
| OpenStreetCam (KartaView) | https://kartaview.org/ | Street-level fotos |
| BaiduMaps | https://map.baidu.com/ | China |
| Naver Maps | https://map.naver.com/ | Coreia do Sul |
| Kakao Maps | https://map.kakao.com/ | Coreia do Sul |
| 2GIS | https://2gis.com/ | Rússia + ex-URSS |
| Here Maps | https://wego.here.com/ | Alternativa profissional |
| MapCrunch | http://www.mapcrunch.com/ | Street View random |
| GeoGuessr | https://www.geoguessr.com/ | Treinamento GEOINT |

### 7.2 Estimativa de Localização por Imagem

| Ferramenta | URL | Método |
|---|---|---|
| GeoEstimation (TIB) | https://labs.tib.eu/geoestimation/ | IA — estimativa por imagem |
| GeoSpy | https://geospy.ai/ | IA — geolocalização |
| Picarta | https://picarta.ai/ | IA — localização |
| OSINT.SH Geolocate | https://osint.sh/images/ | Multi-busca |
| PlanetScope | https://www.planet.com/ | Imagens de satélite |
| Sentinel Hub | https://www.sentinel-hub.com/ | ESA — satélite gratuito |
| Immersal | https://immersal.com/ | Localização por AR |
| Loc8.ai | https://loc8.ai/ | Geoestimation IA |
| EarthKit | https://earthkit.ai/ | Multi-camada |
| GEOINT Search | https://geointsearch.com/ | Busca específica |
| StreetComplete | https://streetcomplete.app/ | Consulta OSM em campo |

### 7.3 Cronolocalização (Posição do Sol e Lua)

| Ferramenta | URL |
|---|---|
| SunCalc | https://www.suncalc.org/ |
| SunEarthTools | https://www.sunearthtools.com/ |
| FindMyShadow | https://findmyshadow.com/ |
| ShadowCalculator | http://shadowcalculator.eu/ |
| NOAA Solar Calculator | https://gml.noaa.gov/grad/solcalc/ |
| MoonCalc | https://www.mooncalc.org/ |
| In-The-Sky.org | https://in-the-sky.org/ |
| Stellarium Web | https://stellarium-web.org/ | Planetário online |
| Photographers' Ephemeris | https://photoephemeris.com/ | Posição celeste |

**Técnica de cronolocalização:**
1. Identifique sombras na imagem
2. Determine direção aproximada pelo contexto visual
3. Use o SunCalc para simular posição do sol em datas/horas diferentes
4. Compare com comprimento e direção das sombras na imagem
5. Refine até convergir em data/hora provável
6. Considere refração atmosférica se precisão alta for necessária

### 7.4 Câmeras Abertas e Vigilância

| Ferramenta | URL |
|---|---|
| Insecam | http://www.insecam.org/ |
| EarthCam | https://www.earthcam.com/ |
| WorldCam | https://worldcam.eu/ |
| OpenTopia | http://www.opentopia.com/ |
| Pictimo | https://www.pictimo.com/ |
| AirportWebcam | https://airportwebcams.net/ |
| Shodan (câmeras) | `product:"webcam"` no Shodan |
| Camarize | https://www.camarize.com/ | CCTV comercial |
| Look4.cam | https://look4.cam/ | Webcams públicas |

> ⚠️ **Alerta:** Muitas dessas câmeras estão expostas por falha de configuração. Apenas observe — nunca tente acessar câmeras internas de locais privados sem autorização judicial (invasão de dispositivo, art. 154-A CP).

### 7.5 Imagens de Satélite Históricas

| Ferramenta | URL |
|---|---|
| World Imagery Wayback | https://livingatlas.arcgis.com/ |
| Google Earth Engine | https://earthengine.google.com/ |
| Copernicus Open Access Hub | https://scihub.copernicus.eu/ |
| USGS EarthExplorer | https://earthexplorer.usgs.gov/ |
| NASA Worldview | https://worldview.earthdata.nasa.gov/ |
| Zoom Earth | https://zoom.earth/ |
| Sentinel Hub EO Browser | https://apps.sentinel-hub.com/eo-browser/ |
| Terraserver | https://terraserver.com/ | Alta resolução paga |
| Maxar Open Data | https://www.maxar.com/open-data | Eventos de crise |
| Airbus OneAtlas | https://www.intelligence-airbusds.com/ | Comercial |
| Descartes Labs Search | https://search.descarteslabs.com/ | Plataforma |
| Bing Maps Birds Eye | https://www.bing.com/maps | Vista oblíqua |
| HOT OSM (Humanitarian) | https://www.hotosm.org/ | Emergências |

### 7.6 Mapas e Análise Geoespacial

| Ferramenta | URL | Função |
|---|---|---|
| QGIS | https://www.qgis.org/ | SIG profissional open-source |
| Google My Maps | https://mymaps.google.com/ | Mapas personalizados |
| Felt | https://felt.com/ | Colaborativo online |
| Kepler.gl | https://kepler.gl/ | Visualização de dados geo |
| uMap | https://umap.openstreetmap.fr/ | Open-source |
| Palladio | https://hdlab.stanford.edu/palladio/ | Análise histórica |
| Mapbox Studio | https://www.mapbox.com/mapbox-studio | Customização |
| Leaflet.js | https://leafletjs.com/ | Biblioteca |
| Deck.gl | https://deck.gl/ | Viz de dados geo |
| CartoDB | https://carto.com/ | SaaS |
| MapServer | https://mapserver.org/ | Server GIS |
| PostGIS | https://postgis.net/ | Banco geoespacial |

### 7.7 Análise de IP e ERB (GSM)

**Estação Rádio Base (ERB):**
- Cada antena da operadora tem um identificador (Cell ID + LAC + MCC + MNC)
- A análise de CDR (Call Detail Record) revela localização aproximada
- Pedido via ofício à operadora com período específico

| Ferramenta | URL | Função |
|---|---|---|
| CellMapper | https://www.cellmapper.net/ | Mapa de antenas colaborativo |
| OpenCellID | https://opencellid.org/ | Base aberta de ERBs |
| Mozilla Location Service | https://location.services.mozilla.com/ | Descontinuado mas histórico |
| UnwiredLabs | https://unwiredlabs.com/ | API comercial |
| LocationAPI | https://www.locationapi.org/ | Multi-source |
| Google Geolocation API | https://developers.google.com/maps/documentation/geolocation | Resolver por WiFi/Cell |
| WiGLE | https://wigle.net/ | WiFi + Cell global |
| BTSearch | https://btsearch.pl/ | Foco em Polônia/EU |

**Referências técnicas:**
- Padrão 3GPP para CDR
- Lei 9.472/1997 (LGT) para acesso a dados de localização
- RFC sobre CGI (Cell Global Identity)

---

## 8. REDES SOCIAIS (SOCMINT)

### 8.1 Instagram

| Ferramenta | URL | Função |
|---|---|---|
| Instaloader | https://github.com/instaloader/instaloader | Download completo do perfil |
| OSINTgram | https://github.com/Datalux/Osintgram | Dados de perfil |
| Toutatis | https://github.com/megadose/toutatis | Dados avançados |
| IntelTechniques IG | https://inteltechniques.com/tools/Instagram.html | Ferramentas integradas |
| Picuki | https://www.picuki.com/ | Visualização sem conta |
| InstaNavigation | https://instanavigation.com/ | Espelho |
| Dumpoir | https://dumpoir.com/ | Espelho |
| StoriesIG | https://storiesig.info/ | Stories sem conta |
| CommentPicker | https://commentpicker.com/ | Extração de comentários |
| NotJustAnalytics | https://www.notjustanalytics.com/ | Análise de perfil |
| Mulkom (IG profile pic HD) | https://www.mulkom.com/ | Foto HD |
| InstaGramDirect | https://codeofaninja.com/tools/find-instagram-user-id/ | ID do usuário |
| ImgInn | https://imginn.com/ | Espelho |
| Pixwox | https://pixwox.com/ | Espelho |
| GramSpy | https://gramspy.com/ | Analytics |
| Inflact | https://inflact.com/ | Analytics + scraper |
| Hypeauditor | https://hypeauditor.com/ | Influencer intel |

**Técnicas Instagram:**
- ID do usuário: `instagram.com/USUARIO/?__a=1&__d=1` (mutável pela plataforma)
- Foto de perfil HD: buscar `profile_pic_url_hd` no JSON
- Dorks: `site:instagram.com "@username"`
- Verificar "followers" e "following" como pivô para rede social
- Tags em posts revelam padrões de localização e círculo social

### 8.2 Facebook

| Ferramenta | URL | Função |
|---|---|---|
| IntelTechniques FB | https://inteltechniques.com/tools/Facebook.html | Toolkit completa |
| IntelX FB | https://intelx.io/tools?tab=facebook | Ferramentas |
| WhoPostedWhat | https://whopostedwhat.com/ | Busca por data |
| OSINT Combine FB | https://www.osintcombine.com/facebook-search-tools | Busca avançada |
| Lookup-ID | https://lookup-id.com/ | ID de perfil |
| FindIDFB | https://findidfb.com/ | ID de perfil |
| ExportComments | https://exportcomments.com/ | Exporta comentários |
| Social-Searcher | https://www.social-searcher.com/ | Posts públicos |
| CyberChef | https://gchq.github.io/CyberChef/ | Converte UNIX timestamp |
| EpochConverter | https://www.epochconverter.com/ | Timestamp |
| ESUIT Chrome | Plugin Chrome | Extrai ID automaticamente |
| Instant Data Scraper | Plugin Chrome | Scraping de listas |
| StalkFace | https://stalkface.com/en/ | Fotos públicas |
| Graph.tips | (arquivo histórico) | Graph Search legacy |
| FB-Search | https://www.facebook.com/search/top/?q= | Busca nativa |
| FB Pages Dir | https://www.facebook.com/directory/pages/ | Páginas públicas |

**Técnicas Facebook:**
- ID no código-fonte: `userID`, `page_id`, `group_id`
- Data de criação: campo `creation_time` (formato UNIX)
- Marketplace: `facebook.com/marketplace/profile/ID`
- Técnica de página: adicionar e-mail como administrador
- Álbum de fotos: `facebook.com/USUARIO/photos`
- Check-ins históricos: `places_visited` (se público)

### 8.3 Twitter / X

| Ferramenta | URL | Função |
|---|---|---|
| TweetDeck (X Pro) | https://pro.twitter.com/ | Monitoramento |
| Twint | https://github.com/twintproject/twint | Scraping sem API (legacy) |
| Tinfoleak | https://github.com/vaguileradiaz/tinfoleak | Análise de metadados |
| Twitonomy | https://www.twitonomy.com/ | Analytics |
| Foller.me | https://foller.me/ | Report do perfil |
| AllMyTweets | https://www.allmytweets.net/ | Todos os tweets |
| TweetBeaver | https://tweetbeaver.com/ | Ferramentas variadas |
| Spoonbill | https://spoonbill.io/ | Monitora mudanças no perfil |
| TrendsMap | https://www.trendsmap.com/ | Trends por localização |
| Twiangulate | https://twiangulate.com/ | Análise de conexões |
| TweeterID | https://tweeterid.com/ | Username → ID |
| Followerwonk | https://followerwonk.com/ | Análise de seguidores |
| Nitter | https://nitter.net/ | Espelho sem rastreamento |
| IntelTechniques TW | https://inteltechniques.com/tools/Twitter.html | Toolkit |
| Social Bearing | https://socialbearing.com/ | Monitoramento |
| Tweepy (Python) | https://www.tweepy.org/ | API client |
| Hoaxy | https://hoaxy.osome.iu.edu/ | Disinfo spread |
| Botometer | https://botometer.osome.iu.edu/ | Bot detection |
| Twitter Archiver | https://archiver.digitalinspiration.com/ | Sheets + Twitter |
| Advanced Search X | https://twitter.com/search-advanced | Nativo |
| X (Grok) search | https://x.com/ | API oficial (paga agora) |

**Twitter Dorks avançados:**
```
from:usuario                      # Tweets do usuário
to:usuario                        # Tweets para o usuário
since:2020-01-01 until:2023-01-01 "termo"
geocode:LAT,LON,RAIOkm "termo"
filter:images                     # Só imagens
filter:videos                     # Só vídeos
min_retweets:100                  # Muito compartilhado
url:dominio.com                   # Links para domínio
-filter:replies                   # Excluir respostas
filter:links                      # Com links
lang:pt                           # Idioma português
filter:verified                   # Usuários verificados
```

### 8.4 TikTok

| Ferramenta | URL | Função |
|---|---|---|
| OSINT Combine TikTok | https://www.osintcombine.com/tiktok-quick-search | Busca rápida |
| UrleBird | https://urlebird.com/ | Visualização de perfis |
| SnapTik | https://snaptik.app/ | Download de vídeos |
| TikTok Hashtags | https://tiktokhashtags.com/ | Hashtags similares |
| InfluenceGrid | https://influencegrid.com/ | Busca de usuários |
| Search4Faces TikTok | https://search4faces.com/tt00/ | Busca facial |
| CommentPicker TikTok | https://commentpicker.com/tiktok-id.php | ID do usuário |
| ExportComments | https://exportcomments.com/ | Exporta comentários |
| TTDown | https://ttdown.org/ | Download de vídeos |
| TikTok Analytics | https://tiktokanalytics.io/ | Analytics |
| CountTik | https://counttik.com/ | Métricas de conta |
| TokAudit | https://tokaudit.io/ | Auditoria de perfil |
| SaveTik | https://ssstik.io/ | Download sem watermark |
| Pentaclay | https://pentaclay.com/tiktok-downloader | Multi-função |

### 8.5 LinkedIn

| Ferramenta | URL | Função |
|---|---|---|
| LinkedIn Sales Navigator | Pago | Busca avançada |
| IntelTechniques LinkedIn | https://inteltechniques.com/tools/LinkedIn.html | Ferramentas |
| theHarvester | https://github.com/laramies/theHarvester | E-mails de empresa |
| LinkedInt | https://github.com/vysec/LinkedInt | OSINT em LinkedIn |
| CrossLinked | https://github.com/m8sec/CrossLinked | Enumeração de funcionários |
| Dork | `site:linkedin.com "empresa" "cargo"` | Busca de funcionários |
| InspyLinked | https://github.com/leapsecurity/InSpy | Enumeração |
| Hunter.io Company | https://hunter.io/search/ | E-mails + cargo |
| Rocketreach | https://rocketreach.co/ | Enriquecimento |
| Lusha | https://www.lusha.com/ | Contatos B2B |
| Apollo.io | https://www.apollo.io/ | Base B2B extensa |
| Kaspr | https://www.kaspr.io/ | Extração contatos |
| Phantombuster | https://phantombuster.com/ | Automação LinkedIn |
| LeadLeaper | https://www.leadleaper.com/ | Extrator |
| SignalHire | https://www.signalhire.com/ | B2B |
| Whoisme (plataforma) | https://whoisme.com/ | LinkedIn scraping |

### 8.6 Telegram

| Bot / Ferramenta | Link | Função |
|---|---|---|
| CreationDateBot | https://t.me/creationdatebot | Data de criação da conta |
| RegDateBot | https://t.me/RegDateBot | Data de registro |
| UserinfoBot | https://t.me/userinfobot | ID pelo username |
| GetMyID Bot | https://t.me/getmyid_bot | Seu próprio ID |
| SangMata BOT | https://t.me/SangMata_BOT | Histórico de usernames |
| TgScanRobot | https://t.me/TgScanRobot | Grupos de um usuário |
| ChatSearchRobot | https://t.me/ChatSearchRobot | Grupos similares |
| TGStat | https://tgstat.ru/ | Ranking e análise de canais |
| Telemetr | https://telemetr.io/ | Análise de canais |
| TDirectory | https://tdirectory.me/ | Diretório de grupos |
| XTEA | https://xtea.io/ | Busca no Telegram |
| Telegram Analytics (TGStat) | https://tgstat.com/ | Global |
| Lyzem | https://lyzem.com/ | Busca em mensagens |
| Telepathy | https://github.com/proseltd/telepathy | OSINT CLI |
| Telegago (Google CSE) | https://cse.google.com/cse?cx=006368593537057042503:efxu7xprihg | Dork para grupos |
| TeleSearch | https://en.telesear.ch/ | Busca agregadora |
| TGdev | https://tgdev.io/ | Analytics de canais |
| Telesco.pe (legacy) | — | Histórico |

### 8.7 YouTube

| Ferramenta | URL | Função |
|---|---|---|
| Comment Picker | https://commentpicker.com/ | Extrai comentários |
| YouTube Metadata | https://mattw.io/youtube-metadata/ | Metadados de vídeo |
| YouTube GeoFind | https://youtube.github.io/geo-search-tool/ | Busca geolocalizada |
| Amnesty YT DataViewer | https://citizenevidence.amnestyusa.org/ | Verificação de vídeo |
| IntelTechniques YT | https://inteltechniques.com/tools/YouTube.html | Toolkit |
| Dork | `site:youtube.com "canal" "palavra"` | Busca indexada |
| YouTube DL / yt-dlp | https://github.com/yt-dlp/yt-dlp | Download |
| VidIQ | https://vidiq.com/ | Analytics |
| Social Blade | https://socialblade.com/ | Stats histórico |
| Channel Crawler | https://www.channelcrawler.com/ | Busca de canais |
| Filmot | https://filmot.com/ | Busca em legendas |
| YouChat (CC search) | https://ccsubs.com/ | Legendas |
| NoxInfluencer | https://www.noxinfluencer.com/ | Influencer intel |

### 8.8 Reddit

| Ferramenta | URL | Função |
|---|---|---|
| Pushshift | https://pushshift.io/ | Histórico de posts (limitado) |
| RedditSearch | https://redditsearch.io/ | Busca avançada |
| Camas Reddit | https://camas.unddit.com/ | Posts deletados |
| KarmaDecay | http://karmadecay.com/ | Busca reversa de imagem |
| SnoopSnoo | https://snoopsnoo.com/ | Análise de usuário |
| Mostly Harmless | https://kerrick.github.io/Mostly-Harmless/ | Histórico |
| Subreddit Stats | https://subredditstats.com/ | Estatísticas |
| Revddit | https://www.revddit.com/ | Posts removidos |
| Unddit / Removeddit | https://www.unddit.com/ | Content removido |
| RedditMetis | https://redditmetis.com/ | Análise de usuário |
| Reddit Investigator | https://www.redditinvestigator.com/ | Perfil completo |
| Pullpush | https://pullpush.io/ | Sucessor Pushshift |
| Old.reddit Search | https://old.reddit.com/search | Interface antiga |

### 8.9 Redes Alternativas / Emergentes 🆕

| Rede | Ferramentas / Técnicas |
|---|---|
| **Bluesky** | API pública (bsky.app), bskydata.com, clearsky.app, firesky.tv (feed live) |
| **Mastodon** | Federação — buscar em instâncias, Fedi.tips, FediSearch |
| **Threads** | Pouca API — via web; ligado ao Instagram, então pivô via IG |
| **Truth Social** | Truthsocial-search, arquivos via Wayback |
| **Parler** | Arquivos via ADL / Kessler (dump de 2021 é famoso) |
| **Gab** | Busca direta gab.com; arquivos via investigadores |
| **Rumble** | Rumble.com pesquisa, Social Blade |
| **Telegram-like (TamTam, Signal)** | Signal: sem OSINT significativo por design |
| **VKontakte** | VK.com busca, Search4Faces, 220vk.com |
| **Odnoklassniki** | OK.ru + Yandex |
| **WeChat** | Sogou WeChat search, Weixin.qq.com |
| **Weibo** | Weibo.com busca, TheDataPack |
| **Line** | Line Today, limitado |
| **Kick** | Kick.com/USER, social Blade |
| **Discord** | Disboard (diretório), Discord.id, Top.gg |
| **Nostr** | nostr.directory, primal.net search |
| **Matrix** | Matrix.org search, Element directory |

### 8.10 Snapchat

| Ferramenta | URL | Função |
|---|---|---|
| Snapchat Map | https://map.snapchat.com/ | Snaps públicos |
| Ghost Codes | https://ghostcod.es/ | Diretório de Snapcodes |
| ConvoZ | https://convoz.com/ | Agregador |
| SnapCodes (arquivo) | via Yandex reverse | Snapcode identificação |

### 8.11 Ferramentas Multi-Plataforma

| Ferramenta | URL | Cobertura |
|---|---|---|
| Social Links (Maltego) | https://sociallinks.io/ | Multi-rede profissional |
| Babel X | https://www.babelstreet.com/ | Multi-linguagem |
| Fivecast | https://www.fivecast.com/ | Profissional |
| Skopenow | https://www.skopenow.com/ | Automated |
| Cobwebs / PenLink Tangles | https://cobwebs.com/ | WEBINT |
| ShadowDragon | https://shadowdragon.io/ | SocialNet |
| Liferaft | https://liferaftinc.com/ | SOCMINT profissional |
| Blackdot Videris | https://www.blackdotsolutions.com/ | Investigação |
| Flashpoint | https://flashpoint.io/ | Dark + surface |

---


## 9. CRIPTOATIVOS E INVESTIGAÇÃO FINANCEIRA

### 9.1 Exploradores de Blockchain

| Blockchain | Ferramenta | URL |
|---|---|---|
| Bitcoin | Blockchain.com | https://www.blockchain.com/ |
| Bitcoin | WalletExplorer | https://walletexplorer.com/ |
| Bitcoin | Blockchair | https://blockchair.com/ |
| Bitcoin | Mempool.space | https://mempool.space/ |
| Bitcoin | BlockStream | https://blockstream.info/ |
| Bitcoin | OXT | https://oxt.me/ |
| Ethereum | Etherscan | https://etherscan.io/ |
| Ethereum | Blockscan | https://blockscan.com/ |
| Ethereum | Beaconchain | https://beaconcha.in/ |
| Ethereum | Phalcon (Blocksec) | https://phalcon.blocksec.com/ |
| Tron | TronScan | https://tronscan.org/ |
| BSC | BscScan | https://bscscan.com/ |
| Solana | Solscan | https://solscan.io/ |
| Solana | SolanaFM | https://solana.fm/ |
| Monero | XMRchain | https://xmrchain.net/ |
| Multi-chain | 3xpl | https://3xpl.com/ |
| Multi-chain | BlockSherlock | https://www.blocksherlock.com/ |
| Multi-chain | Bitquery | https://explorer.bitquery.io/ |
| Multi-chain | CoinMarketCap | https://coinmarketcap.com/ |
| Multi-chain | Dune Analytics | https://dune.com/ | SQL no blockchain |
| Multi-chain | Etherscan Clones | PolyScan, FtmScan, ArbiScan, OpScan, BaseScan, etc. |
| Ripple (XRP) | XRP Scan | https://xrpscan.com/ |
| Cardano | Cardanoscan | https://cardanoscan.io/ |
| Polkadot | Subscan | https://subscan.io/ |
| Cosmos | Mintscan | https://www.mintscan.io/ |
| Avalanche | SnowTrace | https://snowtrace.io/ |
| Near | NEAR Explorer | https://explorer.near.org/ |
| Stellar | StellarExpert | https://stellar.expert/ |
| Algorand | AlgoExplorer | https://algoexplorer.io/ |
| Tezos | TzKT | https://tzkt.io/ |
| Litecoin | Litecoinblockexplorer | https://litecoinblockexplorer.net/ |
| Bitcoin Cash | BCH Explorer | https://blockchair.com/bitcoin-cash |
| Zcash | ZcashBlockExplorer | https://zcashblockexplorer.com/ |
| Dogecoin | DogeChain | https://dogechain.info/ |

### 9.2 Rastreamento e Análise

| Ferramenta | URL | Tipo |
|---|---|---|
| Chainalysis Reactor | https://www.chainalysis.com/ | Comercial — líder de mercado |
| CipherTrace | https://ciphertrace.com/ | Comercial |
| TRM Labs | https://www.trmlabs.com/ | Comercial |
| Elliptic | https://www.elliptic.co/ | Comercial |
| Arkham Intelligence | https://platform.arkhamintelligence.com/ | Semi-gratuito |
| MetaSleuth | https://metasleuth.io/ | Gratuito — multi-chain |
| Intel Arkm | https://intel.arkm.com/ | Pesquisa de carteiras |
| Crystal Blockchain | https://crystalblockchain.com/ | Comercial |
| Breadcrumbs | https://www.breadcrumbs.app/ | Semi-gratuito |
| OXT Research | https://oxt.me/ | Bitcoin |
| GraphSense | https://www.graphsense.info/ | Acadêmico open-source |
| BitQuery IDE | https://ide.bitquery.io/ | GraphQL queries |
| Nansen | https://www.nansen.ai/ | Wallet labeling |
| DeBank | https://debank.com/ | Portfolio view |
| Zerion | https://zerion.io/ | DeFi tracker |
| Zapper | https://zapper.xyz/ | DeFi dashboard |
| Misttrack | https://misttrack.io/ | SlowMist |
| Bubblemaps | https://bubblemaps.io/ | Holders visual |
| Wallet Labels (Dune) | https://dune.com/ | Queries customizadas |
| EigenPhi | https://eigenphi.io/ | MEV/arbitrage |
| Parsec | https://parsec.finance/ | Onchain analytics |
| DefiLlama | https://defillama.com/ | TVL data |
| Token Sniffer | https://tokensniffer.com/ | Rug detection |
| DeBank Profile | https://debank.com/profile/ | Perfil carteira |
| Etherscan Name Tags | Etherscan + API | Labels |

### 9.3 Reputação de Carteiras

| Ferramenta | URL |
|---|---|
| BitcoinWhoIsWho | https://www.bitcoinwhoswho.com/ |
| ChainAbuse | https://www.chainabuse.com/ |
| ScamSearch | https://scamsearch.io/ |
| BadBitcoin | https://badbitcoin.org/ |
| CryptoScamDB | https://cryptoscamdb.org/ |
| WalletExplorer Tags | https://walletexplorer.com/ |
| Scam Alert (Binance) | https://scam.binance.com/ |
| GoPlus Security | https://gopluslabs.io/ |
| DeBankDirectSearch | https://debank.com/ |
| SlowMist MistTrack | https://misttrack.io/ |
| OFAC SDN List | https://sanctionssearch.ofac.treas.gov/ | Sanções crypto |
| TRM SanctionsScreen | https://www.trmlabs.com/ | Comercial |
| Cryptoscamdb (github) | https://github.com/CryptoScamDB/api | Open data |
| USDT Blacklist | Tether freeze list | Via Etherscan |
| USDC Blacklist | Circle freeze list | Via Etherscan |

### 9.4 ATMs de Criptomoedas

| Ferramenta | URL | Função |
|---|---|---|
| CoinATMRadar | https://coinatmradar.com/ | Mapa global de ATMs |
| CoinFlip | https://coinflip.tech/ | EUA — ATMs com KYC |
| Bitcoin Depot | https://bitcoindepot.com/ | EUA |
| Bitcoin ATM Map | https://coinatmradar.com/ | Agregador |
| Athena Bitcoin | https://athenabitcoin.com/ | América Latina |

### 9.5 Exchanges e KYC

**Exchanges centralizadas com obrigação de KYC (sujeitas a ofício judicial):**

**Brasileiras/com operação no Brasil:**
- Binance (via Binance Brasil S.A.)
- Mercado Bitcoin
- Foxbit
- NovaDAX
- BitcoinTrade
- BitPreço
- Bitso (opera no BR)
- Brasil Bitcoin
- BitcoinMax
- Ripio (entrou na LATAM)

**Internacionais:**
- Coinbase
- Kraken
- Bitstamp
- Gemini
- Bitfinex
- KuCoin
- OKX
- Bybit
- Bitget
- HTX (ex-Huobi)
- Crypto.com
- MEXC

**Ofícios e cooperação:**
- Receita Federal — IN RFB 1.888/2019 (obrigação de reporte pelas exchanges)
- COAF — comunicações de operações suspeitas
- Via MLAT para exchanges sediadas fora do Brasil
- Binance e Coinbase têm **portal LEA** (Law Enforcement Request Portal)
- Considerar compartilhamento via Interpol e FBI para atos em outras jurisdições

### 9.6 Mixers e Técnicas de Ofuscação

| Tipo | Exemplos | Impacto Investigativo |
|---|---|---|
| Mixers/Tumblers | Tornado Cash (OFAC-sancionado), Sinbad (tomado down), Wasabi, Samourai CoinJoin | Alta ofuscação |
| Chain Hopping | Uso de múltiplas chains | Dificulta rastreamento |
| Monero (XMR) | Privacy coin | Rastreamento quase impossível |
| Zcash shielded | Privacy coin | Depende do uso |
| Lightning Network | Pagamentos off-chain | Sem registro na blockchain |
| Liquid Network | Sidechain | Semi-privado |
| P2P Sem KYC | LocalMonero (tomado down), Bisq, LocalCoinSwap | Dificulta identificação |
| Bridges cross-chain | Wormhole, LayerZero, Axelar | Salto entre chains |
| Atomic Swaps | Sem intermediário | Difícil rastrear |
| Stealth addresses | Vários (Monero nativo, Umbra ETH) | Ocultam destinatário |

**Técnicas de desmistura (demixing):**
- Análise de timing e montantes (dust heuristics)
- Common-input-ownership heuristic
- Change address detection
- Taint analysis
- ML para clusterização de wallets
- TRM, Chainalysis e Elliptic têm capacidade parcial de rastrear Wasabi/Samourai
- Monero: rastreamento viável em casos de vulnerabilidades antigas (pré-RingCT/Bulletproofs) ou erros do usuário

### 9.7 DeFi e NFTs

| Ferramenta | URL | Função |
|---|---|---|
| OpenSea | https://opensea.io/ | NFT marketplace |
| Blur | https://blur.io/ | NFT marketplace |
| LooksRare | https://looksrare.org/ | NFT |
| Magic Eden | https://magiceden.io/ | NFT multichain |
| Rarible | https://rarible.com/ | NFT |
| NFTGo | https://nftgo.io/ | Analytics |
| Uniswap Info | https://info.uniswap.org/ | DEX |
| DEX Screener | https://dexscreener.com/ | DEX multi |
| GeckoTerminal | https://www.geckoterminal.com/ | Trading view |
| DefiLlama | https://defillama.com/ | TVL |
| Token Terminal | https://tokenterminal.com/ | P&L DeFi |

### 9.8 Investigação Financeira Tradicional

| Fonte | URL | Uso |
|---|---|---|
| BACEN SISBACEN CCS | Via ofício | Contas bancárias |
| COAF | https://www.gov.br/coaf | Relatórios de operações suspeitas |
| CVM | https://www.gov.br/cvm | Investimentos |
| SUSEP | https://www.gov.br/susep | Seguros |
| PREVIC | https://www.gov.br/previc | Previdência complementar |
| Receita Federal (DIRPF, DITR, DOI, DIMOB, DECRED) | Via ofício | Declarações |
| SIMBA (MPF) | Uso institucional | Análise bancária |
| FINCEN 314(a) (EUA) | Via MLAT | Financial intel |
| OpenSanctions | https://www.opensanctions.org/ | Sancionados globais |
| LittleSis | https://littlesis.org/ | Poder + negócios |
| Orbis (Bureau van Dijk) | Comercial | Ownership global |

### 9.9 Pirâmides Financeiras e Esquemas

| Técnica | Aplicação |
|---|---|
| Análise de MLM | Mapa de recrutamento + comissões |
| Token scam detection | Token Sniffer, GoPlus |
| Rug pull analysis | Análise de liquidez e contract audit |
| Ponzi on-chain | Padrões de depósito/saque circular |
| Fake investment platforms | Verificar registro CVM, domain WHOIS |

---

## 10. METADADOS (EXIF E DOCUMENTOS)

### 10.1 Metadados em Documentos Office/PDF

| Ferramenta | URL / Comando | Função |
|---|---|---|
| ExifTool | `exiftool documento.pdf` | Autor, software, data |
| FOCA | https://github.com/ElevenPaths/FOCA | Automação para sites |
| Metagoofil | `metagoofil -d dominio.com -t pdf` | Extração em massa |
| PDF-Parser | `pdf-parser documento.pdf` | Análise estrutural |
| PDF Examiner | https://www.pdf-examiner.com/ | Análise online |
| OfficeMalScanner | Windows | Análise de Office |
| olevba (oletools) | https://github.com/decalage2/oletools | Macros em Office |
| oleid | oletools | Identificação |
| oledump | DidierStevens | Dump de streams OLE |
| peepdf | https://github.com/jesparza/peepdf | Análise PDF |
| PyMuPDF (fitz) | Python | Extração programática |
| LibreOffice Reviewer | Manual | Comentários e histórico |
| PDF Stream Dumper | Ferramenta Windows | Análise profunda |
| Didier Stevens Suite | https://blog.didierstevens.com/ | Vários utilitários |

**Metadados extraíveis de documentos:**
- Nome do autor e coautor
- Organização/empresa
- Software utilizado (versão)
- Data de criação e última modificação
- Número de revisões
- Comentários e anotações ocultas
- Impressoras utilizadas
- Nomes de usuário internos
- Caminhos de arquivo (path) no sistema de origem
- Templates utilizados
- GUIDs de documento
- E-mails em hiperlinks ocultos

### 10.2 Metadados em Imagens (EXIF Completo)

**Campos mais relevantes para investigação:**

| Campo EXIF | Valor de Inteligência |
|---|---|
| `GPS.GPSLatitude` / `GPS.GPSLongitude` | Localização exata |
| `DateTimeOriginal` | Hora real da captura |
| `Make` / `Model` | Modelo do dispositivo |
| `Software` | App de câmera ou edição |
| `SerialNumber` | Número de série do dispositivo |
| `LensModel` | Identifica câmera profissional |
| `UserComment` | Comentários embutidos |
| `ThumbnailImage` | Miniatura original (antes de edição) |
| `Artist` / `Copyright` | Autoria declarada |
| `GPSAltitude` | Altitude (útil para indoor vs outdoor) |
| `GPSImgDirection` | Direção em que a foto foi tirada |
| `HostComputer` | Nome do equipamento |
| `DocumentName` | Nome do documento original |
| `Keywords` | Tags atribuídas |
| `OwnerName` | Proprietário declarado |
| `InternalSerialNumber` | ID profundo (Canon, Nikon) |
| `FirmwareVersion` | Versão do firmware |
| `ShutterCount` | Contagem de disparos (DSLR) |

### 10.3 Metadados em Vídeo

| Campo | Função |
|---|---|
| `creation_time` | Data/hora de criação |
| `encoder` | Software usado |
| `location` (QuickTime) | GPS embutido em iPhone |
| `make` / `model` | Dispositivo |
| `duration` | Tempo de vídeo |
| `frame_rate` | Taxa de quadros |
| `codec` | Codec usado |
| `title` / `comment` | Metadados descritivos |

**Ferramentas:**
- `exiftool video.mp4`
- `ffprobe video.mp4 -show_format -show_streams`
- `mediainfo video.mp4`

### 10.4 Metadados em Áudio

| Campo | Função |
|---|---|
| `artist` / `album` / `title` | ID3 tags |
| `encoder` | Software de captura |
| `date` | Data de criação |
| `GPS` (em alguns apps) | Localização |
| `channel_layout` | Mono/estéreo/5.1 |

### 10.5 Remoção (Anti-Forense) e Detecção de Remoção

- Serviços que removem EXIF: Imgur, Facebook, Twitter (na maioria dos casos)
- Serviços que MANTÉM: Flickr, Google Drive (compartilhado), WeTransfer (parcial)
- Técnica: se um arquivo "puro" teve EXIF removido, isso pode ser um indicador de consciência anti-forense
- Ferramentas de limpeza: MAT2, ExifTool com `-all=`

---


## 11. DARK WEB E DEEP WEB

### 11.1 Conceitos e Diferenciação

| Camada | Definição | Acesso |
|---|---|---|
| **Surface Web** | Conteúdo indexado por buscadores | Qualquer navegador |
| **Deep Web** | Conteúdo não indexado (logins, sistemas) | Autenticação necessária |
| **Dark Web** | Redes overlay (Tor, I2P, Freenet) | Software específico |

### 11.2 Acesso Seguro à Dark Web

> ⚠️ **OPSEC CRÍTICO:** Nunca acesse a dark web sem configuração adequada de OPSEC. Veja seção 19.

| Ferramenta | URL | Função |
|---|---|---|
| Tor Browser | https://www.torproject.org/ | Acesso à rede Tor |
| Tails OS | https://tails.boum.org/ | SO amnésico para anonimato |
| Whonix | https://www.whonix.org/ | VM isolada com Tor |
| I2P | https://geti2p.net/ | Rede alternativa |
| Freenet / Hyphanet | https://hyphanet.org/ | Rede descentralizada |
| ZeroNet | https://zeronet.io/ | P2P web |
| Lokinet | https://lokinet.org/ | Oxen-based |
| Yggdrasil | https://yggdrasil-network.github.io/ | Mesh IPv6 |

### 11.3 Buscadores da Dark Web

| Buscador | URL Onion | Observação |
|---|---|---|
| Ahmia | https://ahmia.fi/ | Também na surface |
| Torch | (onion) | Antigo e confiável |
| DuckDuckGo Onion | (onion) | Privacidade |
| Not Evil | (onion) | Indexação |
| Haystak | (onion) | Foco em conteúdo |
| OnionLand Search | http://onionlandsearchengine.com/ | Agregador |
| Phobos | http://phoboshryxpxdh4tuieoqpbsgxkjqomoq6qroeqkhjrbdgxqyszh6wqd.onion/ | Cauteloso |
| DarkSearch (legacy) | — | Histórico |
| Kilos | (onion - cauteloso, ligado a mercados) | Não usar sem OPSEC |

> ⚠️ URLs onion são voláteis. Prefira começar pelo Ahmia e Tor Project para recursos atualizados.

### 11.4 Monitoramento e Inteligência na Dark Web

| Ferramenta | URL | Tipo |
|---|---|---|
| IntelligenceX | https://intelx.io/ | Paga — dark + surface |
| DarkTracer | https://darktracer.io/ | Threat intel |
| Flare | https://flare.io/ | Monitoramento contínuo |
| Recorded Future | https://www.recordedfuture.com/ | Comercial |
| Digital Shadows (ReliaQuest) | https://www.reliaquest.com/ | Comercial |
| SOCRadar | https://socradar.io/ | Semi-gratuito |
| DeHashed | https://www.dehashed.com/ | Vazamentos |
| SnusBase | https://snusbase.com/ | Vazamentos |
| Flashpoint | https://flashpoint.io/ | Líder em dark intel |
| Sixgill (Cybersixgill) | https://cybersixgill.com/ | Automação |
| KELA | https://www.kelacyber.com/ | Cibercrime |
| IntSights (Rapid7) | https://www.rapid7.com/ | Threat intel |
| ZeroFox | https://www.zerofox.com/ | External threat |
| CTM360 | https://www.ctm360.com/ | Monitoramento |
| DarkOwl | https://www.darkowl.com/ | Ampla coleção |
| Prodaft | https://www.prodaft.com/ | Criminal intel |
| Group-IB | https://www.group-ib.com/ | CERT + intel |

### 11.5 Fóruns e Marketplaces de Interesse Investigativo

> ⚠️ **AVISO:** O acesso a fóruns de crime é permitido apenas em contexto de investigação legal, com autorização judicial (ou enquadramento em infiltração policial virtual pela Lei 12.850/2013, art. 10-A, e Lei 13.441/2017 para crimes contra criança/adolescente), procedimentos documentados de cadeia de custódia digital e OPSEC rigoroso.

**Tipos de ambientes monitorados:**
- Fóruns de venda de dados (fullz, CC, credenciais) — ex.: XSS, Exploit.in, BreachForums (sucessores)
- Marketplaces de drogas e armas — ex.: sucessores AlphaBay, ASAP, Incognito, Abacus
- Fóruns de hacking e malware — ex.: Nulled, Cracked, Hack Forums (surface + dark)
- Canais de CSAM — **notificação obrigatória às autoridades e NCMEC** via SaferNet (BR)
- Grupos de ransomware e extorsão — Ranzy, LockBit leaks, BlackCat/ALPHV, Clop
- Fraude SIM swap — fóruns em Telegram/Discord

**Frameworks úteis para investigação em fóruns:**
- TOAR (Tor-Onion Asset Rating) — classificação de importância
- MITRE ATT&CK + Diamond Model — caracterizar atores
- ADMT (Actor-Driven Monitoring Triage)

### 11.6 Investigação de Paste Sites

| Ferramenta | URL |
|---|---|
| Pastebin | https://pastebin.com/ |
| PasteBin.pl | https://pastebin.pl/ |
| GitHub Gists | https://gist.github.com/ |
| Riseup Pad | https://pad.riseup.net/ |
| Ghostbin | https://ghostbin.com/ |
| Dork | `site:pastebin.com "dado_alvo"` |
| Psbdmp | https://psbdmp.ws/ |
| Paste.ee | https://paste.ee/ |
| Rentry | https://rentry.co/ |
| Dpaste | https://dpaste.com/ |
| Hastebin | https://www.toptal.com/developers/hastebin |
| ControlC | https://controlc.com/ |
| PrivateBin (self-hosted instances) | Vários | Criptografado |
| 0bin | https://0bin.net/ | Client-side crypt |
| Just Paste It | https://justpaste.it/ | |
| Pastelink | https://pastelink.net/ | |

### 11.7 Buscadores Especializados em Vazamentos

| Ferramenta | URL | Tipo |
|---|---|---|
| IntelX | https://intelx.io/ | Vazamentos + dark |
| Leaked Source (sucessores) | (variados) | Monitorar via intel |
| Leak-Lookup | https://leak-lookup.com/ | Paga |
| WeLeakInfo (sucessores) | (variados) | Monitorar |
| Hudson Rock | https://www.hudsonrock.com/ | Infostealer intel |
| BreachDirectory | https://breachdirectory.org/ | Gratuita |
| SpyCloud | https://spycloud.com/ | Comercial |

### 11.8 Infostealer Logs — ecosystem

Infostealers (RedLine, Raccoon, Vidar, Lumma, StealC, Meduza, etc.) geram logs vendidos/compartilhados em fóruns. Para pesquisa investigativa legítima:

- **Hudson Rock** — fornece consulta de logs para LEA e empresas
- **SpyCloud** — exposição corporativa
- **Flare** — monitoramento
- **KELA** — cenário russo de stealer logs

> ⚠️ **Não baixe dumps brutos de infostealer para "análise".** Isso pode caracterizar receptação de dados. Trabalhe com fornecedores legítimos e com acordos formais.

---

## 12. FAVICONS COMO IDENTIFICADORES

### 12.1 Conceito

O hash MurmurHash3 do arquivo `favicon.ico` de um site pode ser usado como impressão digital para encontrar outros sites com a mesma infraestrutura ou pertencentes ao mesmo operador. Útil especialmente para identificar painéis de phishing idênticos em domínios diferentes, fazendas de sites de fraude e infraestrutura compartilhada de grupos criminosos.

### 12.2 Processo de Investigação

**Passo 1 — Obter o favicon:**
```
https://www.google.com/s2/favicons?domain=alvo.com
https://icon.horse/icon/alvo.com
https://alvo.com/favicon.ico
```

**Passo 2 — Calcular o hash (Python):**
```python
import mmh3, base64, requests

resp = requests.get("https://alvo.com/favicon.ico")
favicon_b64 = base64.encodebytes(resp.content)
hash_value = mmh3.hash(favicon_b64)
print(hash_value)
```

**Passo 3 — Buscar no Shodan:**
```
http.favicon.hash:HASH_CALCULADO
```

**Passo 4 — Buscar no Censys:**
```
services.http.response.favicons.md5_hash:HASH
```

### 12.3 Ferramentas

| Ferramenta | URL / Comando |
|---|---|
| FaviHunter | https://github.com/eremit4/favihunter |
| Shodan | `http.favicon.hash:HASH` |
| Censys | `services.http.response.favicons.md5_hash:HASH` |
| FavFreak | https://github.com/devanshbatham/FavFreak |
| FaviconFinder | https://github.com/will-hart/FaviconFinder |
| Hunter.how Favicon | https://hunter.how/ | Query `web.favicon.data` |
| FOFA Favicon | `icon_hash="HASH"` | Alternativa chinesa |
| ZoomEye Favicon | `iconhash:"HASH"` | |
| Netlas Favicon | `favicon.hash_murmur:HASH` | |

### 12.4 Dorks úteis

```
# Encontrar painéis C2 com favicon padrão do Cobalt Strike
http.favicon.hash:989289239 (Shodan)

# Identificar phishing kits com favicon idêntico
http.favicon.hash:HASH_DO_FAVICON_LEGITIMO -ssl.cert.subject.cn:*.dominio-real.com
```

---

## 13. VEÍCULOS, PLACAS E TRANSPORTE

### 13.1 Reconhecimento de Placas (ALPR)

| Ferramenta | URL | Função |
|---|---|---|
| Plate Recognizer | https://platerecognizer.com/ | OCR de placas |
| OpenALPR | https://www.openalpr.com/ | Open-source ALPR |
| CarNet.ai | https://carnet.ai/ | Reconhecimento de veículo |
| PlateRecognizer API | https://platerecognizer.com/ | API REST |
| EyedentityX | https://eyedentifyX.ai/ | Reconhecimento avançado |
| Sighthound | https://www.sighthound.com/ | Plataforma vídeo |
| Rekor Systems | https://rekorsystems.com/ | Enterprise |
| ANPR Open-source (Python) | https://github.com/openalpr/openalpr | Biblioteca |

### 13.2 Consulta de Veículos (Brasil)

| Ferramenta | Fonte | Observação |
|---|---|---|
| Detran (por estado) | Site oficial | Consulta pública limitada |
| SENATRAN | Via ofício | Dados completos |
| Consultas via painéis legítimos | Vide seção 2.1.7 | Com CNPJ registrado |
| Sinesp Cidadão | App oficial | Restrições e roubo |
| Placa FIPE | https://placafipe.com/ | Dados FIPE + placa |
| Consulta Placa (Detran SP) | https://www.detran.sp.gov.br/ | Paulista |
| Tabela FIPE | https://veiculos.fipe.org.br/ | Valores oficiais |
| Renavam via Detran | Site estadual | Dados básicos |
| ConsultaPlaca.com | https://consultaplaca.com/ | Restrito |
| Histórico de Proprietário (via ofício) | Detran estadual | Cadeia de posse |
| CRLV Digital | App CDT | Carteira digital |
| MUSA (Multas) | Via Detran | Infrações |

**Via ofício (Polícia Civil/Judiciária):**
- SENATRAN RENAVAM completo
- SINIESP infraestrutura — consultas unificadas (nacional)
- Infoseg — base integrada
- STF/STJ para restrições judiciais

### 13.3 Rastreamento de Aeronaves

| Ferramenta | URL |
|---|---|
| FlightAware | https://flightaware.com/ |
| FlightRadar24 | https://www.flightradar24.com/ |
| ADS-B Exchange | https://www.adsbexchange.com/ |
| PlaneFinder | https://planefinder.net/ |
| OpenSky Network | https://opensky-network.org/ |
| Radarbox | https://www.radarbox.com/ |
| Flightera | https://www.flightera.net/ |
| AirNav | https://www.airnav.com/ |
| JetPhotos | https://www.jetphotos.com/ | Fotos por matrícula |
| Planespotters | https://www.planespotters.net/ | Histórico de matrículas |
| AeroTransport Data Bank | https://www.aerotransport.org/ | Por aeronave |
| Airframes.org | https://airframes.org/ | Matrículas detalhadas |
| ANAC Aeronaves (Brasil) | https://sistemas.anac.gov.br/ | RAB oficial |
| Flightaware Firehose | API paga | Dados completos |

### 13.4 Rastreamento de Navios e Maritime

| Ferramenta | URL |
|---|---|
| VesselFinder | https://www.vesselfinder.com/ |
| MarineTraffic | https://www.marinetraffic.com/ |
| ShipFinder | https://www.shipfinder.com/ |
| MyShipTracking | https://www.myshiptracking.com/ |
| FleetMon | https://www.fleetmon.com/ |
| Cruisemapper | https://www.cruisemapper.com/ | Cruzeiros |
| Equasis | https://www.equasis.org/ | IMO info |
| Vessel History (MarineTraffic API) | Paga | Track history |
| Antigo Lloyd's Register | Via parceiros | Classificação |
| OpenSea Map | https://www.openseamap.org/ | OSM náutico |
| Global Fishing Watch | https://globalfishingwatch.org/ | Pesca |
| ANTAQ (Brasil) | https://www.gov.br/antaq/ | Navegação brasileira |
| NOAA PORTS | Sistemas portuários EUA | |

### 13.5 Trens e Transporte Terrestre

| Ferramenta | URL | Função |
|---|---|---|
| RailCam.uk | https://www.railcam.uk/ | Câmeras ferroviárias |
| ATLAS Rail | Várias | Plataforma ferroviária |
| Transport for London | https://tfl.gov.uk/ | Infos em tempo real |
| Moovit | https://moovitapp.com/ | Transporte público global |

---

## 14. DOCUMENTOS, REGISTROS E VAZAMENTOS

### 14.1 Registros Públicos (Brasil)

| Fonte | URL | Dados |
|---|---|---|
| Portal da Transparência | https://www.portaltransparencia.gov.br/ | Servidores, salários |
| Diário Oficial da União | https://www.in.gov.br/ | Atos oficiais |
| Tribunal de Contas | https://portal.tcu.gov.br/ | Contratos |
| CNJ | https://www.cnj.jus.br/ | Processos judiciais |
| Jusbrasil | https://www.jusbrasil.com.br/ | Processos e empresas |
| Brasil.io | https://brasil.io/ | Dados governamentais abertos |
| Receita Federal | https://www.gov.br/receitafederal/ | CPF/CNPJ |
| IBGE | https://www.ibge.gov.br/ | Dados demográficos |
| Governo Federal Dados | https://dados.gov.br/ | Datasets abertos |
| Diários Oficiais Estaduais | Site de cada estado | Atos estaduais |
| Diários Oficiais Municipais | Varia | Atos municipais |
| TSE Repositório | https://dadosabertos.tse.jus.br/ | Dados eleitorais |
| INEP | https://www.gov.br/inep/ | Educação |
| DataSUS | https://datasus.saude.gov.br/ | Saúde pública |
| MapBiomas | https://mapbiomas.org/ | Uso do solo |
| FiscalLista | — | Agentes públicos |
| Portal do Software Público | https://www.gov.br/governodigital/ | Softwares |
| LAI — Acesso à Informação | https://www.gov.br/acessoainformacao/ | Pedidos formais |

### 14.2 Registros de Propriedade

| Fonte | Função |
|---|---|
| Cartório de Registro de Imóveis (por estado) | Matrícula de imóveis |
| SENARC | Beneficiários sociais |
| Detran (estadual) | Veículos |
| Receita Federal | Declarações e bens (via ofício) |
| INPI | Marcas e patentes |
| Receita Federal - DIMOB | Imóveis (declaração) |
| Cartórios ORETs | Atos e protestos |
| IRIB - Indicador Nacional | https://www.irib.org.br/ | Registro imobiliário |
| Central de Registro de Imóveis | https://www.registradores.org.br/ | Unificado |
| Serviço Registral Eletrônico (SREI) | Por estado | Digital |

### 14.3 Busca de Documentos Vazados / Expostos

| Ferramenta | URL |
|---|---|
| Google Drive Search | `site:drive.google.com "dado_alvo"` |
| Dork Documentos | `"dado_alvo" filetype:pdf site:gov.br` |
| Scribd | https://www.scribd.com/ |
| Academia.edu | https://www.academia.edu/ |
| DocumentCloud | https://www.documentcloud.org/ |
| Court Listener | https://www.courtlistener.com/ |
| PACER (EUA) | https://pacer.gov/ |
| ResearchGate | https://www.researchgate.net/ |
| SSRN | https://www.ssrn.com/ |
| Calaméo | https://www.calameo.com/ | Revistas digitais |
| Issuu | https://issuu.com/ | Publicações |
| Slideshare | https://www.slideshare.net/ | Apresentações |
| Speaker Deck | https://speakerdeck.com/ | Slides dev |
| Archive.org Documents | https://archive.org/details/texts | Livros/docs |
| OffshoreLeaks (ICIJ) | https://offshoreleaks.icij.org/ | Empresas offshore |
| Distributed Denial of Secrets (DDoSecrets) | https://ddosecrets.com/ | Base de vazamentos (uso ético!) |
| Aleph (OCCRP) | https://aleph.occrp.org/ | Investigativo |

### 14.4 Google Dorks para Documentos Sensíveis

```
filetype:xls "confidencial"
filetype:doc "lista de funcionários"
filetype:pdf "nome_empresa" "interno"
intext:"Não divulgar" filetype:pdf
intitle:"index of" "passwords.txt"
site:empresa.com filetype:xls
inurl:backup filetype:sql
filetype:env DB_PASSWORD
filetype:ini inurl:"database"
filetype:log inurl:"/www/"
filetype:sql "INSERT INTO users"
intitle:"index.of" "parent directory" sensitive
inurl:"/phpinfo.php" OR inurl:"/.env" OR inurl:"/config.yml"
filetype:conf inurl:nginx
filetype:txt "RSA PRIVATE KEY"
"BEGIN CERTIFICATE" filetype:pem
```

### 14.5 OSINT Corporativo e Investigativo

| Fonte | URL | Uso |
|---|---|---|
| OpenCorporates | https://opencorporates.com/ | Empresas globais |
| Aleph (OCCRP) | https://aleph.occrp.org/ | Base investigativa |
| OpenSanctions | https://www.opensanctions.org/ | Sanções |
| Sayari | https://sayari.com/ | Risk + networks |
| Orbis (BvD) | Comercial | Ownership profundo |
| Dun & Bradstreet | https://www.dnb.com/ | Crédito global |
| LittleSis | https://littlesis.org/ | Poder + conexões |
| Kompass | https://www.kompass.com/ | B2B diretório |
| CorporateInformation | https://www.corporateinformation.com/ | Análise financeira |
| SEC EDGAR | https://www.sec.gov/edgar | Empresas públicas EUA |
| CVM Brasil | https://www.gov.br/cvm/ | Empresas listadas BR |
| Companies House (UK) | https://www.gov.uk/government/organisations/companies-house | Empresas UK |

---

## 15. Infraestrutura de Rede, Threat Intelligence e Malware

### 15.1 Plataformas de Threat Intelligence (TI)

| Ferramenta | URL | Função |
|---|---|---|
| VirusTotal | https://www.virustotal.com/ | Multi-engine scanner + grafo |
| AlienVault OTX | https://otx.alienvault.com/ | Comunidade TI (pulses) |
| MISP | https://www.misp-project.org/ | Plataforma TI open-source (auto-hospedável) |
| OpenCTI | https://www.opencti.io/ | TI com STIX 2.1 |
| ThreatConnect | https://threatconnect.com/ | TI enterprise |
| Anomali ThreatStream | https://www.anomali.com/ | TI enterprise |
| Recorded Future | https://www.recordedfuture.com/ | TI + dark web |
| Mandiant Advantage | https://www.mandiant.com/advantage | TI Google |
| CrowdStrike Falcon X | https://www.crowdstrike.com/ | TI + atribuição APT |
| Kaspersky Threat Intelligence Portal | https://opentip.kaspersky.com/ | Lookup gratuito |
| Cisco Talos Intelligence | https://talosintelligence.com/ | Reputação IP/domínio/arquivo |
| IBM X-Force Exchange | https://exchange.xforce.ibmcloud.com/ | TI IBM |
| Microsoft Defender TI | https://ti.defender.microsoft.com/ | ex-RiskIQ PassiveTotal |
| ThreatBook | https://threatbook.io/ | TI asiática |
| QI-ANXIN | https://ti.qianxin.com/ | TI China |
| PulseDive | https://pulsedive.com/ | TI comunitária |
| GreyNoise | https://viz.greynoise.io/ | Scanners/ruído internet |
| SecurityTrails | https://securitytrails.com/ | Histórico domínios/DNS |
| DomainTools Iris | https://www.domaintools.com/ | Investigação domínios premium |
| Team Cymru Pure Signal | https://www.team-cymru.com/ | NetFlow + TI |
| Silent Push | https://www.silentpush.com/ | TI preditiva |
| Validin | https://www.validin.com/ | DNS/IP histórico |
| DNSDumpster | https://dnsdumpster.com/ | Mapeamento gratuito |

### 15.2 Repositórios Públicos de Malware e IoCs

| Ferramenta | URL | Função |
|---|---|---|
| MalwareBazaar (abuse.ch) | https://bazaar.abuse.ch/ | Amostras malware |
| URLhaus (abuse.ch) | https://urlhaus.abuse.ch/ | URLs maliciosas |
| ThreatFox (abuse.ch) | https://threatfox.abuse.ch/ | IoCs |
| Feodo Tracker (abuse.ch) | https://feodotracker.abuse.ch/ | Botnets bancários |
| SSL Blacklist (abuse.ch) | https://sslbl.abuse.ch/ | Certificados maliciosos |
| YARAify (abuse.ch) | https://yaraify.abuse.ch/ | YARA scanning |
| Any.Run | https://app.any.run/ | Sandbox interativa |
| Joe Sandbox | https://www.joesandbox.com/ | Sandbox profissional |
| Hybrid Analysis | https://www.hybrid-analysis.com/ | Sandbox CrowdStrike |
| Intezer Analyze | https://analyze.intezer.com/ | Genética de malware |
| Triage (Hatching) | https://tria.ge/ | Sandbox rápida |
| CAPE Sandbox | https://capev2.hatching.io/ | Open-source |
| Cuckoo Sandbox | https://cuckoosandbox.org/ | Auto-hospedável |
| VX Underground | https://vx-underground.org/ | Biblioteca histórica (uso com cautela) |
| MalShare | https://malshare.com/ | Compartilhamento amostras |
| VirusBay | https://beta.virusbay.io/ | Colaboração IR |
| Open Threat Exchange (OTX) | https://otx.alienvault.com/ | IoCs comunitários |

### 15.3 Análise Estática e Dinâmica

| Ferramenta | Função |
|---|---|
| PEStudio | Análise estática PE |
| Ghidra (NSA) | Engenharia reversa |
| IDA Free/Pro | Disassembler |
| Radare2/Cutter | RE open |
| Binary Ninja | RE comercial |
| x64dbg | Debugger |
| DIE (Detect It Easy) | Detecção packer |
| CAPA (Mandiant) | Capacidades de binários |
| Yara / YaraEditor | Regras de detecção |
| FLOSS (Mandiant) | Extração strings ofuscadas |
| PE-sieve / HollowsHunter | Injeção/hollowing |
| Volatility / MemProcFS | Forense memória |
| Autopsy / Sleuth Kit | Forense disco |
| Plaso / log2timeline | Timelines forenses |

### 15.4 Emulação e Phishing Kit Analysis

| Ferramenta | URL | Função |
|---|---|---|
| urlscan.io | https://urlscan.io/ | Sandbox URL |
| Browserling | https://www.browserling.com/ | Testar URLs com segurança |
| Phish.Report | https://phish.report/ | Takedown + análise |
| Sucuri SiteCheck | https://sitecheck.sucuri.net/ | Malware web |
| Quttera | https://quttera.com/ | Malware sites |
| VirusTotal URL | https://www.virustotal.com/gui/home/url | Multi-engine |
| Gophish | https://getgophish.com/ | Framework phishing (red team) |
| Zphisher / SocialFish | GitHub | Kits (uso apenas em lab autorizado) |
| PhishTool | https://www.phishtool.com/ | Triagem e-mails |
| Phishunt | https://phishunt.io/ | Caça phishing |

### 15.5 Inteligência sobre Vulnerabilidades

| Fonte | URL | Uso |
|---|---|---|
| NVD (NIST) | https://nvd.nist.gov/ | CVEs oficiais |
| MITRE CVE | https://cve.mitre.org/ | Catálogo CVE |
| CISA KEV | https://www.cisa.gov/known-exploited-vulnerabilities-catalog | Exploradas ativamente |
| Exploit-DB | https://www.exploit-db.com/ | PoCs |
| Packet Storm | https://packetstormsecurity.com/ | Exploits e advisories |
| Vulners | https://vulners.com/ | Busca unificada |
| OpenCVE | https://www.opencve.io/ | Monitor CVE |
| VulnCheck | https://vulncheck.com/ | TI vuln comercial |
| Zero Day Initiative | https://www.zerodayinitiative.com/ | Disclosures |
| Rapid7 AttackerKB | https://attackerkb.com/ | Contexto exploit |
| GitHub Advisory DB | https://github.com/advisories | Vulns em deps |
| OSV.dev (Google) | https://osv.dev/ | Vulns open-source |
| CERT.br | https://www.cert.br/ | Alertas BR |
| CTIR Gov (GSI/PR) | https://www.gov.br/ctir/pt-br | Incidentes governo BR |

### 15.6 Honeypots e Coleta de Scanners

| Ferramenta | Função |
|---|---|
| T-Pot (Telekom) | Plataforma honeypot unificada |
| Cowrie | SSH/Telnet honeypot |
| Dionaea | Serviços de rede |
| HoneyDB | API de atacantes |
| SANS ISC DShield | Feeds comunitários |
| GreyNoise Visualizer | Classifica scanners legítimos vs maliciosos |

---

## 16. Investigação Patrimonial e de Bens

### 16.1 Imóveis (Brasil)

| Fonte | URL | Uso |
|---|---|---|
| Registro de Imóveis Eletrônico | https://www.registradores.org.br/ | Consulta via SREI |
| IRIB (Inst. Registro Imobiliário BR) | https://www.irib.org.br/ | Pesquisa por CPF/CNPJ (pago) |
| CENSEC | https://censec.org.br/ | Registros centralizados |
| ITRB — Prefeituras | Variável por município | IPTU por proprietário (via ofício) |
| INCRA / SIGEF | https://sigef.incra.gov.br/ | Imóveis rurais |
| SNCR | https://sncr.serpro.gov.br/ | Cadastro rural |
| CAR — Cadastro Ambiental Rural | https://www.car.gov.br/ | Propriedades rurais |
| CEMAP (Min. Saúde) | Variável | Propriedades saneamento |

### 16.2 Veículos, Aeronaves e Embarcações

| Fonte | URL | Uso |
|---|---|---|
| SENATRAN / Infoseg (via ofício) | https://www.gov.br/senatran | Consulta oficial |
| ANAC — RAB (Registro Aeronáutico) | https://sistemas.anac.gov.br/aeronaves/cons_rab.asp | Aeronaves civis BR |
| Marinha — Tribunal Marítimo | https://www.marinha.mil.br/tm/ | Embarcações |
| ANTAQ | https://www.gov.br/antaq/pt-br | Transporte aquaviário |
| Equasis | https://www.equasis.org/ | Embarcações globais |
| MarineTraffic / VesselFinder | — | Rastreamento AIS |
| FlightAware / ADS-B Exchange | — | Rastreamento aéreo |
| OpenSky Network | https://opensky-network.org/ | Dados ADS-B abertos |

### 16.3 Registros de Pessoas e Empresas (BR)

| Fonte | URL | Uso |
|---|---|---|
| Portal da Transparência (CGU) | https://portaldatransparencia.gov.br/ | Servidores, benefícios, CEIS |
| CEIS / CNEP / CEPIM | Portal Transparência | Empresas inidôneas |
| SIAFI / SIASG / Compras.gov | https://www.gov.br/compras/pt-br | Licitações e contratos |
| SIAPE | via LAI | Servidores federais |
| TCU — Cruzamento de Dados | https://portal.tcu.gov.br/ | Fiscalização |
| e-SIC / Fala.BR | https://falabr.cgu.gov.br/ | Pedidos LAI |
| Receita Federal — CNPJ/CPF | https://www.gov.br/receitafederal | Consulta cadastral |
| TSE Dados Abertos | https://dadosabertos.tse.jus.br/ | Candidatos, doações, patrimônio declarado |
| ANS / CNES / CADSUS | — | Prestadores saúde |
| OAB / CFM / CREA / CRM / CORECON | Variável | Conselhos profissionais |

### 16.4 Internacional

| Fonte | URL | Uso |
|---|---|---|
| Offshore Leaks (ICIJ) | https://offshoreleaks.icij.org/ | Panama/Paradise/Pandora |
| OpenSanctions | https://www.opensanctions.org/ | PEPs, sanções |
| US Property Shark | https://www.propertyshark.com/ | EUA imóveis |
| UK Land Registry | https://www.gov.uk/government/organisations/land-registry | Imóveis UK |
| Spain Registro de la Propiedad | https://www.registradores.org/ | Imóveis Espanha |
| Portugal IRN | https://justica.gov.pt/ | Registros Portugal |
| Companies House UK | https://find-and-update.company-information.service.gov.uk/ | Empresas UK |
| SEC EDGAR | https://www.sec.gov/edgar | Empresas listadas EUA |
| EU Business Register | https://e-justice.europa.eu/ | UE |

---

## 17. HUMINT Digital (Sockpuppets e Engenharia Social)

⚠️ **Uso estritamente profissional, autorizado e documentado.** Operações encobertas em ambiente digital devem estar previstas em MP/ordem judicial quando cabível, nos termos da **Lei 12.850/2013 (arts. 10 a 10-C)** — infiltração de agentes. Fora desses contextos, sockpuppets podem configurar **estelionato (art. 171 CP)**, **falsa identidade (art. 307 CP)** ou **violação de ToS** com repercussões probatórias.

### 17.1 Princípios Operacionais

- **Compartimentação total**: nunca use o mesmo endpoint/IP para persona real e sockpuppet.
- **Legend consistency**: backstopping — perfil precisa ter histórico plausível (fotos EXIF-limpas, atividade temporal distribuída, pegada digital em múltiplas plataformas).
- **Device hygiene**: VM dedicada, navegador com perfil limpo, fingerprint distinto, anti-canvas/WebGL.
- **Rede**: VPN comercial + Tor quando aplicável + residencial proxy para evitar detecção de data center.
- **OPSEC temporal**: horário de atividade coerente com fuso declarado da persona.
- **Financeiro**: se a persona precisar de pagamentos, usar pré-pago não rastreável — mas apenas em operações autorizadas.

### 17.2 Ferramentas de Apoio a Personas

| Ferramenta | URL | Função |
|---|---|---|
| This Person Does Not Exist | https://thispersondoesnotexist.com/ | Avatar GAN (⚠️ facialmente detectável) |
| Generated.Photos | https://generated.photos/ | Bancos de avatares IA |
| Fake Name Generator | https://www.fakenamegenerator.com/ | Identidade sintética |
| BrowserLeaks | https://browserleaks.com/ | Checar fingerprint |
| AmIUnique | https://amiunique.org/ | Unicidade navegador |
| CreepJS | https://abrahamjuliot.github.io/creepjs/ | Detecção anti-bot |
| Multilogin / GoLogin / Incogniton | Comerciais | Anti-detect browsers |
| Kameleo / AdsPower | Comerciais | Gestão multi-perfil |

### 17.3 Detecção de Sockpuppets Adversários

| Sinal | Indicador |
|---|---|
| Metadados avatar | EXIF intacto revela câmera/app/IA |
| Temporal | Atividade 24/7, picos fora do fuso declarado |
| Conteúdo | Poucos posts originais, muito repost/like |
| Rede social | Poucos seguidores com interação real; clusters recíprocos |
| Stylometry | Estilo de escrita inconsistente entre posts |
| Erros linguísticos | Tradução automática/IA detectável |
| Comportamento | Responde em segundos; nunca foge do roteiro |
| Face GAN | Olhos assimétricos, cenário desfocado, acessórios quebrados |

### 17.4 Frameworks Defensivos

- **Sockpuppet Detection** (várias heurísticas acadêmicas)
- **Botometer** (X/Twitter)
- **Hoaxy** (difusão de desinformação)
- **DFRLab Open-Source Tools**
- **Graphika** (análise de redes coordenadas)

---

## 18. Linux / CLI para OSINT e Forense

### 18.1 Distribuições Especializadas

| Distro | Foco |
|---|---|
| Tsurugi Linux | Forense digital |
| CSI Linux | OSINT + forense |
| Kali Linux | Pentest (ferramentas úteis também p/ investigação) |
| Parrot Security | Pentest + forense + OSINT |
| BackBox | Pentest |
| CAINE | Forense italiana |
| SIFT Workstation (SANS) | IR/forense |
| REMnux | Análise malware |
| Whonix / Tails | Anonimato (para OPSEC) |
| Commando VM / FLARE VM | Windows RE |

### 18.2 Ferramentas CLI Essenciais

| Ferramenta | GitHub / Pacote | Função |
|---|---|---|
| theHarvester | github.com/laramies/theHarvester | Subdomínios, e-mails |
| recon-ng | github.com/lanmaster53/recon-ng | Framework modular |
| sherlock | github.com/sherlock-project/sherlock | Username multi-plataforma |
| holehe | github.com/megadose/holehe | E-mail em serviços |
| maigret | github.com/soxoj/maigret | Username + metadados |
| blackbird | github.com/p1ngul1n0/blackbird | Username multi |
| photon | github.com/s0md3v/Photon | Crawler OSINT |
| spiderfoot | github.com/smicallef/spiderfoot | Automação multi-módulo |
| subfinder | github.com/projectdiscovery/subfinder | Enum subdomínios |
| amass | github.com/owasp-amass/amass | Enum ativa/passiva |
| assetfinder | github.com/tomnomnom/assetfinder | Subdomínios |
| httpx | github.com/projectdiscovery/httpx | HTTP probing |
| nuclei | github.com/projectdiscovery/nuclei | Scanner vuln templated |
| naabu | github.com/projectdiscovery/naabu | Port scanner |
| katana | github.com/projectdiscovery/katana | Crawler |
| dnsx | github.com/projectdiscovery/dnsx | Resolver DNS |
| shuffledns | github.com/projectdiscovery/shuffledns | Enum massiva |
| waybackurls | github.com/tomnomnom/waybackurls | URLs Wayback |
| gau (GetAllUrls) | github.com/lc/gau | URLs de múltiplas fontes |
| hakrawler | github.com/hakluke/hakrawler | Crawler rápido |
| gowitness | github.com/sensepost/gowitness | Screenshot em massa |
| aquatone | github.com/michenriksen/aquatone | Inspeção visual |
| exiftool | pacote exiftool | Metadados |
| oletools (olevba/oleid/oledump) | PyPI | Macros Office |
| peepdf | PyPI | PDF malicioso |
| binwalk | github.com/ReFirmLabs/binwalk | Análise firmware |
| foremost / scalpel | pacotes | Carving |
| steghide / stegoveritas / zsteg | pacotes | Esteganografia |
| yt-dlp | github.com/yt-dlp/yt-dlp | Download vídeo/áudio |
| ffmpeg | ffmpeg.org | Mídia |
| mediainfo | mediaarea.net | Metadados mídia |
| whisper / whisperx / faster-whisper | OpenAI / comunitários | Transcrição |
| ripgrep / ugrep | — | Grep rápido em dumps |
| jq / yq | — | JSON/YAML parsing |
| dsniff / mitmproxy / bettercap | — | Tráfego (apenas em ambiente autorizado ⚠️) |
| wireshark / tshark / zeek | — | Análise de tráfego |
| tor + torsocks | — | Rotear CLI via Tor |
| proxychains | — | Encadear proxies |

### 18.3 Frameworks Maiores

- **Buscador/IntelTechniques VM** (descontinuado, mas base de referência)
- **OSINT Framework CLI** (Trace Labs)
- **Mr. Holmes** — bots OSINT
- **Lockdoor Framework**
- **Final Recon**
- **Datasploit** (arquivo histórico)

---

## 19. OPSEC para Investigadores

### 19.1 Princípios

1. **Assuma compromisso permanente**: o alvo PODE estar monitorando.
2. **Compartimentação**: separe persona real, persona investigativa e infraestrutura operacional.
3. **Minimização**: colete o mínimo necessário; não "stalkeie" além do escopo legal.
4. **Documentação**: cadeia de custódia desde o primeiro acesso (Hunchly, ata notarial).
5. **Anti-atribuição**: IP, DNS, timezone, idioma, fingerprint, padrões comportamentais — todos coerentes com a legenda.

### 19.2 Infraestrutura Mínima

| Camada | Ferramenta |
|---|---|
| Host | Máquina física dedicada OU VM descartável (VMware/VirtualBox/Proxmox/Qubes) |
| SO operacional | Linux hardened, Tails (live), Whonix (Tor-gated) |
| Navegador | Firefox com user.js hardening OU Brave privado OU Tor Browser (quando apropriado) |
| Container de sessão | Firefox Multi-Account Containers / Temporary Containers |
| Anti-fingerprint | CanvasBlocker, FingerprintDefender, JShelter, LibreWolf, Mullvad Browser |
| DNS | DoH via Cloudflare 1.1.1.1, Quad9, Mullvad DNS, DNSCrypt |
| VPN | Mullvad, IVPN, ProtonVPN, Windscribe (com pagamento anônimo quando operacional) |
| Tor | Tor Browser, tor + obfs4/meek-azure para redes restritivas |
| E-mail | ProtonMail, Tutanota, Mailfence (contas operacionais) |
| Armazenamento | Cryptomator, VeraCrypt, LUKS (containers encriptados) |
| Comunicação | Signal, SimpleX (com cuidados de OPSEC do device) |
| Senhas | KeePassXC / Bitwarden self-hosted |
| 2FA | Hardware (YubiKey, Solo) — evitar SMS |

### 19.3 Checklist Pré-Operação

- [ ] VM com snapshot limpo
- [ ] VPN conectada ANTES de qualquer app
- [ ] Kill switch de VPN ativo
- [ ] DNS leak test (browserleaks.com)
- [ ] WebRTC leak test
- [ ] Fingerprint test (amiunique.org, creepjs)
- [ ] Timezone/locale coerentes com legenda
- [ ] JavaScript/cookies conforme política do caso
- [ ] Hunchly ativo (captura forense)
- [ ] Comando/MP/ordem judicial em mãos (quando necessário)
- [ ] Registro formal início: data, hora, investigador, caso

### 19.4 Armadilhas Comuns

- **Canary tokens**: links/imagens que notificam o alvo quando você acessa (use Thinkst Canary para PROTEGER; saiba que alvos podem usar contra você).
- **Referer leak**: hyperlinks vazam origem; use `rel="noreferrer"`.
- **Browser fingerprint único**: navegador padrão + extensões delatam identidade.
- **Retweet/like acidental**: manter conta logada em dispositivo errado.
- **Metadados em ofícios/laudos**: limpar EXIF/autor antes de compartilhar.
- **Reutilização de screenshots**: Hunchly adiciona hash + timestamp forense; prints soltos não.
- **Google account persistente**: pesquisas logado vs anônimo = resultados diferentes + expõe investigador.

### 19.5 Firefox user.js — Endereços de Referência

- **arkenfox/user.js**: github.com/arkenfox/user.js (hardening validado pela comunidade)
- **Betterfox**: github.com/yokoffing/Betterfox (balanceado)
- Configurações críticas:
  - `privacy.resistFingerprinting = true`
  - `media.peerconnection.enabled = false` (WebRTC)
  - `network.dns.disablePrefetch = true`
  - `network.prefetch-next = false`
  - `browser.safebrowsing.*` conforme necessidade

---

## 20. Inteligência Artificial Aplicada à Investigação

### 20.1 LLMs em Nuvem (Uso com Cautela de Dados)

⚠️ **Atenção LGPD/sigilo**: nunca submeta dados pessoais de investigados, conteúdo sob segredo de justiça ou documentos classificados a APIs comerciais sem contrato com cláusulas de não-treinamento e residência de dados compatível. Para dados sensíveis, prefira **soluções locais** (seção 20.2).

| Plataforma | URL | Observações |
|---|---|---|
| Claude (Anthropic) | https://claude.ai | Excelente em análise textual e raciocínio |
| ChatGPT | https://chat.openai.com | GPT-4o/o1 para raciocínio |
| Gemini | https://gemini.google.com | Multimodal + integração Google |
| Perplexity | https://www.perplexity.ai | Busca com citações |
| Mistral Le Chat | https://chat.mistral.ai | Empresa europeia (GDPR) |
| DeepSeek | https://chat.deepseek.com | Raciocínio chinês |
| Kagi Assistant | https://kagi.com/assistant | Busca + LLMs |

### 20.2 LLMs Locais (Ollama / LM Studio / vLLM / llama.cpp)

🎯 **Recomendado para investigação com dados sensíveis** — processamento 100% offline, sem envio a terceiros. Abaixo sugestões considerando hardware com ~16–24 GB VRAM.

#### 20.2.1 Modelos para Análise Textual em Português

| Modelo | Tamanho / Quant | VRAM aprox. | Uso |
|---|---|---|---|
| Llama 3.3 70B | Q4_K_M | ~42 GB (offload necessário) | Topo de linha; exige CPU+VRAM |
| Llama 3.1 70B | Q4_K_M | ~42 GB | Alternativa estável |
| Llama 3.1 8B | Q8_0 | ~9 GB | Ótima para 16 GB VRAM |
| Qwen 2.5 72B | Q4_K_M | ~44 GB | Forte em português, matemática |
| Qwen 2.5 32B | Q4_K_M / Q5_K_M | ~20–24 GB | **Sweet spot para RTX ADA 24GB** |
| Qwen 2.5 14B | Q8_0 | ~16 GB | Excelente custo-benefício |
| Qwen 2.5 7B | Q8_0 | ~8 GB | Rápido para triagem |
| Qwen3 14B / 32B | Q4/Q5 | 14–24 GB | Geração recente |
| Mistral Large 2411 | Q4 | ~70 GB (offload) | Topo com licença restrita |
| Mistral Small 24B (2501) | Q4_K_M | ~15 GB | **Ótimo p/ 16 GB** |
| Mistral Nemo 12B | Q6_K | ~10 GB | Eficiente |
| Gemma 3 27B | Q4_K_M | ~18 GB | **Forte em PT-BR** |
| Gemma 3 12B | Q6_K | ~10 GB | Rápido |
| Gemma 3 4B | Q8_0 | ~5 GB | Extração leve |
| Phi-4 14B | Q6_K | ~12 GB | Raciocínio denso |
| Command R+ 104B | Q4 | ~64 GB | RAG especializado |
| Command R 35B | Q4_K_M | ~22 GB | RAG com boa PT |
| DeepSeek-R1-Distill 32B / 14B | Q4/Q6 | 12–22 GB | Raciocínio (cuidado: verboso) |
| Sabiá / Maritaca (comercial PT-BR) | API BR | — | Alternativa nacional |

#### 20.2.2 Modelos de Visão (VLM) para OCR / Relatórios / Tabelas

| Modelo | Uso | Observações |
|---|---|---|
| Qwen2-VL 7B / 72B | OCR + raciocínio visual | Excelente em tabelas e documentos PT-BR |
| Qwen2.5-VL 7B / 32B / 72B | Versão mais recente | Ganho em OCR estruturado |
| MiniCPM-V 2.6 (8B) | OCR multilíngue | Rápido, roda em 16 GB |
| MiniCPM-o 2.6 | Multimodal + áudio | Leve |
| InternVL 2.5 / 3 (até 78B) | Documentos complexos | Forte em charts/formulários |
| LLaVA 1.6 / NeXT | Base clássica | Mais leve, menor qualidade atual |
| Llama 3.2 Vision 11B / 90B | Visão Meta | Integra bem com Ollama |
| Pixtral 12B (Mistral) | Visão europeia | Contexto longo |
| docTR / Nougat (Meta) | OCR acadêmico/científico | Especializado em layout |
| PaddleOCR | OCR tradicional | Muito bom em PT; rápido em GPU |
| Tesseract 5 + LSTM | OCR clássico | Fallback confiável |
| Surya OCR | OCR multilíngue moderno | Layout + linhas |
| EasyOCR | OCR leve | Quando não precisa de raciocínio |

#### 20.2.3 Transcrição de Áudio (Interceptações, Escutas, Vídeos)

| Ferramenta | Uso |
|---|---|
| OpenAI Whisper (large-v3) | Padrão; roda local |
| Faster-Whisper (CTranslate2) | 4–10× mais rápido |
| WhisperX | Diarização (separar falantes) + alinhamento |
| Whisper.cpp | CPU/metal/CUDA leve |
| Pyannote | Diarização profissional |
| NeMo (NVIDIA) | Pipelines ASR + diarização |
| SpeechBrain | Toolkit acadêmico |
| Vosk | Offline leve |

#### 20.2.4 Embeddings e RAG Investigativo

| Ferramenta | Função |
|---|---|
| nomic-embed-text | Embeddings locais |
| bge-m3 (BAAI) | Multilíngue, forte em PT |
| multilingual-e5-large | Baseline sólido |
| Jina Embeddings v3 | Contexto longo |
| Qdrant / Milvus / Weaviate / Chroma | Vector DBs |
| LangChain / LlamaIndex / Haystack | Orquestração RAG |
| AnythingLLM / LibreChat / Open WebUI | Front-ends p/ LLMs locais |
| Msty | UI desktop + multi-provider |
| GPT4All | Desktop offline |

### 20.3 Casos de Uso Investigativos (Local-First)

| Tarefa | Modelo Sugerido |
|---|---|
| Revisão ortográfica/gramatical de relatórios em PT | Qwen 2.5 14B/32B, Gemma 3 12B/27B |
| Sumarização de autos processuais volumosos | Qwen 2.5 32B / Mistral Small 24B |
| Extração estruturada de entidades (CPF, CNPJ, IP, valores) | Qwen 2.5 7B/14B + prompt JSON |
| OCR de relatórios digitalizados com tabelas | Qwen2.5-VL 7B/32B, MiniCPM-V 2.6 |
| Tradução PT↔EN↔ES de mensagens apreendidas | Gemma 3, Qwen 2.5 |
| Transcrição de mídia apreendida | WhisperX (diarizado) |
| Análise de logs (firewall, proxy, auth) | Qwen 2.5 7B + regex + scripts |
| Comparação de estilos (stylometry) | Embeddings BGE-m3 + cosine |
| Classificação de conteúdo (golpe, pornografia etc.) | Classificadores ad-hoc via prompt |
| RAG sobre jurisprudência BR | bge-m3 + Qdrant + Qwen/Gemma |

### 20.4 Deepfakes e Mídia Sintética — Detecção

| Ferramenta | Função |
|---|---|
| Sensity AI | Comercial, detecção multimodal |
| Intel FakeCatcher | Biossinais (PPG) |
| Reality Defender | Comercial |
| Truepic / C2PA | Proveniência (autenticação de origem) |
| Microsoft Video Authenticator | Análise de frames |
| DeepFake-o-Meter | Agregador acadêmico |
| FakeImageDetector | Web |
| Hugging Face deepfake-detector models | Open |
| Faceforensics++ | Dataset/referência |
| AI or Not | Classificador geral |
| Hive Moderation | API comercial |
| Photo Forensics (Foto Forensics) | ELA |

---

## 21. Scraping, Automação e Coleta em Escala

⚠️ **Legalidade**: observar **Marco Civil da Internet** (art. 7º, 8º), **LGPD**, **Lei 12.965/2014**, termos de serviço dos sites e **robots.txt**. Scraping automatizado em escala pode configurar abuso de acesso. Em investigação oficial, documente a necessidade e a finalidade legítima.

### 21.1 Frameworks

| Ferramenta | Linguagem | Uso |
|---|---|---|
| Scrapy | Python | Crawler robusto |
| Scrapy-Splash / Scrapy-Playwright | Python | Páginas JS |
| Playwright | Python/JS | Automação headless moderna |
| Puppeteer | JS | Headless Chrome |
| Selenium | Multi | Clássico |
| Crawlee (Apify) | Node | Framework completo |
| Colly | Go | Alta performance |
| Requests + BeautifulSoup | Python | Simples/rápido |
| httpx (python) + selectolax | Python | Paralelo e rápido |
| curl-impersonate / curl_cffi | — | TLS fingerprint real |
| undetected-chromedriver | Python | Bypass básico anti-bot |
| Hrequests / Nodriver | Python | Anti-detect moderno |

### 21.2 Plataformas e Serviços

| Serviço | URL | Uso |
|---|---|---|
| Apify | https://apify.com/ | Actors prontos |
| Bright Data | https://brightdata.com/ | Proxies + scraping |
| Oxylabs | https://oxylabs.io/ | Proxies enterprise |
| Smartproxy | https://smartproxy.com/ | Residencial |
| ScrapFly | https://scrapfly.io/ | API anti-bloqueio |
| ScrapingBee | https://www.scrapingbee.com/ | API |
| ZenRows | https://www.zenrows.com/ | Anti-bot |
| Browserless | https://www.browserless.io/ | Chrome remoto |

### 21.3 Bypass de Proteções

| Desafio | Abordagem |
|---|---|
| Cloudflare | curl_cffi, FlareSolverr, Playwright stealth |
| reCAPTCHA v2/v3 | 2Captcha, Anti-Captcha, CapSolver (serviços) |
| hCaptcha | idem |
| Akamai / DataDome | Residencial proxy + browser real |
| Rate limit | Rotação de user-agent, IPs, throttle |
| Fingerprint TLS/HTTP2 | curl-impersonate, Hrequests |

### 21.4 Pipelines e Orquestração

- **Airflow / Prefect / Dagster** — workflows
- **Celery / RQ / Dramatiq** — filas
- **n8n / Node-RED** — low-code
- **GitHub Actions** — agendamento leve
- **Kubernetes Jobs / CronJobs** — escala

---

## 22. Análise, Visualização e Gestão de Casos

### 22.1 Link Analysis / Graph

| Ferramenta | Tipo | Uso |
|---|---|---|
| Maltego | Comercial | Padrão indústria OSINT |
| i2 Analyst's Notebook (IBM) | Comercial | Policial/militar |
| Palantir Gotham / Foundry | Comercial | Inteligência/governo |
| Nuix Investigate | Comercial | E-discovery + inv. |
| Cellebrite Pathfinder | Comercial | Ligações + mídia |
| Magnet AXIOM | Comercial | Forense + análise |
| Gephi | Open | Visualização grafo |
| Cytoscape | Open | Bio/redes |
| yEd | Freemium | Grafos rápidos |
| Neo4j / Neo4j Bloom | DB grafo | Consulta Cypher |
| Memgraph | DB grafo | Tempo real |
| ArangoDB | Multi-model | Grafo + docs |
| Graphistry | GPU-viz | Grafos grandes |
| Kumu | Web | Relacionamento |
| OSINT Combine OSINT Explorer | Comercial | Automação |
| Social Links CRIMEWALL | Comercial | Policial |
| IBM Watson Explorer | Comercial | Discovery |

### 22.2 Análise de Dados e BI

| Ferramenta | Uso |
|---|---|
| Jupyter / JupyterLab / VSCode | Notebooks |
| Pandas / Polars / DuckDB | Dataframes |
| Apache Superset / Metabase / Redash | BI open |
| Kibana / Grafana | Logs e séries |
| Splunk / Elastic Security | SIEM |
| Timesketch | Forense temporal |
| Plaso / log2timeline | Eventos forenses |
| Elasticsearch / OpenSearch | Busca |
| ClickHouse | Analytics colunar |

### 22.3 Gestão de Casos e Captura Forense

| Ferramenta | URL | Uso |
|---|---|---|
| Hunchly | https://www.hunch.ly/ | Captura forense web (padrão de fato) |
| WebPreserver | https://www.webpreserver.com/ | Captura com hash |
| Page Vault | https://www.page-vault.com/ | Preservação web jurídica |
| X1 Social Discovery | https://www.x1.com/ | Forense social |
| Pagefreezer | https://www.pagefreezer.com/ | Arquivamento |
| ArchiveBox | https://archivebox.io/ | Self-hosted |
| SingleFile | Extensão | Salvar HTML completo |
| Save Page Now (Archive.org) | https://web.archive.org/save | Preservação pública |
| Conifer | https://conifer.rhizome.org/ | Captura interativa |
| CaseBoard (MPF BR) | Interno | Gestão |
| OCR-based case tools variados | — | — |

### 22.4 Documentação e Relatórios

- **Obsidian / Logseq** — notas com links
- **Joplin** — notas criptografadas
- **Standard Notes** — E2E
- **Notion** — colaborativo (cuidado com sigilo)
- **Typora / Mark Text** — Markdown
- **LaTeX / Pandoc** — laudos e documentos formais
- **draw.io / diagrams.net** — diagramas de fluxo

---

## 23. Frameworks, Metodologias e Legislação

### 23.1 Frameworks de Investigação

| Framework | Fonte |
|---|---|
| OSINT Framework | https://osintframework.com/ |
| Bellingcat Online Investigation Toolkit | https://bit.ly/bcattools |
| IntelTechniques Toolkit | https://inteltechniques.com/tools/ |
| MISP Project | https://www.misp-project.org/ |
| SANS OSINT / SEC487 / FOR578 | https://www.sans.org/ |
| Trace Labs OSINT Framework | https://www.tracelabs.org/ |
| Open Source Security Testing Methodology (OSSTMM) | https://www.isecom.org/ |
| PTES (Penetration Testing Execution Standard) | http://www.pentest-standard.org/ |

### 23.2 Modelos Analíticos

- **Intelligence Cycle** (planejamento → coleta → processamento → análise → disseminação → feedback)
- **Diamond Model of Intrusion Analysis** (adversário, capacidade, infraestrutura, vítima)
- **Cyber Kill Chain** (Lockheed Martin)
- **MITRE ATT&CK** (táticas/técnicas/procedimentos)
- **MITRE D3FEND** (defensivo)
- **Pyramid of Pain** (David Bianco)
- **F3EAD** (Find, Fix, Finish, Exploit, Analyze, Disseminate)
- **PIR** (Priority Intelligence Requirements)
- **Analysis of Competing Hypotheses (ACH)** — Heuer/CIA
- **SATS — Structured Analytic Techniques**
- **SMART/SAEDA** (contrainteligência)
- **COPINE Scale / SAP Scale** — classificação CSAM (NCMEC)

### 23.3 Legislação Brasileira Relevante

| Norma | Assunto |
|---|---|
| CF/88 art. 5º, X, XII, LVI | Intimidade, sigilo, prova ilícita |
| Código Penal — arts. 154-A, 154-B | Invasão de dispositivo informático |
| CP art. 171 / §§ 2º-A, 2º-B | Estelionato digital |
| CP art. 180 | Receptação (aplicável a dados) |
| CP art. 288 / 288-A | Associação criminosa |
| CP art. 307 | Falsa identidade |
| Lei 12.850/2013 | Organização criminosa; colaboração; infiltração |
| Lei 12.965/2014 (Marco Civil da Internet) | Guarda de registros, requisitos para entrega |
| Lei 9.296/1996 | Interceptação telefônica/telemática |
| Lei 9.613/1998 | Lavagem de dinheiro (COAF) |
| Lei 12.737/2012 (Carolina Dieckmann) | Crimes informáticos |
| Lei 13.441/2017 | Infiltração virtual — crimes contra crianças |
| Lei 13.709/2018 (LGPD) | Tratamento de dados + base legal investigativa (art. 4º, III) |
| Lei 14.063/2020 | Assinaturas eletrônicas |
| Lei 14.155/2021 | Agravamento estelionato eletrônico |
| MP 2.200-2/2001 | ICP-Brasil |
| Lei 9.807/1999 | Proteção a testemunhas |
| Lei 11.340/2006 (Maria da Penha) | Violência contra mulher |
| Lei 13.718/2018 | Importunação sexual / divulgação cena sexo |
| Lei 14.132/2021 | Stalking (perseguição) |
| Lei 14.344/2022 (Henry Borel) | Proteção à criança |
| CPP art. 157 | Provas ilícitas |
| CPP arts. 158-A a 158-F | Cadeia de custódia (Pacote Anticrime) |
| CPC art. 384 | Ata notarial |
| Res. CNJ 233/2016 / 345/2020 / 491/2022 | Processo eletrônico; juízo 100% digital |
| Res. CNMP 181/2017 | Investigação pelo MP |
| Portaria MJ 155/2018 | SINIESP |
| Decreto 10.046/2019 | Governança de dados + reconhecimento facial (gov) |
| Lei 14.063/2020 + Resoluções ANPD | LGPD regulamentação |

### 23.4 Instrumentos Internacionais

| Instrumento | Assunto |
|---|---|
| Convenção de Budapeste (2001) | Cibercrime — BR aderiu em 2023 |
| Convenção de Palermo (UNTOC) | Crime organizado |
| Convenção de Mérida | Corrupção |
| Acordo Brasil-EUA MLAT | Cooperação penal |
| Rede 24/7 (Budapeste) | Cooperação urgente |
| Interpol I-24/7 | Comunicação policial |
| Europol SIENA | Troca de info UE |
| FATF / GAFI | AML/CFT |
| Regulamentos da OFAC/UE | Sanções |

### 23.5 CTFs / Treinamento OSINT

- **Trace Labs Search Party CTF** — pessoas desaparecidas (reais)
- **SANS NetWars / Holiday Hack**
- **Cyber Defenders (CyberDefenders.org)**
- **LetsDefend / Blue Team Labs Online**
- **Hack The Box / TryHackMe** — trilhas OSINT
- **OSINT Dojo**
- **CTFtime.org** — calendário
- **GeoGuessr** — treino GEOINT
- **Quiztime (Twitter)** — desafios diários

---

## 24. 🆕 Tipologias de Cibercrime e Protocolos Investigativos

### 24.1 Fraudes Bancárias e Estelionato Digital

| Tipologia | Indicadores / Fontes |
|---|---|
| Phishing bancário | URLs clonadas, SMS/WhatsApp, TXID Pix, contas laranjas |
| SIM swap | Portabilidade irregular, perda súbita de sinal, acesso a OTP |
| Stealer + invasão de conta | Credenciais em infostealer logs, TOTP comprometido |
| Fraude em e-commerce | Chargeback, entrega em endereço falso |
| Fraude em marketplace (OLX/Mercado Livre) | Perfis recentes, pressa, pagamento fora da plataforma |
| Golpe do falso leilão | Sites clonados, boleto adulterado |
| Golpe do motoboy | Ligação falsa bancária + retirada cartão |
| Falso suporte bancário | Vishing, TeamViewer/AnyDesk |
| Pix malicioso (QR adulterado) | Chaves falsas, beneficiário divergente |

**Artefatos de interesse**: logs de acesso, registros SPI/Bacen (via ofício), dispositivo apreendido, telemetria do app bancário, TXIDs Pix, e-mails de confirmação, números chamadores (via operadora).

### 24.2 Sextorsão e Crimes Sexuais Online

| Tipologia | Observações |
|---|---|
| Sextorsão adulta | Grooming → captura → extorsão. CP art. 158 |
| Revenge porn / NCII | Lei 13.718/2018 — 1 a 5 anos |
| Stalking digital | Lei 14.132/2021 — até 2 anos |
| Cyberbullying com vítima menor | ECA + CP |
| Deepfake pornográfico sem consentimento | Lei 14.811/2024 agravou CSAM; analisar enquadramento vítima adulta |

**Canais oficiais**:
- **SaferNet (disque 100)**: https://new.safernet.org.br/
- **NCMEC CyberTipline**: https://report.cybertip.org/
- **INHOPE**: https://www.inhope.org/
- **Interpol Baseline / ICSE DB** (via PF)
- **ESTUPRO / Central Mulher**: 180

### 24.3 Ransomware e Extorsão Corporativa

| Passo | Ação |
|---|---|
| Triagem inicial | Variante (ID Ransomware), vetor (phishing/RDP/CVE), impacto |
| IoCs | Extensões, notas de resgate, endereço BTC/Monero |
| Blockchain | Rastrear carteira de resgate — seção 9 |
| TOR leak site | Monitorar exposição de dados — seção 11 |
| Cooperação | CERT.br, CTIR Gov, FBI IC3, Europol |
| Decryptors | No More Ransom (nomoreransom.org) |

### 24.4 Pirâmides Financeiras e Golpes em Criptoativos

- **CVM** — Processos Administrativos Sancionadores públicos
- **COAF** — Relatórios RIF
- **Cadastro CVM de não autorizados**
- **MPF Força-Tarefa Tsunami Cripto** (precedente)
- Ferramentas seção 9 (Chainalysis/TRM/Arkham/Misttrack)

### 24.5 Violência Digital contra Mulher

**Canais**:
- **Ligue 180** — Central de Atendimento à Mulher
- **Delegacia Virtual (variável por UF)**
- **Lei Maria da Penha** online
- **SaferNet Helpline**
- Ferramentas de reconhecimento de imagem íntima: **StopNCII.org** (hashing consentido)

### 24.6 Material de Abuso Sexual Infantil (CSAM) — Protocolo Crítico

🛑 **PROTOCOLO**:
1. **NÃO baixar, não salvar, não encaminhar.** Apenas URL/hash é suficiente para a denúncia.
2. **Registrar hora, URL, screenshot com Hunchly** (sem baixar mídia).
3. **Denúncia imediata**: SaferNet (canais.safernet.org.br) + Polícia Federal
4. **Identificação**: PhotoDNA (Microsoft), Project Arachnid (C3P), NCMEC hashes
5. **Colaboração**: via PF → Interpol ICSE → Operação Luz na Infância / Darknet

### 24.7 Crimes contra Honra Online

- **Calúnia/Difamação/Injúria** — CP 138–140
- **Racismo/Injúria racial** — Lei 7.716/1989 + Lei 14.532/2023
- **Provas**: ata notarial (CPC 384), preservação via Marco Civil (MCI art. 10 § 2º: até 6 meses registros de conexão; 6 meses aplicação)

---

## 25. 🆕 Integração com o Processo Penal Brasileiro

### 25.1 Cadeia de Custódia Digital (CPP 158-A a 158-F)

| Etapa | Ação |
|---|---|
| Reconhecimento | Identificar fonte de prova digital |
| Isolamento | Evitar contaminação (modo avião, bloqueador de escrita) |
| Fixação | Hash SHA-256/SHA-3, fotografias, lacre |
| Coleta | Clonagem bit-a-bit quando possível (dd, FTK Imager) |
| Acondicionamento | Recipiente lacrado, etiqueta com hash |
| Transporte | Registro de quem, quando, como |
| Processamento | Laudo em ambiente controlado |
| Armazenamento | Servidor institucional com backup |
| Descarte | Conforme determinação judicial |

### 25.2 Preservação de Evidência Volátil Web

| Situação | Ferramenta |
|---|---|
| Print simples | ❌ Frágil juridicamente |
| Screenshot + hash manual | ⚠️ Aceitável com narrativa |
| **Ata notarial** (CPC 384) | ✅ Forte (tabelião fé pública) |
| **Hunchly** | ✅ Hash + metadados + cadeia |
| **Wayback Machine** | ✅ Fonte independente (corroboração) |
| **WebPreserver / Page Vault** | ✅ Preservação jurídica |

### 25.3 Laudos Periciais Digitais — Estrutura Típica

1. Identificação (autoridade solicitante, número de caso)
2. Descrição da autoridade e do perito
3. Material recebido (hash, lacre)
4. Quesitos formulados
5. Metodologia empregada (ferramentas, versões, hashes)
6. Exame (passo a passo, comandos, screenshots)
7. Respostas aos quesitos
8. Conclusão
9. Anexos (relatórios, capturas, códigos-fonte quando relevante)
10. Identificação digital e assinatura com e-CPF/ICP-Brasil

### 25.4 Modelos de Ofício (Requisição)

| Destinatário | Fundamento |
|---|---|
| Provedor de aplicação (Meta, Google, Microsoft etc.) | MCI art. 15 + art. 10, §1º (decisão judicial para conteúdo) |
| Provedor de conexão (ISP) | MCI art. 13 |
| Instituição financeira | LC 105/2001 (quebra de sigilo bancário) |
| Operadora de telecom | Lei 9.472/1997 + 9.296/1996 (interceptação) |
| Exchange de cripto | IN RFB 1.888/2019 + Lei 14.478/2022 |
| Prestadores internacionais | MLAT BR-EUA / Convenção Budapeste |
| Redes sociais (portais LEA) | https://www.facebook.com/records / https://lers.google.com/ / https://cs.linkedin.com/ etc. |

### 25.5 Portais LEA (Law Enforcement) dos Principais Provedores

| Provedor | Portal |
|---|---|
| Meta (Facebook/Instagram/WhatsApp) | https://www.facebook.com/records/ |
| Google (todos serviços) | https://lers.google.com/ |
| Microsoft | https://leportal.microsoft.com/ |
| X/Twitter | https://legalrequests.x.com/ |
| LinkedIn | https://cs.linkedin.com/ |
| Apple | legal@apple.com + Portal dedicado |
| TikTok | https://www.tiktok.com/legal/law-enforcement |
| Snap | https://www.snapchat.com/lawenforcement |
| Discord | https://discord.com/safety-policies |
| Telegram | abuse@telegram.org (limitado) |
| Cloudflare | https://support.cloudflare.com/hc/en-us/requests/new |
| GoDaddy | legal@godaddy.com |
| Registro.br | https://registro.br/ |
| NIC.br | https://cert.br/ / https://nic.br/ |
| Binance | law.enforcement@binance.com |
| Coinbase | https://www.coinbase.com/legal |
| Amazon AWS | https://pages.awscloud.com/LERS |
| Oracle / Microsoft Azure | Via forms corporativos |

---

## 26. 🆕 Ferramentas Dual-Use — Avisos Éticos e Legais

Esta seção reúne ferramentas **poderosas** cujo uso **exige fundamentação legal clara**, autorização institucional e respeito à LGPD/ANPD. Não são recomendadas para uso "livre" — são citadas porque investigadores precisam **conhecer** (tanto para operar quando autorizado quanto para defender vítimas que sofreram abuso dessas ferramentas).

### 26.1 Reconhecimento Facial em Escala Aberta

⚠️ **LGPD arts. 5º, II; 7º; 11 (dado sensível biométrico)** + **Decreto 10.046/2019** + **recomendações ANPD**. Uso em investigação depende de base legal específica (inciso III art. 4º LGPD para segurança pública) e proporcionalidade. Não use de forma indiscriminada.

| Ferramenta | Observação |
|---|---|
| PimEyes | Busca facial em fotos públicas; polêmica ética significativa |
| FaceCheck.ID | Similar |
| Lenso.ai | Busca facial + imagem reversa |
| Clearview AI | Apenas LEA autorizado (EUA); banido em várias jurisdições |
| Paravision / NEC / Cognitec | Enterprise |
| FindClone (RU) | Cobre VK russo |
| Search4Faces (RU) | VK/OK |
| DeepFace / InsightFace / CompreFace (open) | Auto-hospedado |

**Uso correto**: identificação de vítima desconhecida, reconhecimento de autor de crime com autorização, investigação com ordem judicial. **Uso incorreto**: vigilância em massa, perfilamento arbitrário.

### 26.2 Scraping Agressivo de Dados Pessoais

⚠️ **LGPD** + **Marco Civil**. Raspagem massiva de dados pessoais fora de base legal é ilícita — mesmo que tecnicamente viável.

| Ferramenta | Alerta |
|---|---|
| Datasets de "vazamentos" em Telegram/fóruns | Geralmente **crime-meio** (acesso indevido, receptação); prova contaminada |
| ProPrivacy / Hudson Rock | Comerciais com governança; usam fontes declaradas |
| SpyCloud / Constella Intelligence | LEA com contrato |
| Have I Been Pwned | Transparência + responsabilidade |
| DeHashed / Leak-Lookup | **Uso controverso** — verifique base legal antes |

### 26.3 Detecção de Stalkerware (Defesa de Vítimas)

✅ **Uso pró-vítima recomendado**:

| Ferramenta | Função |
|---|---|
| Coalition Against Stalkerware | https://stopstalkerware.org/ |
| TinyCheck (Kaspersky) | Detecção em Raspberry Pi |
| ISDi (Univ. Cornell) | Indicadores stalkerware |
| MVT (Amnesty) | Mobile Verification Toolkit — checa comprometimento |
| iVerify | iOS segurança |
| CERT.br Checagens | Material educativo |

### 26.4 Interceptação e Coleta de Tráfego

🛑 **Lei 9.296/1996** — interceptação telefônica/telemática requer **ordem judicial**. Fora disso, é crime (art. 10 da própria lei).

| Ferramenta | Alerta |
|---|---|
| Wireshark/tshark passivo | OK em rede própria/lab |
| Bettercap / Ettercap / mitmproxy | MITM — apenas em rede própria/autorizada |
| IMSI catchers (Stingray) | Uso restrito a LEA com mandado |
| FinFisher / Pegasus / Predator | Mercenários — polêmicas graves; cuidado jurídico máximo |

### 26.5 Vigilância de Redes Sociais em Escala

⚠️ **LGPD** — mesmo dados "públicos" em redes sociais têm limites para tratamento (finalidade, necessidade, base legal).

| Plataforma | Observação |
|---|---|
| Babel X / Cobwebs / Voyager / Fivecast / ShadowDragon / Social Links CRIMEWALL | Enterprise LEA — exigem contrato + governança |
| Palantir Gotham | Grandes operações policiais |
| Skopenow / Liferaft / Flashpoint Social | Investigação corporativa + LEA |

---

## 27. 🆕 Investigação de Operadores de Painéis Clandestinos

> **Nota importante**: esta seção substitui e desaconselha qualquer listagem de painéis clandestinos. A orientação correta não é "usar painéis com aviso legal", mas sim **investigar quem os opera**. Painéis não oficiais no Brasil são sustentados por **crimes-meio** — acesso indevido a Infoseg/Detran/Receita/Siapa (CP 154-A), divulgação ilegal de dados sigilosos (LGPD arts. 42-45), receptação de dados (CP 180), associação/organização criminosa (CP 288, Lei 12.850/2013), e frequentemente **vazamentos originados dentro de órgãos públicos** (corrupção, prevaricação). Usar tais painéis, mesmo em investigação, contamina a cadeia de custódia (CPP 157) e expõe o próprio investigador a imputações graves — há jurisprudência consolidada nesse sentido (STJ HC 598.051/SP e operações como Data Call, Datasan, Vazabus, Blackout do MPF/CGU).

### 27.1 Tipologia dos Operadores

| Perfil | Vetor |
|---|---|
| Agente público vazador | Login legítimo Infoseg/Detran/Receita usado para extrair lotes |
| Ex-agente público | Credenciais ainda válidas, estrutura de relações |
| Broker intermediário | Compra de múltiplas fontes, revende em painéis/bots |
| Operador de painel web | Hospeda interface, cobra mensalidade |
| Bot Telegram | Distribuição escalável (consulta por PIX) |
| Call center de golpe | Consome painéis para aplicar fraudes |
| Grupo cibercriminoso organizado | Combina painéis + malware + lavagem |

### 27.2 Vetores de Investigação

| Vetor | Detalhes |
|---|---|
| **Dinheiro** | Pix das mensalidades → CPFs/CNPJs recebedores → quebra bancária → lavagem |
| **Infraestrutura** | Domínio do painel → WHOIS → hospedagem → CDN → IP de origem → provedor |
| **Operacional** | Bot Telegram → @username do admin → dump de usuários → recon em OSINT |
| **Fonte primária** | Logs de acesso nos sistemas oficiais → correlação de consultas de massa → identificação do servidor público |
| **Marketing** | Anúncios em Telegram/WhatsApp/Instagram → perfis do anunciante |
| **Suporte técnico** | Grupos/canais de ajuda → membros → redes |
| **Criptomoedas** | Quando aceita cripto, rastreio on-chain (seção 9) |
| **SaaS usados** | Cloudflare (retirar proteção via ofício), hospedagem, gateway Pix |

### 27.3 Técnicas Específicas

| Técnica | Como |
|---|---|
| **Undercover/infiltração** | Lei 12.850/2013 — com MP/autorização judicial |
| **Auditoria de acessos Infoseg/Detran** | Via ofício + cooperação institucional; buscar padrões anômalos (muitas consultas/h, CPFs não relacionados a ocorrências) |
| **Análise de logs SIAPE/servidor** | Correlação temporal entre consultas oficiais e publicação no painel |
| **Cloudflare bypass** | Certificados (crt.sh), histórico DNS (SecurityTrails, Netlas), cabeçalhos de erro originais, origem IP em subdomínios esquecidos |
| **Pivot em Telegram** | Telepathy, Telegago, TGStat, análise de admins e mensagens encaminhadas |
| **Quebra de sigilo Pix** | Via ofício → Bacen/SPI → destinatários → rede de contas laranja |
| **Quebra de sigilo telefônico** | Lei 9.296/1996 para interceptação; MCI art. 10 para registros de conexão |
| **Cooperação internacional** | Se infra hospedada fora — MLAT ou Budapeste |

### 27.4 Legislação Aplicável aos Operadores

| Norma | Aplicação |
|---|---|
| CP art. 154-A / 154-B | Invasão de dispositivo informático (quando há acesso indevido) |
| CP art. 180 | Receptação (comercialização de dados obtidos ilicitamente) |
| CP art. 288 / 288-A | Associação criminosa |
| CP art. 313-A / 313-B | Inserção e modificação não autorizada em sistema da administração pública |
| CP art. 325 | Violação de sigilo funcional |
| CP art. 327 | Conceito de funcionário público (alcance ampliado) |
| Lei 12.737/2012 | Crimes informáticos |
| Lei 8.137/1990 | Crimes contra ordem tributária (se dados da Receita) |
| Lei 12.850/2013 | Organização criminosa |
| Lei 9.613/1998 | Lavagem (quando há movimentação estruturada) |
| LGPD art. 42-45 | Responsabilização civil/administrativa + art. 52 (sanções) |
| Lei 13.709/2018 art. 46-49 | Segurança e governança de dados |
| Lei 14.155/2021 | Estelionato eletrônico agravado |

### 27.5 Coordenação Institucional

| Órgão | Papel |
|---|---|
| **Polícia Federal — DICOR/GGI** | Vazamentos em órgãos federais |
| **MPF — GCCC / CAEX** | Cooperação nacional + internacional |
| **PCDF / Polícias Civis estaduais — DRCCs** | Painéis regionais |
| **CGU** | Corregedoria (servidor vazador) |
| **AGU** | Defesa da União quando órgão lesado |
| **ANPD** | Incidentes LGPD (notificação art. 48) |
| **SERPRO / Dataprev / RFB** | Auditoria técnica |
| **Bacen / COAF** | Movimentações financeiras |
| **CGI.br / NIC.br / CERT.br** | Coordenação com infraestrutura internet |

---

## 28. 🆕 Cooperação Internacional

### 28.1 Instrumentos Jurídicos

| Instrumento | Aplicação |
|---|---|
| **Convenção de Budapeste (2001)** | BR aderiu em 2023; cibercrime + cooperação |
| **Rede 24/7 de Budapeste** | Preservação urgente de dados |
| **MLAT BR-EUA (Decreto 3.810/2001)** | Cooperação penal |
| **Acordos de MLAT bilaterais** | Diversos países |
| **Convenção de Palermo (UNTOC)** | Crime organizado transnacional |
| **Convenção de Mérida (UNCAC)** | Corrupção |
| **Acordo de Assistência Jurídica CPLP** | Países lusófonos |
| **DRCI/MJSP** | Autoridade central BR |
| **Tratados extradição** | Variáveis |

### 28.2 Canais Policiais

| Canal | Uso |
|---|---|
| **Interpol I-24/7** | Comunicação policial 24/7 + difusões |
| **Europol SIENA** | UE (via PF) |
| **Ameripol** | Américas |
| **AFP-LEGAT, FBI-LEGAT** | Adidos policiais em embaixadas |
| **Rede Hemisférica OEA** | MLAT Américas |
| **EG-MAC / Egmont Group** | UIF (COAF) intercâmbio |

### 28.3 Portais LEA Globais (reforço da seção 25.5)

Grandes provedores globais mantêm canais para requisições estrangeiras — via MLAT ou diretamente conforme política interna. Consulte sempre os **Transparency Reports** (Meta, Google, Microsoft, Apple, X, TikTok) para políticas atuais.

### 28.4 Fluxograma Simplificado de Pedido Internacional

```
1. Incidente/crime com elemento estrangeiro
2. Identificar dado/evidência necessário
3. Verificar se provedor aceita pedido direto (preservação — MCI/CoE) OU exige MLAT
4. Para preservação urgente: Rede 24/7 Budapeste (via PF/MJSP)
5. Para obtenção de conteúdo: MLAT via DRCI → autoridade central estrangeira
6. Para conteúdo com consentimento do titular: direto ao provedor
7. Para dados abertos: coleta direta documentada
8. Cadeia de custódia + tradução juramentada quando aplicável
```

### 28.5 Transparency Reports Úteis

| Empresa | URL |
|---|---|
| Meta | https://transparency.meta.com/ |
| Google | https://transparencyreport.google.com/ |
| Microsoft | https://www.microsoft.com/corporate-responsibility/law-enforcement-requests-report |
| Apple | https://www.apple.com/legal/transparency/ |
| X/Twitter | https://transparency.x.com/ |
| TikTok | https://www.tiktok.com/transparency |
| Cloudflare | https://www.cloudflare.com/transparency/ |
| Discord | https://discord.com/safety-transparency-reports |
| Telegram | Limitado — apenas ToS |
| Amazon | https://www.amazon.com/gp/help/customer/display.html?nodeId=GYSDRGWQ2C2CRYEF |

---

## 🏁 Encerramento

### Reputação, ética e sustentabilidade da atividade OSINT

Esta base de conhecimento é uma **ferramenta de trabalho profissional**. Seu valor depende de três compromissos:

1. **Legalidade**: toda coleta deve ter base jurídica clara. Dado tecnicamente acessível não equivale a dado legalmente utilizável.
2. **Proporcionalidade**: coletar apenas o necessário, pelo tempo necessário, para a finalidade investigativa legítima.
3. **Cadeia de custódia**: evidência mal preservada é evidência perdida — e investigação comprometida é vítima sem justiça.

### Atualização

OSINT muda semanalmente. Domínios caem, APIs fecham, novas ferramentas surgem. Mantenha hábito de:
- Seguir **Bellingcat**, **OSINT Dojo**, **SANS**, **IntelTechniques**, **Trace Labs**, **OSINT Combine**, **DFRLab**
- Monitorar **CERT.br**, **CTIR Gov**, **ANPD**
- Participar de CTFs OSINT para manter skill
- Revisar este documento periodicamente

### Créditos de metodologia

Este material bebe de fontes como Bellingcat, SANS SEC487/FOR578, Michael Bazzell (IntelTechniques), Trace Labs, OSINT Curious, Nixintel, Sector035 e comunidade brasileira de perícia digital (ABCF, ABFC, peritos federais/estaduais, MPF-GCCC).

---

**Versão**: 3.0
**Idioma**: Português (BR)
**Foco**: Investigação de cibercrimes no Brasil
**Licença de uso**: profissional, com responsabilidade individual do operador
