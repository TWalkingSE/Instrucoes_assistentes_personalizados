# CYBERSHIELD — Base de Conhecimento: Ferramentas de Segurança Digital e Privacidade

> **Versão:** 4.0 | **Atualização:** Abril 2026
> **Fonte primária:** "Proteja-se Online: Dicas e Softwares Essenciais para Sua Segurança Digital" (TWalking, 1ª Edição, Janeiro 2025)
> **Fontes complementares:** PrivacyGuides.org, PrivacyTools.io, EFF, awesome-selfhosted, auditorias independentes, documentação oficial das ferramentas.

---

## ÍNDICE DE CATEGORIAS

1. Gerenciadores de Senhas e 2FA
2. Antivírus e Proteção de Endpoint
3. Backup e Armazenamento em Nuvem
4. Criptografia de Dados
5. Exclusão Segura de Dados
6. VPNs
7. Proxies
8. Rede Tor e Anonimato de Rede
9. Navegadores Seguros (Desktop e Mobile)
10. Motores de Busca Seguros
11. Sistemas Operacionais Seguros
12. Aliases de E-mail
13. Aplicativos de Mensageria Segura
14. Gerenciamento de Metadados
15. Ferramentas Anti-Phishing
16. DNS Seguro e Bloqueio de Rastreadores
17. Segurança de E-mail (Provedores)
18. Criptoativos e Carteiras Seguras
19. Ferramentas OSINT / Sock Puppet
20. Máquinas Virtuais e Isolamento
21. Segurança de Rede Doméstica
22. Privacidade de Fotos e Armazenamento
23. Notificações Push e Telemetria
24. Chaves de Segurança Físicas (Hardware)
25. Transferência Segura de Arquivos
26. Notas e Documentos Criptografados
27. Pastebins Criptografados
28. Clientes de E-mail Seguros
29. Videoconferência e Chamadas Seguras
30. Ferramentas de Teste de Vazamento (Leak Test)
31. Privacidade no Android (Apps e Configuração)
32. Privacidade no iOS
33. Firewalls Pessoais
34. Remoção de Dados Pessoais (Data Brokers)
35. Sincronização de Arquivos (P2P)
36. Calendários e Contatos Seguros
37. Privacidade em IA e LLMs
38. Sandbox e Isolamento de Aplicações
39. Office Suites e Colaboração Privada
40. Editores e Ferramentas de PDF Seguras
41. Tradutores e Ferramentas Linguísticas Privadas
42. Mídia: Streaming, Vídeo e Música Privados
43. Redes Sociais e Microblogging Alternativos
44. Plataformas de Vídeo Alternativas
45. Hospedagem de Código e Colaboração
46. Compartilhamento Seguro de Senhas/Segredos
47. Ferramentas Forenses e Anti-Stalkerware
48. Bloqueadores de Anúncios e Rastreadores (Standalone)
49. Gerenciadores de Cookies e Limpeza de Navegação
50. Mapas, Navegação e Localização Privados
51. Apps de Saúde, Fitness e Período Privados
52. Leitores de Feed (RSS) e Read-It-Later
53. Ofuscação de Tráfego e Anti-Censura
54. Criptografia Pós-Quântica e Ferramentas Avançadas
55. Auditoria de Apps e Análise de Permissões
56. Servidores VPN Auto-Hospedados
57. Honeypots e Detecção de Intrusão Pessoal
58. Compartilhamento de Tela e Acesso Remoto Seguro
59. Gerenciamento de Identidade e SSO Privado
60. Ferramentas de Conscientização e Educação

---

## 1. GERENCIADORES DE SENHAS E 2FA

### [Camada 4 — Aplicação]

### 1.1 Gerenciadores de Senhas

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **Bitwarden** | ✅ Sim | Windows, macOS, Linux, Android, iOS, Web, extensões | Open-source, auto-hospedável (Vaultwarden), plano gratuito robusto, auditado | https://bitwarden.com/ |
| **KeePassXC** | ✅ Sim | Windows, macOS, Linux | 100% offline, base de dados local criptografada (AES-256), sem nuvem | https://keepassxc.org/ |
| **1Password** | ❌ Não | Windows, macOS, Linux, Android, iOS, Web | UX premium, Travel Mode, Watchtower (monitoramento de vazamentos) | https://1password.com/pt |
| **Dashlane** | ❌ Não | Windows, macOS, Android, iOS, Web | VPN integrada, monitoramento de dark web, preenchimento automático avançado | https://www.dashlane.com/ |
| **NordPass** | ❌ Não | Windows, macOS, Linux, Android, iOS | Criptografia XChaCha20, scanner de vazamentos, do grupo Nord Security | https://nordpass.com/ |
| **Proton Pass** | ✅ Sim | Windows, macOS, Linux, Android, iOS, Web | Do ecossistema Proton, aliases de e-mail integrados, E2EE | https://proton.me/pass |
| **LastPass** | ❌ Não | Windows, macOS, Android, iOS, Web | ⚠️ ALERTA: Sofreu vazamento grave em 2022 (cofres criptografados roubados). Uso não recomendado. | https://www.lastpass.com/pt |
| **RoboForm** | ❌ Não | Windows, macOS, Android, iOS | Preenchimento de formulários avançado, plano familiar acessível | https://www.roboform.com/br |
| **Zoho Vault** | ❌ Não | Windows, macOS, Android, iOS, Web | Integração com ecossistema Zoho, gestão de senhas corporativas | https://www.zoho.com/pt-br/vault/ |
| **Vaultwarden** | ✅ Sim | Auto-hospedado (Docker) | Servidor compatível com Bitwarden escrito em Rust, leve, ideal para NAS/Raspberry Pi | https://github.com/dani-garcia/vaultwarden |
| **Psono** | ✅ Sim | Auto-hospedado, Web, extensões | Foco corporativo, compartilhamento granular, auditoria | https://psono.com/ |
| **Passbolt** | ✅ Sim | Auto-hospedado, Web, Desktop, Mobile | Gerenciador de senhas para times, baseado em OpenPGP | https://www.passbolt.com/ |
| **pass (Unix Password Store)** | ✅ Sim | Linux, macOS (CLI) | CLI Unix, GPG + Git, filosofia KISS | https://www.passwordstore.org/ |
| **gopass** | ✅ Sim | Windows, macOS, Linux | Sucessor do `pass` em Go, suporte a múltiplos cofres e equipes | https://www.gopass.pw/ |
| **Enpass** | ❌ Não | Windows, macOS, Linux, Android, iOS | Armazenamento local ou em sua própria nuvem (sem servidor próprio) | https://www.enpass.io/ |
| **Strongbox** | Parcial | macOS, iOS | Compatível com KeePass, integração iCloud/Dropbox | https://strongboxsafe.com/ |
| **KeeWeb** | ✅ Sim | Windows, macOS, Linux, Web | Cliente web/desktop compatível com KeePass | https://keeweb.info/ |

### 1.2 Autenticação de Dois Fatores (2FA)

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **Aegis Authenticator** | ✅ Sim | Android | Backup criptografado, importação de outros apps, interface limpa | https://getaegis.app/ |
| **Ente Auth** | ✅ Sim | Android, iOS, Web, Desktop | Backup E2EE em nuvem, multiplataforma, do mesmo time do Ente Photos | https://ente.io/auth/ |
| **Yubico Authenticator** | ✅ Sim | Windows, macOS, Linux, Android, iOS | Requer chave YubiKey física, TOTP armazenado no hardware | https://www.yubico.com/products/yubico-authenticator/ |
| **Authy** | ❌ Não | Windows, macOS, Linux, Android, iOS | Backup em nuvem, multi-dispositivo. ⚠️ Requer número de telefone, código proprietário | https://authy.com/ |
| **Google Authenticator** | ❌ Não | Android, iOS | Simples e funcional. ⚠️ Backup em nuvem NÃO é E2EE; Google pode acessar os códigos | — |
| **Microsoft Authenticator** | ❌ Não | Android, iOS | Integração com ecossistema Microsoft, login sem senha, backup em nuvem | — |
| **2FAS Auth** | ✅ Sim | Android, iOS, extensões | Backup em nuvem opcional, sincronização entre celular e navegador | https://2fas.com/ |
| **Raivo OTP** | ✅ Sim | iOS, macOS | Backup criptografado iCloud, código aberto | https://raivo-otp.com/ |
| **andOTP** | ✅ Sim | Android | Backup criptografado, descontinuado mas amplamente usado (→ migrar para Aegis) | F-Droid |
| **FreeOTP+** | ✅ Sim | Android | Da Red Hat, simples, com backup e import | F-Droid |
| **Stratum (ex-Cotp)** | ✅ Sim | Android | TOTP/HOTP com sincronização autohospedada opcional | F-Droid |
| **OnlyKey** | ✅ Sim (firmware) | Hardware | Chave hardware com TOTP, senhas e FIDO2 em um único dispositivo | https://onlykey.io/ |

---

## 2. ANTIVÍRUS E PROTEÇÃO DE ENDPOINT

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Diferencial | Alerta de Privacidade |
|---|---|---|---|---|
| **ClamAV** | ✅ Sim | Windows, macOS, Linux | Antivírus open-source, ideal para servidores e scans sob demanda | ✅ Respeita privacidade |
| **Hypatia** | ✅ Sim | Android (via F-Droid) | Scanner de malware baseado em ClamAV para Android | ✅ Respeita privacidade |
| **Windows Defender** | ❌ Não | Windows 10/11 | Integrado ao Windows, proteção em tempo real, sem custo adicional | ⚠️ Telemetria Microsoft |
| **Bitdefender** | ❌ Não | Windows, macOS, Linux, Android, iOS | Excelente detecção, baixo impacto no sistema, VPN e firewall inclusos | ⚠️ Coleta telemetria |
| **Kaspersky** | ❌ Não | Windows, macOS, Linux, Android, iOS | Alta taxa de detecção, VPN e gerenciador de senhas inclusos | ⚠️ Preocupações geopolíticas (empresa russa) |
| **ESET NOD32** | ❌ Não | Windows, macOS, Linux, Android, iOS | Leve, proteção bancária, anti-phishing avançado | ⚠️ Coleta telemetria |
| **Sophos Home** | ❌ Não | Windows, macOS, Android, iOS | Gerenciamento remoto via painel web, protege até 10 dispositivos | ⚠️ Coleta telemetria |
| **Norton 360** | ❌ Não | Windows, macOS, Android, iOS | VPN, backup em nuvem, monitoramento de identidade | ⚠️ Coleta telemetria extensiva |
| **McAfee** | ❌ Não | Windows, macOS, Android, iOS, ChromeOS | Proteção familiar, monitoramento de identidade | ⚠️ Coleta telemetria extensiva |
| **Avast** | ❌ Não | Windows, macOS, Linux, Android, iOS | ⚠️ ALERTA: Multada em US$16,5M pela FTC em 2024 por vender dados de navegação dos usuários. Uso NÃO recomendado. | 🔴 Histórico de venda de dados |
| **Malwarebytes** | ❌ Não | Windows, macOS, Android, iOS | Excelente para remoção de malware/PUPs em modo on-demand, complementa AVs tradicionais | ⚠️ Telemetria moderada |
| **Emsisoft** | ❌ Não | Windows | Dual-engine, anti-ransomware comportamental, foco em PMEs | ⚠️ Telemetria |
| **F-Secure** | ❌ Não | Windows, macOS, Android, iOS | Finlandês, banking protection, VPN inclusa | ⚠️ Telemetria |
| **GData** | ❌ Não | Windows, macOS, Android | Alemão, dual-engine (Bitdefender + próprio), no-backdoor pledge | ⚠️ Telemetria |
| **chkrootkit** | ✅ Sim | Linux, macOS | Detector de rootkits clássico, CLI | ✅ Respeita privacidade |
| **rkhunter** | ✅ Sim | Linux, macOS | Rootkit Hunter, baseline de integridade do sistema | ✅ Respeita privacidade |
| **Lynis** | ✅ Sim | Linux, macOS, BSD | Auditoria de hardening de sistemas, checks de compliance | ✅ Respeita privacidade |
| **YARA** | ✅ Sim | Multi | Engine de regras para identificar malware (usado por SOCs) | ✅ Respeita privacidade |
| **Wazuh** | ✅ Sim | Multi | XDR/SIEM open-source com EDR para endpoints | ✅ Respeita privacidade |

---

## 3. BACKUP E ARMAZENAMENTO EM NUVEM

### [Camada 4 — Aplicação]

### 3.1 Nuvem com Foco em Privacidade

| Ferramenta | Open-Source | E2EE | Armazenamento | Diferencial | Link |
|---|---|---|---|---|---|
| **Proton Drive** | ✅ Sim | ✅ Nativo | 1-500 GB+ | E2EE por padrão, ecossistema Proton, Suíça | https://proton.me/drive |
| **Tresorit** | ❌ Não | ✅ Nativo | 200 GB - 4 TB | E2EE, compliance empresarial, Suíça | https://tresorit.com/ |
| **Sync.com** | ❌ Não | ✅ Nativo | 5 GB grátis, até 6 TB | E2EE, zero-knowledge, Canadá | https://www.sync.com/ |
| **Nextcloud** | ✅ Sim | ✅ (com E2EE plugin) | Auto-hospedado | 100% controle do usuário, auto-hospedável | https://nextcloud.com/ |
| **Cryptomator** | ✅ Sim | ✅ Sim | Complementar | Criptografa arquivos antes de enviar para QUALQUER nuvem (Google Drive, Dropbox, etc.) | https://cryptomator.org/ |
| **Filen** | Parcial | ✅ Nativo | 10 GB grat. – 2 TB | E2EE zero-knowledge, Alemanha, sync e drive virtual | https://filen.io/ |
| **MEGA** | Parcial (cliente) | ✅ Nativo | 20 GB grat. – 16 TB | E2EE com chave do usuário, Nova Zelândia. ⚠️ Histórico controverso (Kim Dotcom) | https://mega.io/ |
| **pCloud** | ❌ Não | ✅ Crypto add-on | 10 GB grat. – 2 TB | Pagamento único (lifetime), pCloud Crypto opcional, Suíça | https://www.pcloud.com/ |
| **Internxt** | ✅ Sim | ✅ Nativo | 10 GB grat. – 2 TB | E2EE zero-knowledge, Espanha, integração com IPFS | https://internxt.com/ |
| **Seafile** | ✅ Sim | ✅ (biblioteca) | Auto-hospedado | Sync confiável para equipes, criptografia de bibliotecas | https://www.seafile.com/ |
| **OwnCloud Infinite Scale** | ✅ Sim | Parcial | Auto-hospedado | Reescrita em Go do OwnCloud clássico | https://owncloud.com/ |

### 3.2 Nuvem Geral (sem E2EE nativo — considerar Cryptomator)

| Ferramenta | Criptografia | Armazenamento Gratuito | Diferencial | Link |
|---|---|---|---|---|
| **Google Drive** | AES-256 em repouso, TLS em trânsito. Sem E2EE. | 15 GB | Integração Google Workspace, histórico 30 dias | https://drive.google.com/ |
| **OneDrive** | AES-256, TLS. Personal Vault com camada extra. Sem E2EE. | 5 GB | Integração Windows/Office 365, recuperação ransomware | https://onedrive.live.com/ |
| **Dropbox** | AES-256, TLS. Sem E2EE. | 2 GB | Smart Sync, integração com Slack e Office | https://www.dropbox.com/pt_BR/ |
| **Backblaze** | AES-256, TLS. E2EE com chave privada (opcional). | Ilimitado (backup) | Custo-benefício excepcional, recuperação física (disco enviado) | https://www.backblaze.com/ |
| **IDrive** | AES-256, TLS. E2EE com chave privada (opcional). | 10 GB | Multi-dispositivo, IDrive Express (envio físico), HIPAA compliant | https://www.idrive.com/ |
| **Acronis True Image** | AES-256, E2EE com chave privada. | — (pago) | Backup híbrido (local+nuvem), clone de disco, anti-ransomware integrado (Active Protection) | https://www.acronis.com/pt-br/products/true-image/ |
| **Carbonite** | AES-128/256, TLS. Chave privada opcional. | — (pago) | Armazenamento ilimitado (planos pessoais), interface simples | https://www.carbonite.com/ |

### 3.3 Backup Local (Software)

| Ferramenta | Open-Source | Plataformas | Diferencial |
|---|---|---|---|
| **BorgBackup** | ✅ Sim | Linux, macOS | Deduplicação, compressão, criptografia AES-256, eficiente para backups incrementais |
| **Restic** | ✅ Sim | Windows, macOS, Linux | Multi-backend (local, S3, SFTP, etc.), criptografia por padrão |
| **Kopia** | ✅ Sim | Windows, macOS, Linux | GUI e CLI, snapshots, criptografia, deduplicação |
| **Duplicati** | ✅ Sim | Windows, macOS, Linux | Interface web, suporte a 20+ backends de nuvem, criptografia AES-256 |
| **Vorta** | ✅ Sim | Windows, macOS, Linux | GUI Qt para BorgBackup, agendamento, snapshots |
| **Pika Backup** | ✅ Sim | Linux | GUI GNOME para BorgBackup, simples para usuários domésticos |
| **Deja Dup** | ✅ Sim | Linux | Frontend GNOME para Duplicity, integrado ao Ubuntu |
| **Time Shift** | ✅ Sim | Linux | Snapshots tipo Time Machine, restauração do sistema |
| **rsync** | ✅ Sim | Linux, macOS, Windows (WSL) | CLI clássico para cópias incrementais, base de muitos scripts |
| **Arq Backup** | ❌ Não | Windows, macOS | Backup criptografado para vários provedores de nuvem, pagamento único |
| **Macrium Reflect** | ❌ Não | Windows | Imagem de disco, backup incremental, versão gratuita |
| **Veeam Agent Free** | ❌ Não | Windows, Linux | Backup empresarial em versão gratuita para uso pessoal |

---

## 4. CRIPTOGRAFIA DE DADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **VeraCrypt** | ✅ Sim | Windows, macOS, Linux | Disco/Volume | Criptografia de disco completo, volumes ocultos (deniable encryption), AES/Twofish/Serpent | https://www.veracrypt.fr/ |
| **Cryptomator** | ✅ Sim | Windows, macOS, Linux, Android, iOS | Arquivos/Nuvem | Criptografa arquivos individuais para nuvem, transparente ao usuário | https://cryptomator.org/ |
| **GnuPG (GPG)** | ✅ Sim | Windows, macOS, Linux | Arquivos/E-mail | Criptografia de e-mail (PGP), assinatura digital, padrão OpenPGP | https://gnupg.org/ |
| **age** | ✅ Sim | Windows, macOS, Linux | Arquivos | Criptografia simples e moderna, substituição do GPG para uso cotidiano | https://age-encryption.org/ |
| **BitLocker** | ❌ Não | Windows 10/11 Pro/Enterprise | Disco | Integrado ao Windows, TPM, criptografia AES-128/256. ⚠️ Chave pode ser enviada para conta Microsoft | — |
| **FileVault** | ❌ Não | macOS | Disco | Criptografia de disco nativa do macOS, XTS-AES-128. ⚠️ Chave pode ser armazenada no iCloud | — |
| **LUKS** | ✅ Sim | Linux | Disco | Padrão de criptografia de disco do Linux, AES-256 | — |
| **AxCrypt** | Parcial | Windows, macOS, Android, iOS | Arquivos | Criptografia de arquivos individuais, integração com cloud. ⚠️ Versão gratuita limitada | https://www.axcrypt.net/ |
| **NordLocker** | ❌ Não | Windows, macOS | Arquivos/Nuvem | Criptografia de arquivos com armazenamento em nuvem E2EE, interface simples | https://nordlocker.com/ |
| **7-Zip** | ✅ Sim | Windows, Linux | Arquivos | Compressão + criptografia AES-256, formato 7z | https://www.7-zip.org/ |
| **Tresorit** | ❌ Não | Windows, macOS, Linux, Android, iOS | Nuvem | Armazenamento em nuvem com E2EE, Suíça | https://tresorit.com/ |
| **Picocrypt** | ✅ Sim | Windows, macOS, Linux | Arquivos | Pequeno (~3 MB), XChaCha20, Argon2id, portátil | https://github.com/Picocrypt/Picocrypt |
| **rage** | ✅ Sim | Multi | Arquivos | Implementação em Rust de `age`, suporte a YubiKey | https://github.com/str4d/rage |
| **Kleopatra** | ✅ Sim | Windows, Linux | Chaves PGP/X.509 | GUI para GnuPG, gestão de chaves, cifragem de e-mail | https://www.openpgp.org/software/kleopatra/ |
| **Sequoia PGP** | ✅ Sim | Multi | OpenPGP | Implementação moderna de OpenPGP em Rust | https://sequoia-pgp.org/ |
| **OpenSSL** | ✅ Sim | Multi | Toolkit | Criptografia de arquivos via CLI (`openssl enc`), TLS, certs | https://www.openssl.org/ |
| **Hat.sh** | ✅ Sim | Web | Arquivos | Criptografia client-side no navegador (XChaCha20-Poly1305) | https://hat.sh/ |
| **Tomb** | ✅ Sim | Linux | Volume | Wrapper de LUKS para criar “túmulos” criptografados portáteis | https://www.dyne.org/software/tomb/ |
| **gocryptfs** | ✅ Sim | Linux, macOS | Sistema de arquivos | Filesystem criptografado em userspace, AES-GCM | https://nuetzlich.net/gocryptfs/ |
| **EncFS** | ✅ Sim | Linux, macOS, Windows | Sistema de arquivos | Filesystem criptografado em userspace (⚠️ auditoria 2014 apontou fraquezas) | https://vgough.github.io/encfs/ |

---

## 5. EXCLUSÃO SEGURA DE DADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **BleachBit** | ✅ Sim | Windows, Linux | Arquivos/Sistema | Limpeza de sistema + exclusão segura, padrões Gutmann/DoD | https://www.bleachbit.org/ |
| **Eraser** | ✅ Sim | Windows | Arquivos/Disco | Exclusão segura com agendamento, múltiplos algoritmos (Gutmann, DoD 5220.22-M) | https://eraser.heidi.ie/ |
| **DBAN (Darik's Boot and Nuke)** | ✅ Sim | Boot (qualquer SO) | Disco completo | Apagamento total de disco via boot, ideal para descarte de hardware | https://dban.org/ |
| **shred** | ✅ Sim | Linux/macOS | Arquivos | Comando nativo do Linux para sobrescrita segura de arquivos | — (nativo) |
| **secure-delete (srm)** | ✅ Sim | Linux | Arquivos/Disco | Suite com srm, sfill, sswap, smem para exclusão segura | — |
| **BCWipe** | ❌ Não | Windows | Arquivos/Disco | Apagamento certificado (DoD, NIST), logs de auditoria para compliance | https://www.jetico.com/ |
| **Secure Eraser** | ❌ Não | Windows | Arquivos/Disco | Apagamento seguro com 5 métodos, limpeza de registro e espaço livre | https://www.ascompsoftware.com/ |
| **CCleaner (Wipe)** | ❌ Não | Windows, macOS | Arquivos/Sistema | Limpeza de sistema + exclusão segura (1-35 passagens). ⚠️ Histórico de bundleware | https://www.ccleaner.com/pt-br |
| **WipeFile** | ❌ Não | Windows | Arquivos | Leve, portátil, 14 métodos de apagamento | https://www.gaijin.at/en/software/wipefile |
| **File Shredder** | ❌ Não | Windows | Arquivos | Gratuito, 5 algoritmos de sobrescrita, integração com menu de contexto | https://www.fileshredder.org/ |
| **nwipe** | ✅ Sim | Linux | Disco | Sucessor open-source do DBAN, múltiplos métodos (DoD, Gutmann, PRNG) | https://github.com/martijnvanbrummelen/nwipe |
| **ShredOS** | ✅ Sim | Boot | Disco | Distribuição mínima focada em rodar `nwipe` | https://github.com/PartialVolume/shredos.x86_64 |
| **HDDErase** | ✅ Sim | Boot | Disco/SSD | Usa comando ATA Secure Erase nativo (ideal para SSDs) | — |
| **Parted Magic** | ❌ Não | Boot | Disco/SSD | Conjunto profissional com Secure Erase para SSDs e HDDs | https://partedmagic.com/ |
| **Blancco Drive Eraser** | ❌ Não | Boot/Live | Disco | Padrão corporativo certificado (NIST, DoD), relatórios auditáveis | https://www.blancco.com/ |

---

## 6. VPNs

### [Camada 3 — Transporte]

| VPN | Open-Source | Jurisdição | No-Log Auditado | Protocolo Principal | Servidores | Dispositivos Simultâneos | Preço Mensal | Diferencial | Link |
|---|---|---|---|---|---|---|---|---|---|
| **Mullvad VPN** | ✅ Sim | Suécia | ✅ (auditoria independente) | WireGuard | ~800 / 39 países | 5 | €5/mês fixo | Registro anônimo (sem e-mail), aceita Monero e dinheiro por correio. Busca policial em 2023 não encontrou dados. | https://mullvad.net/pt |
| **ProtonVPN** | ✅ Sim | Suíça | ✅ (auditoria independente) | WireGuard/OpenVPN | ~2.900 / 65 países | 1-10 | Gratuito - €9,99 | Secure Core (multi-hop), Tor sobre VPN, NetShield (bloqueador), plano gratuito sem limite de dados | https://protonvpn.com/pt-br |
| **IVPN** | ✅ Sim | Gibraltar | ✅ (auditoria independente) | WireGuard/OpenVPN | ~90 / 30+ países | 7 | ~$6/mês | Multi-hop, AntiTracker, registro anônimo, aceita Monero | https://www.ivpn.net |
| **NordVPN** | ❌ Não | Panamá | ✅ (PwC) | NordLynx (WireGuard) | ~5.800 / 60 países | 6 | ~$3-12/mês | Double VPN, Threat Protection (bloqueio malware/anúncios), grande rede. ⚠️ Incidente em datacenter Finlândia 2018 (sem dados comprometidos). | https://nordvpn.com/pt-br/ |
| **ExpressVPN** | ❌ Não | Ilhas Virgens Britânicas | ✅ (PwC, KPMG) | Lightway | ~3.000 / 94 países | 5 | ~$6-13/mês | TrustedServer (RAM-only), velocidade premium. ⚠️ Adquirida pela Kape Technologies (2021). Vazamento DNS com split tunneling (2022-2024, corrigido). | https://www.expressvpn.com/pt |
| **Surfshark** | ❌ Não | Ilhas Virgens Britânicas → Holanda | ✅ (Deloitte, Cure53) | WireGuard | ~3.200 / 100 países | Ilimitado | ~$2-13/mês | Dispositivos ilimitados, CleanWeb, MultiHop, Rotating IP, Camouflage Mode | https://surfshark.com/pt-br |
| **Private Internet Access (PIA)** | ✅ Sim (cliente) | EUA | Parcial (Deloitte 2020) | WireGuard/OpenVPN | ~35.000 / 78 países | 10 | ~$2-12/mês | Maior rede de servidores, PIA MACE (bloqueador), no-logs comprovado em tribunal (2015, 2016). ⚠️ Sede nos EUA (5 Eyes). | https://www.privateinternetaccess.com/pt/ |
| **Windscribe** | ✅ Sim (cliente) | Canadá | Parcial | WireGuard/OpenVPN | ~480 / 69 países | Ilimitado | Grat. 10 GB/mês – ~$5,75/mês | R.O.B.E.R.T. (firewall DNS), Build-a-Plan, plano grat. generoso | https://windscribe.com/ |
| **AirVPN** | ✅ Sim (cliente) | Itália | Não auditado público | OpenVPN/WireGuard | ~250 / 23 países | 5 | ~€3-7/mês | Operada por ativistas, port forwarding, aceita cripto, transparência em tempo real | https://airvpn.org/ |
| **TorGuard** | ❌ Não | EUA | Parcial | WireGuard/OpenVPN | ~3.000 / 50 países | 8 | ~$5-10/mês | Foco em P2P, IPs dedicados | https://torguard.net/ |
| **OVPN** | Parcial | Suécia | ✅ Auditado | WireGuard/OpenVPN | ~110 / 29 países | 4-7 | ~$4-11/mês | Servidores RAM-only de propriedade própria, transparência legal | https://www.ovpn.com/ |
| **Hide.me** | Parcial | Malásia | ✅ Auditado | WireGuard/OpenVPN | ~2.400 / 90+ países | 10 | Grat. 10 GB – ~$5/mês | Plano grat. sem publicidade, kill switch | https://hide.me/ |
| **CyberGhost** | ❌ Não | Romênia | Parcial | WireGuard/OpenVPN | ~11.000 / 100 países | 7 | ~$2-13/mês | Servidores otimizados para streaming. ⚠️ Também do grupo Kape | https://www.cyberghostvpn.com/ |
| **TunnelBear** | ❌ Não | Canadá | ✅ Auditado | OpenVPN/IKEv2 | ~5.000 / 47 países | Ilimitado | Grat. 2 GB – ~$3-10/mês | Interface amigável para iniciantes (do grupo McAfee desde 2018) | https://www.tunnelbear.com/ |

### 6.1 Clientes VPN Open-Source (multi-protocolo)

| Cliente | Plataformas | Diferencial |
|---|---|---|
| **WireGuard (oficial)** | Multi | Cliente referência, leve, ideal para perfis manuais |
| **OpenVPN Connect** | Multi | Cliente oficial OpenVPN |
| **Tunnelblick** | macOS | GUI OpenVPN gratuita para macOS |
| **Viscosity** | Windows, macOS | OpenVPN profissional, pagamento único |
| **WG Easy** | Auto-hospedado | UI web para gerenciar peers WireGuard |

---

## 7. PROXIES

### [Camada 2 — Internet / Camada 3 — Transporte]

### 7.1 Proxies Pagos (mais seguros)

| Serviço | Tipo | Diferencial |
|---|---|---|
| **Smartproxy** | Residencial/Datacenter | Velocidade e confiabilidade, pool grande de IPs |
| **Oxylabs** | Residencial/Datacenter | Criptografia forte, APIs avançadas |
| **Bright Data** (ex-Luminati) | Residencial/Datacenter/Móvel | Recursos avançados de segurança, grande escala |
| **IPRoyal** | Residencial | Foco em privacidade |

### 7.2 Proxies Gratuitos (uso limitado)

| Serviço | Tipo | Observação |
|---|---|---|
| **Hide.me** | Web proxy | Versão gratuita limitada, boa reputação |
| **VPNBook** | Web proxy | Gratuito, sem registro |
| **HMA (HideMyAss)** | Web proxy | Opção gratuita de proxy web. ⚠️ Histórico controverso (logs entregues a autoridades) |

> ⚠️ **ATENÇÃO:** Proxies NÃO criptografam dados. Use apenas para contornar restrições geográficas, NUNCA para anonimato. Para proteção real, use VPN ou Tor.

---

## 8. REDE TOR E ANONIMATO DE REDE

### [Camada 2 — Internet]

| Ferramenta | Tipo | Diferencial |
|---|---|---|
| **Tor Browser** | Navegador | Navegação anônima via onion routing, 3 saltos, resistente a fingerprinting | https://www.torproject.org/ |
| **Tor Bridges** | Infraestrutura | Relays não listados para contornar bloqueio do Tor em países com censura |
| **Snowflake** | Transporte plugável | Transforma navegadores de voluntários em proxies de acesso ao Tor |
| **I2P** | Rede de anonimato | Alternativa ao Tor, focada em serviços internos (eepsites), garlic routing | https://geti2p.net/ |
| **Lokinet** | Rede de anonimato | Onion routing baseado em LLARP da Oxen, suporta qualquer protocolo IP | https://lokinet.org/ |
| **Freenet/Hyphanet** | Rede de anonimato | Datastore P2P resistente à censura | https://www.hyphanet.org/ |
| **ZeroNet** | Rede descentralizada | Sites P2P usando Bitcoin/BitTorrent (⚠️ manutenção irregular) | https://zeronet.io/ |
| **Yggdrasil** | Mesh network IPv6 | Rede mesh criptografada e auto-organizável | https://yggdrasil-network.github.io/ |
| **cwtch** | Mensagens via Tor | Mensageria P2P metadata-resistant via Tor | https://cwtch.im/ |
| **Orbot** | Cliente Tor (mobile/desktop) | Roteia tráfego de apps específicos via Tor | https://orbot.app/ |
| **Onion Browser (iOS)** | Navegador Tor | Navegador oficial Tor para iOS | https://onionbrowser.com/ |
| **obfs4 / meek / WebTunnel** | Pluggable transports | Disfarçam tráfego Tor para evitar DPI/censura |

---

## 9. NAVEGADORES SEGUROS

### [Camada 4 — Aplicação]

### 9.1 Desktop

| Navegador | Open-Source | Motor | Diferencial | Link |
|---|---|---|---|---|
| **Tor Browser** | ✅ Sim | Firefox/Gecko | Máximo anonimato via rede Tor, anti-fingerprinting uniforme | https://www.torproject.org/ |
| **Mullvad Browser** | ✅ Sim | Firefox/Gecko | Baseado no Tor Browser SEM Tor, anti-fingerprinting máximo, uso com Mullvad VPN | https://mullvad.net/en/browser/ |
| **LibreWolf** | ✅ Sim | Firefox/Gecko | Firefox sem telemetria, pré-configurado para privacidade, uBlock Origin incluído | https://librewolf.net |
| **Firefox** (hardened) | ✅ Sim | Gecko | Com Arkenfox user.js: anti-fingerprinting, sem telemetria. Configuração manual necessária. | https://www.mozilla.org/firefox |
| **Brave** | ✅ Sim | Chromium/Blink | Bloqueio nativo de anúncios/rastreadores, anti-fingerprinting. ⚠️ Incidente links de afiliado (2020, corrigido). BAT/Rewards opcional. | https://brave.com |
| **Ungoogled Chromium** | ✅ Sim | Chromium/Blink | Chromium sem conexões Google, sem telemetria, sem auto-update Google | https://ungoogled-software.github.io/ |
| **DuckDuckGo Privacy Browser** | ✅ Sim | WebKit | Foco em privacidade, bloqueio de rastreadores, Fire Button (limpar tudo). ⚠️ Exceção Microsoft Advertising (2022, mitigado). | https://duckduckgo.com/app |
| **Epic Browser** | ❌ Não | Chromium/Blink | Proxy embutido, sem histórico/cache por padrão, bloqueia fingerprinting | https://www.epicbrowser.com |
| **Waterfox** | ✅ Sim | Gecko | Fork de Firefox sem telemetria, suporte a extensões legacy | https://www.waterfox.net/ |
| **IceCat** | ✅ Sim | Gecko | Versão GNU do Firefox, 100% software livre | https://www.gnu.org/software/gnuzilla/ |
| **Pale Moon** | ✅ Sim | Goanna (fork Gecko) | Foco em customização e desempenho, motor próprio | https://www.palemoon.org/ |
| **Vivaldi** | Parcial | Chromium/Blink | Altamente customizável, bloqueador embutido. ⚠️ UI proprietária | https://vivaldi.com/ |
| **Thorium** | ✅ Sim | Chromium | Chromium otimizado para velocidade e privacidade | https://thorium.rocks/ |
| **Zen Browser** | ✅ Sim | Gecko | Fork moderno de Firefox com workspaces e UI redesenhada | https://zen-browser.app/ |
| **Floorp** | ✅ Sim | Gecko | Firefox com foco em customização, mantido no Japão | https://floorp.app/ |

### 9.2 Mobile (Android)

| Navegador | Diferencial |
|---|---|
| **Tor Browser** | Anonimato máximo via rede Tor |
| **Brave** | Bloqueio nativo de anúncios e rastreadores |
| **Firefox Focus** | Apaga automaticamente o histórico ao sair, bloqueia rastreadores |
| **Bromite** | Chromium com bloqueio de anúncios e anti-fingerprinting (descontinuado → ver Cromite) |
| **Cromite** | Fork do Bromite, manutenção ativa |
| **Mull** | Firefox com configurações de privacidade reforçadas (via DivestOS) |
| **IronFox** | Sucessor do Mull (descontinuado), Firefox endurecido para Android | https://gitlab.com/ironfox-oss/IronFox |
| **Vanadium** | Navegador Chromium endurecido nativo do GrapheneOS |
| **DuckDuckGo Browser (mobile)** | App tudo-em-um com Fire Button e bloqueio de rastreadores |
| **Privacy Browser** | Foco em controle granular de cookies, JavaScript e DOM Storage | https://www.stoutner.com/privacy-browser/ |

### 9.3 Extensões Essenciais para Navegadores

| Extensão | Função | Navegadores |
|---|---|---|
| **uBlock Origin** | Bloqueador de anúncios e rastreadores (FOSS) | Firefox, Chrome, Edge |
| **NoScript** | Bloqueia JavaScript por padrão (whitelist) | Firefox |
| **Canvas Blocker** | Protege contra Canvas fingerprinting | Firefox |
| **HTTPS Everywhere** | Força HTTPS (integrado em muitos navegadores modernos) | Firefox, Chrome |
| **DuckDuckGo Privacy Essentials** | Bloqueio de rastreadores + nota de privacidade | Firefox, Chrome, Edge |
| **Privacy Badger (EFF)** | Bloqueio heurístico de rastreadores baseado em comportamento | Firefox, Chrome, Edge |
| **ClearURLs** | Remove parâmetros de tracking de URLs (utm_, fbclid, etc.) | Firefox, Chrome |
| **Decentraleyes** | Hospeda CDNs localmente para evitar conexões a Google/Cloudflare | Firefox, Chrome |
| **LocalCDN** | Sucessor mais ativo do Decentraleyes | Firefox, Chrome |
| **Cookie AutoDelete** | Apaga cookies ao fechar abas, exceções por domínio | Firefox, Chrome |
| **Multi-Account Containers** | Isola cookies por container (Firefox) | Firefox |
| **Temporary Containers** | Cria container descartável para cada aba | Firefox |
| **Skip Redirect** | Pula redirecionamentos intermediários de tracking | Firefox |
| **SponsorBlock** | Pula trechos patrocinados em vídeos do YouTube | Multi |
| **Snowflake (extensão)** | Transforma seu navegador em proxy para usuários Tor censurados | Firefox, Chrome |
| **JShelter** | Restringe APIs JavaScript usadas para fingerprinting | Firefox, Chrome |
| **CanvasBlocker** | Bloqueia/aleatoriza Canvas fingerprint | Firefox |
| **User-Agent Switcher** | Muda User-Agent para reduzir fingerprint único | Firefox, Chrome |
| **Bitwarden / KeePassXC-Browser** | Auto-fill seguro do gerenciador de senhas | Multi |

### 9.4 Ferramentas de Teste de Fingerprinting

| Ferramenta | Função | Link |
|---|---|---|
| **AmIUnique** | Mostra quão único é seu navegador | https://amiunique.org |
| **BrowserLeaks** | Teste detalhado de vazamentos (WebRTC, Canvas, WebGL, AudioContext) | https://browserleaks.com |
| **Cover Your Tracks (EFF)** | Teste de rastreabilidade do navegador | https://coveryourtracks.eff.org |
| **CreepJS** | Detecção avançada de fingerprinting e spoofing | https://abrahamjuliot.github.io/creepjs/ |
| **DeviceInfo** | Informações detalhadas sobre seu dispositivo/navegador | https://www.deviceinfo.me |

### 9.5 Ferramentas de Segurança Web Geral

| Ferramenta | Função | Link |
|---|---|---|
| **Qualys SSL Labs** | Testa configurações SSL/TLS de servidores | https://www.ssllabs.com/ssltest |
| **Mozilla Observatory** | Análise de segurança de websites | https://observatory.mozilla.org |
| **GoLogin** | Gerenciamento de múltiplos perfis de navegador (anti-fingerprinting) | https://gologin.com |
| **BrowserScan** | Scanner de segurança de navegador | https://browserscan.net |

---

## 10. MOTORES DE BUSCA SEGUROS

### [Camada 4 — Aplicação]

| Motor | Índice Próprio | Jurisdição | Diferencial | Link |
|---|---|---|---|---|
| **DuckDuckGo** | Parcial (usa Bing) | EUA | Mais popular, sem rastreamento, bangs (!g, !w). ⚠️ Exceção Microsoft (2022, mitigada). | https://duckduckgo.com/ |
| **Startpage** | Não (usa Google) | Holanda | Resultados do Google sem rastreamento, modo de visualização anônima | https://www.startpage.com/ |
| **Brave Search** | ✅ Sim | EUA | Índice independente, sem dependência de Google/Bing, Goggles (filtros personalizáveis) | https://search.brave.com |
| **SearXNG** | Meta-busca | Auto-hospedável | Open-source, descentralizado, combina resultados de múltiplos motores, sem rastreamento | https://docs.searxng.org/ |
| **Mojeek** | ✅ Sim | Reino Unido | Índice 100% próprio, sem rastreamento, crawlers independentes | https://www.mojeek.com/ |
| **Qwant** | Parcial (usa Bing) | França | Sediado na UE, conformidade GDPR, sem personalização | https://www.qwant.com/ |
| **MetaGer** | Meta-busca | Alemanha | Organização sem fins lucrativos, visualização anônima de resultados, GDPR | https://metager.org |
| **Swisscows** | Parcial (usa Bing) | Suíça | Filtro de conteúdo adulto, foco familiar, leis de privacidade suíças | https://swisscows.com |
| **Ecosia** | Não (usa Bing) | Alemanha | Planta árvores com receita de anúncios, política de privacidade razoável | https://www.ecosia.org |
| **Oscobo** | Não (usa Bing/Yahoo) | Reino Unido | Sem rastreamento, sem personalização | https://www.oscobo.com |
| **Disconnect Search** | Meta-busca | EUA | Redireciona consultas anonimizadas para Google/Bing/Yahoo | https://search.disconnect.me |
| **Kagi** | ✅ Sim | EUA | Pago, sem anúncios, lenses, IA opcional, bloqueio de domínios | https://kagi.com/ |
| **Whoogle Search** | Meta-busca | Auto-hospedado | Resultados Google sem JS, sem IP do usuário, FOSS | https://github.com/benbusby/whoogle-search |
| **You.com** | ✅ Sim | EUA | IA + busca, modo privado | https://you.com/ |
| **Presearch** | ✅ Sim | Canadá | Descentralizado, recompensa em token PRE | https://presearch.com/ |
| **YaCy** | Meta-busca P2P | Auto-hospedado | Motor descentralizado P2P, cada nó é um crawler | https://yacy.net/ |
| **4get** | Meta-busca | Auto-hospedado | Front-end leve para Google, Bing, etc., sem JS | https://4get.ca/ |
| **LibreY** | Meta-busca | Auto-hospedado | Fork ativo do antigo LibreX | https://github.com/Ahwxorg/LibreY |

---

## 11. SISTEMAS OPERACIONAIS SEGUROS

### [Transversal — Múltiplas Camadas]

| SO | Open-Source | Base | Nível | Diferencial |
|---|---|---|---|---|
| **Tails** | ✅ Sim | Debian | Avançado | Live OS que roda de USB, roteia TODO tráfego via Tor, amnésico (sem rastros), criptografia LUKS |
| **Whonix** | ✅ Sim | Debian | Avançado | VM dupla (Gateway + Workstation), anonimato via Tor, isolamento de rede por design |
| **Qubes OS** | ✅ Sim | Xen hypervisor | Avançado | Segurança por compartimentalização (qubes/VMs isoladas), integração Whonix |
| **GrapheneOS** | ✅ Sim | AOSP | Avançado | Android sem Google, hardened, perfis isolados, apenas para Pixel |
| **CalyxOS** | ✅ Sim | AOSP | Intermediário | Android com microG (compatibilidade Google limitada), Datura Firewall |
| **LineageOS** | ✅ Sim | AOSP | Intermediário | Android custom ROM, ampla compatibilidade de dispositivos, sem Google |
| **Linux (geral)** | ✅ Sim | Variado | Todos | Open-source, customizável, AppArmor/SELinux, sem telemetria. Distribuições recomendadas: Fedora, Debian, Arch |
| **OpenBSD** | ✅ Sim | BSD | Avançado | Segurança por padrão, código auditado, criptografia forte, ASLR avançado |
| **Kicksecure** | ✅ Sim | Debian | Intermediário | Base do Whonix, hardening Debian sem necessariamente usar Tor |
| **Qubes-Whonix** | ✅ Sim | Xen + Debian | Avançado | Whonix rodando como qubes dentro do Qubes OS (combo máximo) |
| **DivestOS** | ✅ Sim | LineageOS fork | Intermediário | Android focado em privacidade para dispositivos antigos |
| **/e/OS** | ✅ Sim | LineageOS fork | Intermediário | Android desgooglificado com serviços Murena (alternativa amigável) |
| **iodeOS** | ✅ Sim | LineageOS fork | Intermediário | Foca em bloqueio de rastreadores em nível de sistema |
| **PureOS** | ✅ Sim | Debian | Intermediário | SO da Purism (Librem 5), endossado pela FSF |
| **postmarketOS** | ✅ Sim | Alpine | Avançado | Linux real para celulares (suporte 10+ anos por dispositivo) |
| **Parrot Security OS** | ✅ Sim | Debian | Avançado | Pentesting + privacidade, modo anonsurf integrado |
| **Kodachi** | ✅ Sim | Debian | Avançado | Live OS focado em anonimato, VPN+Tor+DNSCrypt encadeados |
| **Subgraph OS** | ✅ Sim | Debian | Avançado | Sandboxing por aplicação (Oz), kernel hardening (Grsecurity) |
| **Heads** | ✅ Sim | Debian | Avançado | Alternativa libre a Tails (sem blobs) |
| **Septor** | ✅ Sim | Debian | Intermediário | KDE + Tor por padrão, alternativa polõo ao Tails |
| **Alpine Linux** | ✅ Sim | musl/BusyBox | Avançado | Mínimo, hardened (PaX/grsec histórico), popular em containers |

---

## 12. ALIASES DE E-MAIL

### [Camada 4 — Aplicação]

| Serviço | Open-Source | Plano Gratuito | Diferencial | Link |
|---|---|---|---|---|
| **SimpleLogin** | ✅ Sim | 10 aliases | Open-source, integrado ao Proton Mail, auto-hospedável | https://simplelogin.io/ |
| **addy.io** (ex-AnonAddy) | ✅ Sim | Ilimitado (subdomínio) | Open-source, auto-hospedável, aliases ilimitados no plano gratuito (com domínio compartilhado) | https://addy.io/ |
| **Firefox Relay** | ✅ Sim | 5 aliases | Integração com Firefox, da Mozilla | https://relay.firefox.com/ |
| **Apple Hide My Email** | ❌ Não | Com iCloud+ | Integrado ao ecossistema Apple, gera aliases aleatórios | — |
| **SpamGourmet** | ✅ Sim | Gratuito | Aliases auto-destrutivos (limita quantidade de e-mails recebidos), minimalista | https://www.spamgourmet.com/ |
| **DuckDuckGo Email Protection** | ❌ Não | Gratuito | Aliases @duck.com, remove rastreadores de e-mail antes de encaminhar | https://duckduckgo.com/email |
| **Erine.email** | ✅ Sim | Gratuito | Aliases descartáveis com base em desafios de prova | https://erine.email/ |
| **Forward Email** | ✅ Sim | Grat. + pago | Forwarding criptografado, auto-hospedado, suporta domínio próprio | https://forwardemail.net/ |
| **33mail** | ❌ Não | Gratuito | Subdomínio grátis, ilimitados aliases | https://33mail.com/ |
| **EmailOnDeck** | ❌ Não | Gratuito | E-mails temporários (10 minutos), sem cadastro | https://www.emailondeck.com/ |
| **Mail.tm** | ❌ Não | Gratuito | Mailbox temporária com API pública | https://mail.tm/ |
| **Guerrilla Mail** | ❌ Não | Gratuito | Mailbox descartável clássica (1h) | https://www.guerrillamail.com/ |

---

## 13. APLICATIVOS DE MENSAGERIA SEGURA

### [Camada 4 — Aplicação]

| App | Open-Source | E2EE | Registro | Diferencial | Link |
|---|---|---|---|---|---|
| **Signal** | ✅ Sim | ✅ Padrão | Número de telefone | Padrão-ouro de E2EE (protocolo Signal), metadados mínimos, sealed sender | https://signal.org/ |
| **SimpleX Chat** | ✅ Sim | ✅ Padrão | Sem identificador | SEM identificador de usuário (nem número, nem username), descentralizável, metadados mínimos | https://simplex.chat/ |
| **Session** | ✅ Sim | ✅ Padrão | Session ID (sem telefone) | Rede descentralizada (Oxen), onion routing, sem número de telefone | https://getsession.org/ |
| **Briar** | ✅ Sim | ✅ Padrão | Sem servidor central | P2P via Tor/Wi-Fi/Bluetooth, funciona sem internet, ideal para ativistas | https://briarproject.org/ |
| **Element (Matrix)** | ✅ Sim | ✅ (Megolm) | Conta Matrix | Protocolo federado (Matrix), auto-hospedável, rooms criptografadas | https://element.io/ |
| **Wire** | ✅ Sim | ✅ Padrão | E-mail ou telefone | E2EE por padrão, foco corporativo, Suíça. ⚠️ Armazena metadados (quem fala com quem). | https://wire.com/ |
| **Threema** | ✅ Sim (cliente) | ✅ Padrão | Threema ID (sem telefone) | Suíça, sem número de telefone obrigatório, pago (sem modelo de anúncios) | https://threema.ch/ |
| **Telegram** | Parcial (cliente) | ⚠️ Apenas Secret Chats | Número de telefone | Chats normais NÃO são E2EE. Secret Chats são E2EE mas não sincronizam entre dispositivos. ⚠️ Servidor proprietário. | https://telegram.org/ |
| **WhatsApp** | ❌ Não | ✅ (Signal protocol) | Número de telefone | E2EE em mensagens e chamadas, mas backups em iCloud/Drive nem sempre são E2EE; metadados extensos coletados pela Meta | https://whatsapp.com/ |
| **Molly** | ✅ Sim | ✅ Padrão | Número de telefone | Fork hardened do Signal para Android (cofre criptografado, bloqueio biométrico) | https://molly.im/ |
| **DeltaChat** | ✅ Sim | ✅ (Autocrypt) | E-mail | Mensageria sobre IMAP/SMTP com PGP automático (Autocrypt), usa qualquer provedor de e-mail | https://delta.chat/ |
| **Status** | ✅ Sim | ✅ Padrão | Chave Ethereum | Mensageria descentralizada, integração com carteira ETH, P2P via Whisper | https://status.app/ |
| **Berty** | ✅ Sim | ✅ Padrão | Sem identificador | Mensageria P2P sem servidores, BLE/Wi-Fi/Internet | https://berty.tech/ |
| **Jami** | ✅ Sim | ✅ Padrão | Sem servidor central | Mensageria/chamadas P2P (DHT OpenDHT), GNU project | https://jami.net/ |
| **Cwtch** | ✅ Sim | ✅ Padrão | Sem identificador | Mensageria metadata-resistant via Tor onion services | https://cwtch.im/ |
| **XMPP (Conversations, Gajim, Dino)** | ✅ Sim | ✅ (OMEMO) | JID | Protocolo federado XMPP com OMEMO E2EE | https://conversations.im/ |
| **Mattermost** | ✅ Sim | Parcial | Conta em servidor | Slack open-source, auto-hospedado, ideal para equipes | https://mattermost.com/ |
| **Rocket.Chat** | ✅ Sim | Parcial | Conta em servidor | Slack open-source, federação EE, auto-hospedado | https://www.rocket.chat/ |
| **Revolt** | ✅ Sim | ❌ | Conta | Alternativa FOSS ao Discord, em desenvolvimento | https://revolt.chat/ |

---

## 14. GERENCIAMENTO DE METADADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **ExifTool** | ✅ Sim | Windows, macOS, Linux | CLI | Padrão da indústria, lê/edita metadados de 400+ formatos de arquivo | https://exiftool.org/ |
| **mat2** | ✅ Sim | Linux | CLI | Remove metadados de imagens, documentos, áudio, vídeo | https://0xacab.org/jfrber/mat2 |
| **Scrambled Exif** | ✅ Sim | Android | App | Remove metadados de fotos antes de compartilhar | F-Droid |
| **Metapho** | ❌ Não | iOS | App | Visualiza e remove metadados de fotos no iPhone | App Store |
| **ImageOptim** | ✅ Sim | macOS | App | Otimiza imagens removendo metadados e comprimindo | https://imageoptim.com/ |
| **GIMP** | ✅ Sim | Windows, macOS, Linux | Editor | Editor de imagem completo, permite remover/editar metadados ao exportar | https://www.gimp.org/ |
| **MetaCleaner** | ❌ Não | Web | Web | Limpeza de metadados online (PDF, imagens, Office) | https://www.metacleaner.com/ |
| **PDF Metadata Editor** | ✅ Sim | Multi | Desktop | Edita metadados de PDFs em batch | https://broken-by.me/pdf-metadata-editor/ |
| **jhead** | ✅ Sim | Multi (CLI) | CLI | Visualiza/edita EXIF de JPEGs | https://www.sentex.ca/~mwandel/jhead/ |
| **MediaInfo** | ✅ Sim | Multi | Desktop/CLI | Análise técnica de vídeo/áudio (codecs, metadados) | https://mediaarea.net/MediaInfo |
| **mat2 web** | ✅ Sim | Web | Web | Versão web auto-hospedada do mat2 | https://0xacab.org/jvoisin/mat2-web |

---

## 15. FERRAMENTAS ANTI-PHISHING

### [Camada 4 — Aplicação]

| Ferramenta | Tipo | Diferencial | Link |
|---|---|---|---|
| **VirusTotal** | Scanner de URL/arquivo | Analisa URLs e arquivos contra 70+ engines antivírus | https://www.virustotal.com/ |
| **PhishTank** | Base de dados colaborativa | Comunidade que reporta e verifica sites de phishing | https://phishtank.org/ |
| **URLVoid** | Verificador de reputação | Analisa URLs contra 30+ fontes de blacklist | https://www.urlvoid.com/ |
| **dnstwist** | Detector de typosquatting | Identifica domínios similares usados para phishing | https://dnstwist.it/ |
| **Google Phishing Quiz** | Educacional | Treinamento interativo para reconhecer phishing | https://phishingquiz.withgoogle.com/ |
| **Phishing.org** | Educacional | Recursos e alertas sobre ataques de phishing | https://www.phishing.org/ |
| **LeilãoSeguro** | Verificação de comércio | Verificação de segurança de sites de leilão/e-commerce (Brasil) | https://www.leilaoseguro.org.br/ |

---

## 16. DNS SEGURO E BLOQUEIO DE RASTREADORES

### [Camada 4 — Aplicação / Camada 2 — Internet]

### 16.1 Provedores DNS Criptografados

| Provedor | DoH | DoT | DNSSEC | Diferencial |
|---|---|---|---|---|
| **Quad9** (9.9.9.9) | ✅ | ✅ | ✅ | Sem fins lucrativos, bloqueio de malware, Suíça |
| **Cloudflare** (1.1.1.1) | ✅ | ✅ | ✅ | Rápido, auditado, opção family (1.1.1.3) |
| **Mullvad DNS** | ✅ | ✅ | ✅ | Bloqueio de anúncios/rastreadores, sem log |
| **NextDNS** | ✅ | ✅ | ✅ | Customizável, listas de bloqueio, logs opcionais |
| **AdGuard DNS** | ✅ | ✅ | ✅ | Bloqueio de anúncios/rastreadores integrado |
| **dns0.eu** | ✅ | ✅ | ✅ | DNS europeu, sem fins lucrativos |
| **ControlD** | ✅ | ✅ | ✅ | Custom profiles, regras geográficas, redirecionamento de serviços |
| **OpenDNS / Cisco Umbrella** | Parcial | ❌ | ✅ | Clássico, parental controls, da Cisco |
| **CleanBrowsing** | ✅ | ✅ | ✅ | Filtros family/adult/security, gratuito |
| **LibreDNS** | ✅ | ✅ | ✅ | Sem logs, foco em privacidade, sem censura |
| **DNSCrypt-proxy** | — | — | — | Cliente local que adiciona DNSCrypt/DoH a qualquer SO | https://dnscrypt.info/ |
| **Stubby** | — | ✅ | — | Cliente DNS-over-TLS local | https://dnsprivacy.org/ |
| **YogaDNS** | — | — | — | Cliente Windows que aplica regras (DoH/DoT/DoQ) por domínio | https://www.yogadns.com/ |

### 16.2 Bloqueadores de Rastreadores em Rede

| Ferramenta | Tipo | Diferencial |
|---|---|---|
| **Pi-hole** | DNS sinkhole (auto-hospedado) | Bloqueia anúncios e rastreadores em toda a rede doméstica |
| **AdGuard Home** | DNS sinkhole (auto-hospedado) | Alternativa ao Pi-hole com interface moderna, DoH/DoT nativo |
| **Technitium DNS Server** | DNS recursivo + sinkhole | Servidor DNS completo com bloqueio, DoH/DoT/DoQ | https://technitium.com/dns/ |
| **Blocky** | DNS proxy | DNS proxy rápido em Go, listas de bloqueio | https://0xerr0r.github.io/blocky/ |
| **DNSCloak (iOS)** | Cliente DoH/DoT | Cliente móvel para usar DoH em iOS | App Store |
| **Nebulo (Android)** | Cliente DoH/DoT/DNSCrypt | Cliente Android open-source | F-Droid |

---

## 17. SEGURANÇA DE E-MAIL (PROVEDORES)

### [Camada 4 — Aplicação]

| Provedor | Open-Source | E2EE | Jurisdição | Diferencial | Link |
|---|---|---|---|---|---|
| **Proton Mail** | ✅ Sim | ✅ Nativo | Suíça | E2EE por padrão, zero-access encryption, calendario e drive integrados. ⚠️ Obrigado a registrar IP sob ordem judicial suíça (2021). | https://proton.me/mail |
| **Tuta** (ex-Tutanota) | ✅ Sim | ✅ Nativo | Alemanha | E2EE com protocolo próprio, calendário criptografado, plano gratuito | https://tuta.com/ |
| **Mailfence** | ❌ Não | ✅ (PGP) | Bélgica | PGP integrado, calendário, documentos, assinaturas digitais | https://mailfence.com/ |
| **Posteo** | ❌ Não | ✅ (PGP via Mailvelope) | Alemanha | Pagamento anônimo, energia renovável, €1/mês | https://posteo.de/ |
| **Mailbox.org** | Parcial | ✅ (PGP) | Alemanha | PGP server-side opcional, calendário, drive, €1-9/mês | https://mailbox.org/ |
| **StartMail** | ❌ Não | ✅ (PGP) | Holanda | Da Startpage, PGP integrado, aliases descartáveis | https://www.startmail.com/ |
| **CounterMail** | ❌ Não | ✅ Nativo | Suécia | OpenPGP forte, servidores diskless, jurisdição sueca | https://countermail.com/ |
| **Disroot** | ✅ Sim | ✅ (PGP) | Holanda | Coletivo sem fins lucrativos, ecossistema completo (mail, cloud, pad) | https://disroot.org/ |
| **Riseup** | ✅ Sim | ✅ | EUA (ativismo) | Provedor para ativistas, requer convite, sem logs | https://riseup.net/ |
| **Skiff Mail** | ✅ Sim | ✅ Nativo | EUA | E2EE, integração com web3 (⚠️ adquirido pela Notion em 2024 — status incerto) | https://skiff.com/ |
| **Soverin** | ❌ Não | ⚠️ | Holanda | Foco simplicidade + domínio próprio | https://soverin.net/ |
| **Runbox** | ❌ Não | ⚠️ (TLS) | Noruega | 100% energia renovável, jurisdição forte | https://runbox.com/ |
| **Kolab Now** | ✅ Sim | ⚠️ (TLS) | Suíça | Suite colaborativa (mail/cal/contacts/files) | https://kolabnow.com/ |

### 17.1 Servidores de E-mail Auto-Hospedados

| Ferramenta | Tipo | Diferencial |
|---|---|---|
| **Mailcow** | Stack Docker | Solução completa (Postfix, Dovecot, Rspamd, SoGo) |
| **Mail-in-a-Box** | Bundle | Setup automatizado em Ubuntu |
| **Mailu** | Stack Docker | Stack modular, antispam integrado |
| **Modoboa** | Suite Python | Painel administrativo amigável |
| **Stalwart Mail Server** | Tudo-em-um | Servidor Rust moderno (SMTP/IMAP/JMAP) com antispam embutido |
| **Maddy** | Tudo-em-um | Servidor SMTP+IMAP em Go, configuração simples |

---

## 18. CRIPTOATIVOS E CARTEIRAS SEGURAS

### [Camada 4 — Aplicação]

### 18.1 Hardware Wallets

| Carteira | Tipo | Diferencial |
|---|---|---|
| **Ledger** (Nano S Plus, Nano X, Stax) | Hardware | Chip seguro (CC EAL5+), suporte a 5.500+ criptoativos |
| **Trezor** (Model One, Model T, Safe 3) | Hardware | Open-source, sem chip seguro proprietário, interface web |
| **Coldcard Mk4** | Hardware | Bitcoin-only, air-gapped via SD/QR, código aberto |
| **BitBox02** | Hardware | Suíça, versões Bitcoin-only e Multi |
| **KeepKey** | Hardware | Open-source, tela grande |
| **Foundation Passport** | Hardware | Bitcoin-only air-gapped, foco em verificação |
| **Jade (Blockstream)** | Hardware | Acessível, integração com Green Wallet |

### 18.2 Software Wallets

| Carteira | Open-Source | Plataformas | Diferencial |
|---|---|---|---|
| **Sparrow Wallet** | ✅ Sim | Windows, macOS, Linux | Bitcoin-only, foco em privacidade, suporte a CoinJoin |
| **Electrum** | ✅ Sim | Windows, macOS, Linux, Android | Bitcoin-only, leve, suporte a hardware wallets |
| **Wasabi Wallet** | ✅ Sim | Windows, macOS, Linux | Bitcoin com CoinJoin nativo (WabiSabi) |
| **Samourai Wallet** | ✅ Sim | Android | Bitcoin com Whirlpool CoinJoin, Stonewall, Stowaway |
| **BlueWallet** | ✅ Sim | Android, iOS, Desktop | Bitcoin + Lightning, multi-carteira |
| **Zeus LN** | ✅ Sim | Android, iOS | Cliente para nó Lightning próprio |
| **Phoenix Wallet** | ✅ Sim | Android, iOS | Lightning self-custodial, abertura automática de canais |
| **Cake Wallet** | ✅ Sim | Multi | Monero/Bitcoin/etc., nó próprio configurável |
| **Monero GUI** | ✅ Sim | Multi | Carteira oficial Monero |
| **Feather Wallet** | ✅ Sim | Multi | Carteira leve Monero, suporte a Tor |
| **MyMonero** | ✅ Sim | Multi | Carteira Monero leve (⚠️ remote node) |

### 18.3 Moedas com Foco em Privacidade

| Moeda | Diferencial |
|---|---|
| **Monero (XMR)** | Transações privadas por padrão (ring signatures, stealth addresses, RingCT) |
| **Zcash (ZEC)** | Transações blindadas opcionais (zk-SNARKs) |
| **Firo (XZC)** | Lelantus Spark, anonimato sem trusted setup |
| **Pirate Chain (ARRR)** | Fork do Zcash com transações blindadas obrigatórias |
| **Dash** | PrivateSend (CoinJoin opcional) |
| **DeroHE** | Smart contracts privados via TLS-like + Stargate |

---

## 19. FERRAMENTAS OSINT / SOCK PUPPET

### [Camada 4 — Aplicação]

### 19.1 Geradores de Identidade Fictícia (para investigação/OSINT)

| Ferramenta | Tipo | Link |
|---|---|---|
| **4Devs** | Gerador de CPF, CNPJ, dados ficcionais (BR) | https://www.4devs.com.br/ |
| **Fake Name Generator** | Perfis completos fictícios | https://www.fakenamegenerator.com/ |
| **DataFakeGenerator** | Dados fictícios variados | http://www.datafakegenerator.com/ |
| **Randus** | Perfis aleatórios | https://randus.org/ |
| **FauxID** | Identidades fictícias | https://fauxid.com/ |
| **NameFake** | Nomes e dados fictícios | https://namefake.com/ |
| **FakeInfo** | Informações fictícias | https://fakeinfo.net/ |
| **UK-OSINT** | Guia para criação de identidades (investigação) | https://www.uk-osint.net/creatingids.html |

### 19.2 Geradores de Imagens (Faces Fictícias)

| Ferramenta | Link |
|---|---|
| **ThisPersonDoesNotExist** | https://thispersondoesnotexist.com/ |
| **WhichFaceIsReal** | https://www.whichfaceisreal.com/ |
| **Generated Photos** | https://generated.photos/ |

### 19.3 Números Temporários

| Serviço | Link |
|---|---|
| **TextNow** | https://www.textnow.com/ |
| **Hushed** | https://hushed.com |
| **BurnerApp** | https://www.burnerapp.com |
| **Blacktel** | https://blacktel.io |
| **OnlineSim** | https://onlinesim.io/ |
| **Fragment** (Telegram) | https://fragment.com/numbers |

### 19.4 Verificação de Exposição (OSINT Defensivo)

| Ferramenta | Tipo | Link |
|---|---|---|
| **Have I Been Pwned** | Verificar se seu e-mail/senha foram vazados | https://haveibeenpwned.com/ |
| **DeHashed** | Busca em bases de dados vazadas | https://dehashed.com/ |
| **Mozilla Monitor** | Monitoramento de vazamentos | https://monitor.mozilla.org/ |

### 19.5 Frameworks e Ferramentas OSINT (Investigativo)

| Ferramenta | Tipo | Diferencial |
|---|---|---|
| **Maltego** | Grafo/Visual | Plataforma clássica de OSINT, transformas comunitárias |
| **SpiderFoot** | Automatizado | 200+ módulos, rastreio automático de alvos |
| **theHarvester** | Recon | Coleta e-mails, subdomínios, hosts |
| **Recon-ng** | Framework | Framework modular Python para reconhecimento |
| **Sherlock** | Username | Busca usernames em 300+ redes sociais |
| **WhatsMyName** | Username | Web/CLI para lookup de usernames |
| **Holehe** | E-mail | Verifica em quais sites um e-mail tem conta |
| **GHunt** | Google | OSINT em contas Google (Gaia ID) |
| **OSINT Framework** | Diretório | Mapa visual de centenas de ferramentas | https://osintframework.com/ |
| **Photon** | Crawler | Crawler rápido para extrair dados de sites |
| **shodan.io** | Buscador | Motor de busca de dispositivos conectados |
| **Censys.io** | Buscador | Indexa hosts e certificados na internet |
| **GreyNoise** | Threat intel | Filtra ruído de scans massivos da internet |
| **EXIF.tools / FotoForensics** | Análise de imagem | Análise forense de imagens |
| **Yandex Reverse Image** | Imagens | Busca reversa muito eficaz para faces |
| **Wayback Machine** | Histórico web | Snapshots históricos de sites | https://web.archive.org/ |

---

## 20. MÁQUINAS VIRTUAIS E ISOLAMENTO

### [Transversal — Múltiplas Camadas]

| Ferramenta | Open-Source | Tipo | Diferencial |
|---|---|---|---|
| **VirtualBox** | ✅ Sim | Hypervisor tipo 2 | Gratuito, multiplataforma, fácil de usar |
| **KVM/QEMU** | ✅ Sim | Hypervisor tipo 1 (Linux) | Performance nativa, integração com libvirt |
| **Whonix** | ✅ Sim | VM pré-configurada | Gateway Tor + Workstation isolada |
| **VMware Workstation** | ❌ Não | Hypervisor tipo 2 | Performance profissional, snapshots avançados |
| **Hyper-V** | ❌ Não | Hypervisor tipo 1 (Windows) | Nativo Windows Pro/Enterprise, integração WSL2 |
| **Proxmox VE** | ✅ Sim | Hypervisor tipo 1 | Plataforma de virtualização empresarial baseada em KVM/LXC |
| **XCP-ng** | ✅ Sim | Hypervisor tipo 1 | Fork open-source do Citrix Hypervisor |
| **GNOME Boxes** | ✅ Sim | Linux | GUI simples para KVM |
| **virt-manager** | ✅ Sim | Linux | GUI clássica para libvirt/KVM |
| **UTM** | ✅ Sim | macOS, iOS | Frontend de QEMU para Apple Silicon |
| **Multipass** | ✅ Sim | Multi | VMs Ubuntu rápidas via CLI |
| **Vagrant** | ✅ Sim | Multi | Provisionamento de VMs reproduzível |
| **Docker / Podman** | ✅ Sim | Multi | Containerização; Podman é daemonless e rootless |
| **LXC / LXD / Incus** | ✅ Sim | Linux | Containers de sistema (não de aplicação) |

---

## 21. SEGURANÇA DE REDE DOMÉSTICA

### [Camada 1 — Acesso à Rede / Camada 4 — Aplicação]

| Ferramenta | Tipo | Diferencial |
|---|---|---|
| **Pi-hole** | DNS sinkhole | Bloqueia anúncios e rastreadores em toda a rede |
| **AdGuard Home** | DNS sinkhole | Interface moderna, DoH/DoT nativo, filtros customizáveis |
| **pfSense** | Firewall/Router | Firewall open-source profissional |
| **OPNsense** | Firewall/Router | Fork do pfSense, interface moderna |
| **OpenWrt** | Firmware de roteador | Firmware open-source para roteadores, customizável |
| **DD-WRT** | Firmware de roteador | Clássico custom firmware, ampla compat |
| **FreshTomato** | Firmware de roteador | Sucessor do Tomato, foco em desempenho |
| **IPFire** | Firewall/Router | Distribuição Linux focada em firewall |
| **Untangle / Edge Threat Management** | Firewall/UTM | Plataforma UTM com módulos comerciais e gratuitos |
| **Suricata** | IDS/IPS | Engine de detecção de intrusão de alta performance |
| **Snort 3** | IDS/IPS | IDS clássico mantido pela Cisco, regras comunitárias |
| **Zeek (Bro)** | NSM | Network monitoring para análise comportamental |
| **Wireshark** | Análise | Sniffer/analisador de pacotes padrão da indústria |
| **nmap / Zenmap** | Scanner de rede | Mapeamento de hosts e portas, descoberta de devices |
| **Fing** | Mobile/Desktop | Detecção de devices na rede doméstica |
| **Angry IP Scanner** | Scanner | Scanner de IP/portas multiplataforma |
| **WireGuard / Tailscale / Headscale** | VPN mesh | VPN mesh para acessar rede doméstica remotamente |
| **NetBird** | VPN mesh | Alternativa open-source ao Tailscale |
| **ZeroTier** | SDN/VPN | Rede virtual P2P |
| **Nebula** | Mesh VPN | Mesh VPN da Slack, escalável |

---

## 22. PRIVACIDADE DE FOTOS E ARMAZENAMENTO

### [Camada 4 — Aplicação]

| Serviço | Open-Source | E2EE | Diferencial | Link |
|---|---|---|---|---|
| **Ente Photos** | ✅ Sim | ✅ Nativo | Alternativa ao Google Photos com E2EE, auto-hospedável | https://ente.io/ |
| **Stingle Photos** | ✅ Sim | ✅ Nativo | Backup E2EE de fotos e vídeos | https://stingle.org/ |
| **Cryptee** | ✅ Sim | ✅ Nativo | Documentos + fotos criptografados, Estônia | https://crypt.ee/ |
| **Immich** | ✅ Sim | Parcial (E2EE em desenvolvimento) | Auto-hospedado, ML local (faces/objetos), substituto direto do Google Photos | https://immich.app/ |
| **PhotoPrism** | ✅ Sim | ⚠️ (em disco) | Auto-hospedado, IA local de classificação, Go | https://photoprism.app/ |
| **LibrePhotos** | ✅ Sim | ⚠️ | Auto-hospedado, reconhecimento facial, mapas | https://github.com/LibrePhotos/librephotos |
| **Piwigo** | ✅ Sim | ⚠️ | Galeria web clássica, organização flexível | https://piwigo.org/ |
| **Lychee** | ✅ Sim | ⚠️ | Galeria minimalista PHP | https://lycheeorg.github.io/ |

---

## 23. NOTIFICAÇÕES PUSH E ALTERNATIVAS

### [Camada 4 — Aplicação]

| Ferramenta | Tipo | Diferencial |
|---|---|---|
| **UnifiedPush** | Protocolo | Alternativa descentralizada ao Google FCM/Apple APNs para push notifications |
| **ntfy** | Servidor de notificações | Open-source, auto-hospedável, sem Google/Apple |

> ⚠️ **RISCO:** Google FCM e Apple APNs podem ser usados para rastreamento. Governos já solicitaram dados de notificações push a Google e Apple.

---

## 24. CHAVES DE SEGURANÇA FÍSICAS (HARDWARE)

### [Transversal — Múltiplas Camadas]

| Dispositivo | Protocolos | Diferencial |
|---|---|---|
| **YubiKey 5 Series** | FIDO2, U2F, TOTP, PIV, OpenPGP | Padrão da indústria, ampla compatibilidade, USB-A/C/NFC |
| **YubiKey Security Key** | FIDO2, U2F | Versão acessível, focada em FIDO2 |
| **Nitrokey** | FIDO2, OpenPGP, TOTP | Open-source (hardware e firmware), fabricado na Alemanha |
| **SoloKeys** | FIDO2, U2F | Open-source, acessível |
| **OnlyKey** | FIDO2, TOTP, senhas, PGP | Armazena senhas no hardware + 2FA, PIN de proteção |
| **Token2** | FIDO2, TOTP | Acessível, programaável para TOTP fixo |
| **Feitian ePass** | FIDO2, U2F | Linha econômica certificada FIDO |
| **GoTrust Idem Key** | FIDO2, U2F | Acessível, USB-A/C/Lightning |
| **Trustkey** | FIDO2, U2F | Coreano, certificação FIDO L1 |
| **Google Titan Security Key** | FIDO2, U2F | Chave do Google, USB-A/C/NFC |
| **Apple Security Keys** | FIDO2 | Suporte oficial em contas Apple ID (iOS 16.3+) |
| **NitroKey 3** | FIDO2, OpenPGP, OTP | Open-hardware, RISC-V, atualizável |
| **Tillitis TKey** | Customizável | Chave RISC-V open-hardware programável |

## 25. TRANSFERÊNCIA SEGURA DE ARQUIVOS

### [Camada 4 — Aplicação / Camada 2 — Internet]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **OnionShare** | ✅ Sim | Windows, macOS, Linux | P2P via Tor | Compartilha arquivos via serviço onion temporário, sem servidor intermediário, anônimo | https://onionshare.org/ |
| **Magic Wormhole** | ✅ Sim | Windows, macOS, Linux | P2P/CLI | Transferência E2EE com código curto falado, PAKE (SPAKE2), sem upload para nuvem | https://magic-wormhole.readthedocs.io/ |
| **Croc** | ✅ Sim | Windows, macOS, Linux | P2P/CLI | Similar ao Magic Wormhole, escrito em Go, suporta múltiplos arquivos e retomada | https://github.com/schollz/croc |
| **Wormhole.app (Send)** | ✅ Sim | Web | Navegador | E2EE via navegador, até 10GB, link auto-expirante, baseado no Firefox Send descontinuado | https://wormhole.app/ |
| **LocalSend** | ✅ Sim | Windows, macOS, Linux, Android, iOS | Rede local | AirDrop open-source multiplataforma, sem internet, criptografia TLS | https://localsend.org/ |
| **PairDrop** | ✅ Sim | Web | Rede local/Web | Fork do Snapdrop, compartilhamento P2P via navegador na mesma rede | https://pairdrop.net/ |
| **Tresorit Send** | ❌ Não | Web | Nuvem E2EE | Compartilhamento E2EE com controle de acesso, até 5GB gratuito | https://send.tresorit.com/ |
| **Keybase Filesystem** | ✅ Sim | Windows, macOS, Linux | P2P/Nuvem | Sistema de arquivos criptografado com identidade verificável | https://keybase.io/ |
| **RetroShare** | ✅ Sim | Windows, macOS, Linux | P2P | Comunicação descentralizada P2P com compartilhamento de arquivos, OpenPGP | https://retroshare.cc/ |
| **Syncthing** | ✅ Sim | Windows, macOS, Linux, Android | P2P | Sincronização contínua entre dispositivos, E2EE, sem servidor central | https://syncthing.net/ |
| **KDE Connect** | ✅ Sim | Multi | Rede local | Compartilhamento, clipboard, controle remoto entre dispositivos | https://kdeconnect.kde.org/ |
| **Warpinator** | ✅ Sim | Linux, Android | Rede local | Clône open-source do Nitroshare/AirDrop, do Linux Mint | https://github.com/linuxmint/warpinator |
| **ShareDrop** | ✅ Sim | Web | Rede local | AirDrop via WebRTC entre dispositivos da mesma rede | https://www.sharedrop.io/ |
| **Send (Tuta)** | Parcial | Web | E2EE | Sucessor inspirado no Firefox Send, planos pagos | https://tuta.com/ |
| **Bitwarden Send** | ✅ Sim | Web/App | E2EE | Texto/arquivo E2EE com expiração, integrado ao Bitwarden | https://bitwarden.com/products/send/ |

---

## 26. NOTAS E DOCUMENTOS CRIPTOGRAFADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | E2EE | Plataformas | Diferencial | Link |
|---|---|---|---|---|---|
| **Standard Notes** | ✅ Sim | ✅ Nativo | Windows, macOS, Linux, Android, iOS, Web | Notas E2EE, extensível com editores, 100% criptografado | https://standardnotes.com/ |
| **Joplin** | ✅ Sim | ✅ (com sync E2EE) | Windows, macOS, Linux, Android, iOS | Alternativa ao Evernote, Markdown, sync com Nextcloud/OneDrive/Dropbox | https://joplinapp.org/ |
| **Notesnook** | ✅ Sim | ✅ Nativo | Windows, macOS, Linux, Android, iOS, Web | Notas E2EE com editor rico, zero-knowledge, plano gratuito generoso | https://notesnook.com/ |
| **Obsidian** | ❌ Não | ⚠️ (com Sync pago) | Windows, macOS, Linux, Android, iOS | Vault local em Markdown, graph view, plugins extensivos. Dados locais por padrão. | https://obsidian.md/ |
| **Logseq** | ✅ Sim | ⚠️ (local) | Windows, macOS, Linux, Android, iOS | Outliner + graph, dados locais, sync via Git ou Logseq Sync | https://logseq.com/ |
| **Cryptee** | ✅ Sim | ✅ Nativo | Web | Documentos + fotos criptografados, Estônia | https://crypt.ee/ |
| **CryptPad** | ✅ Sim | ✅ Nativo | Web | Documentos colaborativos E2EE (docs, planilhas, kanban, formulários), auto-hospedável | https://cryptpad.org/ |
| **Trilium Notes** | ✅ Sim | ⚠️ (local/auto-hospedado) | Windows, macOS, Linux, Web | Base de conhecimento hierárquica, auto-hospedável, relações entre notas | https://github.com/zadam/trilium |
| **AnyType** | ✅ Sim | Multi | E2EE local-first com sync P2P | https://anytype.io/ |
| **SilverBullet** | ✅ Sim | Web | Notas Markdown extensível, auto-hospedado | https://silverbullet.md/ |
| **AppFlowy** | ✅ Sim | Multi | Alternativa FOSS ao Notion | https://appflowy.io/ |
| **Affine** | ✅ Sim | Multi | Alternativa moderna a Notion/Miro com edição local | https://affine.pro/ |
| **Memos** | ✅ Sim | Web/Mobile | Microblog/notas auto-hospedado | https://www.usememos.com/ |
| **Outline** | ✅ Sim | Web | Wiki para times auto-hospedado | https://www.getoutline.com/ |
| **BookStack** | ✅ Sim | Web | Wiki/documentação organizada em livros/capítulos | https://www.bookstackapp.com/ |
| **HedgeDoc** | ✅ Sim | Web | Markdown colaborativo em tempo real | https://hedgedoc.org/ |
| **Etherpad** | ✅ Sim | Web | Editor colaborativo clássico | https://etherpad.org/ |

---

## 27. PASTEBINS CRIPTOGRAFADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Diferencial | Link |
|---|---|---|---|
| **PrivateBin** | ✅ Sim | Pastebin minimalista E2EE, auto-hospedável, zero-knowledge, auto-destruição | https://privatebin.info/ |
| **0bin** | ✅ Sim | Pastebin criptografado client-side, chave na URL (nunca enviada ao servidor) | https://0bin.net/ |
| **Defuse.ca** | ✅ Sim | Pastebin criptografado por pesquisador de segurança, burn-after-reading | https://defuse.ca/pastebin.htm |
| **TheSecureNote** | ❌ Não | AES-256-GCM, auto-destruição, compartilhamento via QR | https://thesecurenote.com/ |

---

## 28. CLIENTES DE E-MAIL SEGUROS

### [Camada 4 — Aplicação]

| Cliente | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **Thunderbird** | ✅ Sim | Windows, macOS, Linux | Cliente completo, suporte nativo a OpenPGP (desde v78), calendário integrado | https://www.thunderbird.net/ |
| **K-9 Mail → Thunderbird Mobile** | ✅ Sim | Android | Renomeado para Thunderbird Mobile, OpenPGP via OpenKeychain | https://k9mail.app/ |
| **FairEmail** | ✅ Sim | Android | Focado em privacidade, sem rastreamento, suporte PGP, design material | https://email.faircode.eu/ |
| **Canary Mail** | ❌ Não | macOS, iOS, Android, Windows | PGP integrado, SecureSend (E2EE para não-PGP), IA local | https://canarymail.io/ |
| **Apple Mail** | ❌ Não | macOS, iOS | S/MIME nativo, integrado ao ecossistema Apple | — |
| **Mailvelope** | ✅ Sim | Extensão (Chrome, Firefox, Edge) | Adiciona PGP a qualquer webmail (Gmail, Outlook, Yahoo) | https://mailvelope.com/ |
| **Claws Mail** | ✅ Sim | Multi | Cliente leve em GTK, suporte a PGP via plugins | https://www.claws-mail.org/ |
| **Evolution** | ✅ Sim | Linux | Cliente GNOME completo, S/MIME, PGP, calendar | https://wiki.gnome.org/Apps/Evolution |
| **Geary** | ✅ Sim | Linux | Cliente GNOME minimalista | https://wiki.gnome.org/Apps/Geary |
| **Mutt / NeoMutt** | ✅ Sim | Multi (CLI) | Cliente terminal clássico, altamente customizável | https://neomutt.org/ |
| **aerc** | ✅ Sim | Multi (CLI) | Cliente terminal moderno em Go | https://aerc-mail.org/ |
| **Betterbird** | ✅ Sim | Multi | Fork “melhorado” do Thunderbird | https://www.betterbird.eu/ |
| **Outlook** | ❌ Não | Multi | Suporta S/MIME e Microsoft Purview | — |

---

## 29. VIDEOCONFERÊNCIA E CHAMADAS SEGURAS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | E2EE | Diferencial | Link |
|---|---|---|---|---|
| **Jitsi Meet** | ✅ Sim | ✅ (opcional) | Videoconferência sem conta, auto-hospedável, sem limite de participantes | https://meet.jit.si/ |
| **Signal (chamadas)** | ✅ Sim | ✅ Nativo | Chamadas de voz e vídeo E2EE, grupo até 40 pessoas | https://signal.org/ |
| **Element (Matrix)** | ✅ Sim | ✅ (Megolm) | Chamadas via protocolo Matrix, federado, auto-hospedável | https://element.io/ |
| **Wire** | ✅ Sim | ✅ Nativo | Chamadas E2EE, conferências, foco corporativo, Suíça | https://wire.com/ |
| **Brave Talk** | ❌ Não | ✅ (opcional) | Integrado ao Brave, baseado em Jitsi, chamadas gratuitas sem conta | https://talk.brave.com/ |
| **Mumble** | ✅ Sim | ✅ Sim | VoIP de baixa latência, criptografia forte, auto-hospedável, ideal para comunidades | https://www.mumble.info/ |
| **BigBlueButton** | ✅ Sim | Parcial | Plataforma de webconferência open-source, foco educacional, auto-hospedada | https://bigbluebutton.org/ |
| **Nextcloud Talk** | ✅ Sim | ✅ (1:1) | Chamadas integradas ao Nextcloud, auto-hospedado | https://nextcloud.com/talk/ |
| **Galene** | ✅ Sim | ⚠️ | SFU SFU leve em Go, auto-hospedado | https://galene.org/ |
| **Linphone** | ✅ Sim | ✅ (ZRTP) | Cliente SIP/VoIP com criptografia ZRTP | https://linphone.org/ |
| **Tox / qTox** | ✅ Sim | ✅ Padrão | Chamadas P2P E2EE sem servidores centrais | https://qtox.github.io/ |
| **Element Call** | ✅ Sim | ✅ (Megolm) | Chamadas em grupo nativas no Matrix | https://element.io/ |

---

## 30. FERRAMENTAS DE TESTE DE VAZAMENTO (LEAK TEST)

### [Transversal — Múltiplas Camadas]

| Ferramenta | Tipo | O que testa | Link |
|---|---|---|---|
| **DNS Leak Test** | Web | Vazamento de consultas DNS fora do túnel VPN | https://dnsleaktest.com/ |
| **IPLeak.net** | Web | Vazamento de IP, DNS, WebRTC, geolocalização, torrent IP | https://ipleak.net/ |
| **BrowserLeaks** | Web | WebRTC, Canvas, WebGL, AudioContext, fonts, etc. | https://browserleaks.com/ |
| **Mullvad Connection Check** | Web | IP, DNS, WebRTC, chave de conta Mullvad | https://mullvad.net/check |
| **AmIUnique** | Web | Fingerprint do navegador (quão único você é) | https://amiunique.org/ |
| **Cover Your Tracks (EFF)** | Web | Rastreabilidade do navegador, fingerprinting | https://coveryourtracks.eff.org/ |
| **CreepJS** | Web | Detecção avançada de fingerprinting e tentativas de spoofing | https://abrahamjuliot.github.io/creepjs/ |
| **Qualys SSL Labs** | Web | Configuração SSL/TLS de servidores | https://www.ssllabs.com/ssltest |
| **Mozilla Observatory** | Web | Segurança de headers HTTP de websites | https://observatory.mozilla.org/ |
| **Have I Been Pwned** | Web | Verificar se e-mail/senha foram vazados | https://haveibeenpwned.com/ |
| **';--have i been pwned (Passwords)** | Web | Verificar se uma senha específica apareceu em vazamentos | https://haveibeenpwned.com/Passwords |
| **DeHashed** | Web | Busca em bases de dados vazadas (e-mail, nome, IP, etc.) | https://dehashed.com/ |
| **Mozilla Monitor** | Web | Monitoramento contínuo de vazamentos para seu e-mail | https://monitor.mozilla.org/ |
| **GoLogin** | Desktop | Gerenciamento de múltiplos perfis de navegador (anti-fingerprinting) | https://gologin.com/ |
| **BrowserScan** | Web | Scanner de segurança e fingerprint do navegador | https://browserscan.net/ |
| **DeviceInfo** | Web | Informações detalhadas expostas pelo seu dispositivo/navegador | https://www.deviceinfo.me/ |
| **Panopticlick (legado)** | Web | Predecessor do Cover Your Tracks | https://panopticlick.eff.org/ |
| **WebRTC Leak Test** | Web | Teste isolado de vazamento WebRTC | https://www.expressvpn.com/webrtc-leak-test |
| **DoILeak** | Web | Teste consolidado IP/DNS/WebRTC | https://www.doileak.com/ |
| **Test-IPv6** | Web | Verifica conectividade e vazamentos IPv6 | https://test-ipv6.com/ |
| **What is My IP** | Web | Mostra IP público, DNS, headers | https://whatismyipaddress.com/ |
| **Email Header Analyzer (MXToolbox)** | Web | Analisa headers de e-mail (SPF/DKIM/DMARC) | https://mxtoolbox.com/EmailHeaders.aspx |
| **EmailRep** | Web/API | Reputação de endereços de e-mail | https://emailrep.io/ |
| **HardenedBSD/Kernel hardening checks** | CLI | Verificações de hardening de kernel | — |

---

## 31. PRIVACIDADE NO ANDROID (APPS E CONFIGURAÇÃO)

### [Transversal — Múltiplas Camadas]

### 31.1 Lojas Alternativas e Desgooglificação

| Ferramenta | Open-Source | Diferencial | Link |
|---|---|---|---|
| **F-Droid** | ✅ Sim | Loja de apps exclusivamente FOSS (Free and Open Source Software) | https://f-droid.org/ |
| **Aurora Store** | ✅ Sim | Cliente anônimo para Google Play Store (sem conta Google) | https://auroraoss.com/ |
| **Obtainium** | ✅ Sim | Obtém APKs diretamente dos repositórios (GitHub, GitLab), sem loja intermediária | https://github.com/ImranR98/Obtainium |
| **Droid-ify** | ✅ Sim | Cliente F-Droid moderno com Material Design 3 | https://github.com/Droid-ify/client |

### 31.2 Firewalls e Controle de Rede

| Ferramenta | Open-Source | Root | Diferencial | Link |
|---|---|---|---|---|
| **NetGuard** | ✅ Sim | ❌ Não | Firewall sem root via VPN local, bloqueia acesso à internet por app | https://netguard.me/ |
| **AFWall+** | ✅ Sim | ✅ Sim | Firewall baseado em iptables, controle granular por app/UID | https://github.com/ukanth/afwall |
| **RethinkDNS** | ✅ Sim | ❌ Não | Firewall + DNS + bloqueio de rastreadores, tudo em um | https://rethinkdns.com/ |
| **TrackerControl** | ✅ Sim | ❌ Não | Monitora e bloqueia rastreadores em tempo real, baseado no TrackerDB | https://trackercontrol.org/ |
| **Blokada** | ✅ Sim | ❌ Não | Bloqueador de anúncios e rastreadores no nível de DNS | https://blokada.org/ |

### 31.3 Isolamento e Perfis

| Ferramenta | Open-Source | Diferencial |
|---|---|---|
| **Shelter** | ✅ Sim | Cria perfil de trabalho isolado (Work Profile) para apps, usando funcionalidade nativa Android |
| **Insular** | ✅ Sim | Fork do Island, isola apps em sandbox usando perfil de trabalho |

### 31.4 Teclados Seguros

| Ferramenta | Open-Source | Diferencial | Link |
|---|---|---|---|
| **OpenBoard** | ✅ Sim | Teclado FOSS baseado no AOSP, sem conexão à internet | https://github.com/openboard-team/openboard |
| **HeliBoard** | ✅ Sim | Fork ativo do OpenBoard com melhorias, sem telemetria | https://github.com/Helium314/HeliBoard |
| **FlorisBoard** | ✅ Sim | Teclado moderno FOSS, extensível, em desenvolvimento ativo | https://florisboard.org/ |
| **AnySoftKeyboard** | ✅ Sim | Teclado FOSS com suporte a 200+ idiomas, sem rastreamento | https://anysoftkeyboard.github.io/ |

### 31.5 Outros Apps Android para Privacidade

| Ferramenta | Função | Link |
|---|---|---|
| **Scrambled Exif** | Remove metadados de fotos antes de compartilhar | F-Droid |
| **Fake GPS** | Simula localização GPS | Play Store |
| **Orbot** | Proxy Tor para Android (roteia apps pela rede Tor) | https://orbot.app/ |
| **NewPipe** | Cliente YouTube sem rastreamento Google, sem conta necessária | https://newpipe.net/ |
| **Organic Maps** | Mapas offline baseados em OpenStreetMap, sem rastreamento | https://organicmaps.app/ |
| **InviZible Pro** | DNSCrypt + Tor + I2P combinados em um app | F-Droid |
| **Exodus Privacy** | Auditoria de rastreadores e permissões em apps Android | https://exodus-privacy.eu.org/ |
| **TrackerControl** | Bloqueio de rastreadores em apps em tempo real | https://trackercontrol.org/ |
| **Warden** | Detecção de stalkerware em Android | F-Droid |
| **Hypatia** | Scanner antimalware FOSS para Android | F-Droid |
| **Briar** | Mensageria P2P offline-first (Tor/Wi-Fi/BT) | https://briarproject.org/ |
| **AntennaPod** | Cliente de podcasts FOSS sem rastreio | https://antennapod.org/ |
| **OsmAnd** | Mapas offline OpenStreetMap | https://osmand.net/ |
| **LibreTube** | Front-end YouTube via Piped sem Google | F-Droid |
| **NewPipe Sponsorblock** | NewPipe + SponsorBlock | F-Droid |
| **Tor Browser (Android)** | Versão oficial Tor para Android | https://www.torproject.org/ |
| **Bitwarden / KeePassDX** | Gerenciamento de senhas no Android | F-Droid / Play |
| **Aegis Authenticator** | TOTP com backup criptografado | https://getaegis.app/ |
| **DAVx⁵** | Sync CalDAV/CardDAV | https://www.davx5.com/ |
| **K-9/Thunderbird Mobile** | Cliente de e-mail FOSS | https://k9mail.app/ |
| **Document Viewer** | PDF reader minimalista FOSS | F-Droid |
| **Secure Camera** | Câmera com remoção automática de EXIF (GrapheneOS) | — |
| **Tasks.org** | Lista de tarefas FOSS com sync DAV | https://tasks.org/ |

---

## 32. PRIVACIDADE NO iOS

### [Transversal — Múltiplas Camadas]

| Ferramenta/Configuração | Tipo | Diferencial |
|---|---|---|
| **Safari** (hardened) | Navegador | Anti-fingerprinting nativo, Intelligent Tracking Prevention, isola cookies |
| **Lockdown Privacy** | Firewall | Firewall on-device para iOS, bloqueia rastreadores, open-source |
| **AdGuard Pro** | DNS/Bloqueador | Bloqueio de anúncios e rastreadores via DNS no nível do sistema |
| **Apple Mail + S/MIME** | E-mail | Suporte nativo a S/MIME para criptografia de e-mail |
| **Apple Hide My Email** | Aliases | Aliases de e-mail integrados ao iCloud+ |
| **iCloud Private Relay** | Proxy | Proxy de privacidade da Apple para Safari (oculta IP de sites) |
| **Brave (iOS)** | Navegador | Bloqueio nativo de rastreadores e anúncios |
| **Signal (iOS)** | Mensageiro | E2EE por padrão |
| **Orbot (iOS)** | Proxy Tor | Roteia tráfego via Tor no iOS |
| **Metapho** | Metadados | Visualiza e remove metadados de fotos no iPhone |
| **ProtonVPN (iOS)** | VPN | VPN open-source com plano gratuito |
| **1Blocker / Wipr / AdGuard** | Content blocker | Content blockers nativos do Safari |
| **Better Blocker** | Content blocker | Content blocker focado em ética/privacidade |
| **Firefox Focus (iOS)** | Navegador | Apaga sessão ao sair, usa WebKit |
| **Onion Browser** | Navegador Tor | Cliente Tor oficial para iOS |
| **Strongbox** | Senhas | Compatível com KeePass, integração iCloud |
| **KeePassium** | Senhas | Cliente KeePass moderno para iOS |
| **Raivo OTP / Tofu / OTP Auth** | 2FA | Apps TOTP nativos com backup iCloud |
| **DAVx⁵ alternatives (CardBook/CalDAV-Sync)** | Sync DAV | Sync de calendário/contatos com servidor próprio |
| **Stealth iCloud Backup encryption (Advanced Data Protection)** | Configuração | Habilitar ADP no iCloud para E2EE de backups (iOS 16.3+) |

> **Dica iOS:** Desative: Siri & Ditado (dados enviados à Apple), Analytics (Configurações > Privacidade > Analytics), Personalização de Anúncios, Localização para apps desnecessários.

---

## 33. FIREWALLS PESSOAIS (DESKTOP)

### [Camada 3 — Transporte / Camada 1 — Acesso à Rede]

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **Little Snitch** | ❌ Não | macOS | Firewall de aplicação com visualização de conexões em tempo real, controle granular | https://www.obdev.at/littlesnitch/ |
| **LuLu** | ✅ Sim | macOS | Firewall open-source para macOS, bloqueia conexões de saída não autorizadas | https://objective-see.org/products/lulu.html |
| **Portmaster** | ✅ Sim | Windows, Linux | Firewall de aplicação + DNS seguro + controle de privacidade por app | https://safing.io/portmaster/ |
| **simplewall** | ✅ Sim | Windows | Interface simples para Windows Filtering Platform (WFP), leve | https://github.com/henrypp/simplewall |
| **OpenSnitch** | ✅ Sim | Linux | Firewall de aplicação para Linux (similar ao Little Snitch) | https://github.com/evilsocket/opensnitch |
| **GlassWire** | ❌ Não | Windows, Android | Monitoramento visual de rede + firewall, detecta ameaças | https://www.glasswire.com/ |
| **Comodo Firewall** | ❌ Não | Windows | Firewall gratuito robusto com sandboxing de aplicações | https://www.comodo.com/home/internet-security/firewall.php |
| **UFW (Uncomplicated Firewall)** | ✅ Sim | Linux | Frontend simplificado para iptables, ideal para iniciantes Linux | — (nativo) |
| **firewalld** | ✅ Sim | Linux | Firewall dinâmico padrão em RHEL/Fedora | — |
| **nftables** | ✅ Sim | Linux | Sucessor moderno do iptables | — |
| **PFBlockerNG** | ✅ Sim | pfSense | Módulo para bloquear listas IP/DNS no pfSense | https://www.pfsense.org/ |
| **Sunshine Firewall (PFSense plugin)** | Parcial | pfSense | Painel amigável sobre pfSense | — |
| **TinyWall** | ✅ Sim | Windows | Wrapper leve para o firewall nativo do Windows | https://tinywall.pados.hu/ |
| **Windows Firewall Control** | ❌ Não | Windows | GUI avançada para Windows Defender Firewall | https://www.binisoft.org/ |
| **NetLimiter** | ❌ Não | Windows | Firewall + traffic shaping por aplicação | https://www.netlimiter.com/ |
| **PeerBlock** | ✅ Sim | Windows | Bloqueia ranges de IP por listas (legado, pouco mantido) | — |

---

## 34. REMOÇÃO DE DADOS PESSOAIS (DATA BROKERS)

### [Camada 4 — Aplicação]

| Serviço | Tipo | Cobertura | Diferencial | Link |
|---|---|---|---|---|
| **Incogni** | Automatizado | EUA, UK, Canadá, Suíça, UE | Remove dados de 180+ data brokers automaticamente, do grupo Surfshark | https://incogni.com/ |
| **DeleteMe** | Automatizado | EUA | Remove dados pessoais de data brokers, relatórios trimestrais | https://joindeleteme.com/ |
| **Privacy Duck** | Manual/Assistido | EUA | Remoção manual assistida, foco em completude | https://www.privacyduck.com/ |
| **Kanary** | Automatizado | EUA | Monitoramento contínuo + remoção de 400+ fontes | https://www.thekanary.com/ |
| **Optery** | Automatizado | EUA | Painel de controle visual, remoção de 300+ data brokers | https://www.optery.com/ |
| **JustDeleteMe** | Diretório/Manual | Global | Diretório de links diretos para deletar contas em serviços web | https://justdeleteme.xyz/ |
| **AccountKiller** | Diretório/Manual | Global | Guias passo a passo para deletar contas online | https://www.accountkiller.com/ |

> **LGPD/GDPR:** Cidadãos brasileiros e europeus podem exercer o direito de exclusão diretamente junto às empresas. Use modelos de solicitação LGPD disponíveis no site da ANPD.

---

## 35. SINCRONIZAÇÃO DE ARQUIVOS (P2P)

### [Camada 4 — Aplicação / Camada 3 — Transporte]

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **Syncthing** | ✅ Sim | Windows, macOS, Linux, Android | Sincronização P2P sem nuvem, E2EE, sem servidor central, relay opcional | https://syncthing.net/ |
| **Resilio Sync** | ❌ Não | Windows, macOS, Linux, Android, iOS | Sync P2P baseado em BitTorrent, rápido, planos empresariais | https://www.resilio.com/ |
| **Rclone** | ✅ Sim | Windows, macOS, Linux | CLI para sync com 40+ backends (S3, GDrive, Dropbox, SFTP), criptografia | https://rclone.org/ |
| **Unison** | ✅ Sim | Multi | Sync bidirecional clássico via SSH | https://www.cis.upenn.edu/~bcpierce/unison/ |
| **FreeFileSync** | ✅ Sim | Multi | GUI multiplataforma para sync entre pastas | https://freefilesync.org/ |
| **SyncBackFree** | ❌ Não | Windows | Sync e backup robustos, versão gratuita | https://www.2brightsparks.com/ |
| **Duplicacy** | Parcial | Multi | Backup/sync com lock-free deduplicação | https://duplicacy.com/ |
| **OnionShare Sync (em desenvolvimento)** | ✅ Sim | Multi | Sync via Tor onion services | https://onionshare.org/ |
| **Tailscale Drop / Taildrop** | Parcial | Multi | Compartilhamento rápido entre devices na sua tailnet | https://tailscale.com/kb/1106/taildrop |

---

## 36. CALENDÁRIOS E CONTATOS SEGUROS

### [Camada 4 — Aplicação]

| Serviço | Open-Source | E2EE | Diferencial | Link |
|---|---|---|---|---|
| **Proton Calendar** | ✅ Sim | ✅ Nativo | Calendário E2EE integrado ao ecossistema Proton, Suíça | https://proton.me/calendar |
| **Tuta Calendar** | ✅ Sim | ✅ Nativo | Calendário criptografado integrado ao Tuta Mail | https://tuta.com/ |
| **EteSync** | ✅ Sim | ✅ Nativo | Sync E2EE de calendário, contatos e tarefas, auto-hospedável | https://www.etesync.com/ |
| **Nextcloud Calendar/Contacts** | ✅ Sim | ⚠️ (em disco) | CalDAV/CardDAV auto-hospedável, integrado ao Nextcloud | https://nextcloud.com/ |
| **Radicale** | ✅ Sim | ⚠️ (em disco) | Servidor CalDAV/CardDAV leve e simples, auto-hospedável | https://radicale.org/ |
| **DAVx⁵** | ✅ Sim | — (cliente) | App Android para sync CalDAV/CardDAV com qualquer servidor | https://www.davx5.com/ |
| **Baikal** | ✅ Sim | ⚠️ | Servidor leve CalDAV/CardDAV em PHP | https://sabre.io/baikal/ |
| **Mailfence Calendar** | ❌ Não | ⚠️ | Calendário integrado ao Mailfence | https://mailfence.com/ |
| **Murena Cloud (incl. cal)** | ✅ Sim | ⚠️ | Suite tipo Google integrada ao /e/OS | https://murena.com/ |
| **Disroot Calendar** | ✅ Sim | ⚠️ | CalDAV via Nextcloud do coletivo Disroot | https://disroot.org/ |

---

## 37. PRIVACIDADE EM IA E LLMs

### [Camada 4 — Aplicação]

| Ferramenta/Prática | Tipo | Diferencial | Link |
|---|---|---|---|
| **DuckDuckGo AI Chat** | Chat IA privado | Acesso anônimo a LLMs (Claude, GPT, Llama), sem armazenamento de conversas | https://duckduckgo.com/aichat |
| **Brave Leo** | Chat IA no navegador | IA integrada ao Brave, conversas não associadas a conta, processamento local quando possível | https://brave.com/leo/ |
| **Ollama** | LLM local | Roda LLMs localmente (Llama, Mistral, Gemma, etc.), sem envio de dados para nuvem | https://ollama.com/ |
| **LM Studio** | LLM local | Interface gráfica para rodar LLMs localmente, chat e API local | https://lmstudio.ai/ |
| **Jan** | LLM local | Cliente open-source para LLMs locais, offline-first | https://jan.ai/ |
| **GPT4All** | LLM local | Roda modelos localmente, gratuito, privado | https://gpt4all.io/ |
| **CamoCopy** | Anonimização de texto | Remove padrões estilísticos (stylometry) do texto antes de postar, protege autoria | https://www.camocopy.com/ |
| **Open WebUI** | Interface local | UI web auto-hospedada para Ollama/llama.cpp, multi-usuário | https://openwebui.com/ |
| **AnythingLLM** | RAG local | Chat com seus documentos sem enviar à nuvem | https://anythingllm.com/ |
| **PrivateGPT** | RAG local | Pipeline RAG 100% offline | https://github.com/zylon-ai/private-gpt |
| **llama.cpp / llamafile** | Inferência local | Execução eficiente de LLMs em CPU/GPU comum | https://github.com/ggerganov/llama.cpp |
| **HuggingChat** | Chat IA aberto | Chat com modelos open-source hospedado pela Hugging Face | https://huggingface.co/chat |
| **Venice.ai** | Chat IA privado | Sem armazenamento de conversas, modelos open-source | https://venice.ai/ |
| **Mistral Le Chat** | Chat IA UE | Empresa francesa, conformidade GDPR | https://chat.mistral.ai/ |
| **Perplexity (modo incógnito)** | Busca IA | Modo que não retém histórico nem treina | https://www.perplexity.ai/ |
| **Whisper.cpp** | STT local | Transcrição de áudio offline com Whisper da OpenAI | https://github.com/ggerganov/whisper.cpp |
| **Piper TTS** | TTS local | Text-to-speech offline de qualidade | https://github.com/rhasspy/piper |
| **Coqui TTS / XTTS** | TTS local | Síntese de voz multilíngue offline | https://github.com/coqui-ai/TTS |

> ⚠️ **RISCO IA:** Todo texto enviado a serviços de IA na nuvem (ChatGPT, Gemini, etc.) pode ser usado para treinamento. Para dados sensíveis, use LLMs locais (Ollama, LM Studio) ou serviços com política explícita de não-treinamento (DuckDuckGo AI Chat, API do Claude).

---

## 38. SANDBOX E ISOLAMENTO DE APLICAÇÕES

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **Sandboxie-Plus** | ✅ Sim | Windows | Sandbox clássico para isolar apps Windows, fork mantido | https://sandboxie-plus.com/ |
| **Windows Sandbox** | ❌ Não | Windows 10/11 Pro | Sandbox descartável nativo baseado em Hyper-V | — |
| **Firejail** | ✅ Sim | Linux | Sandbox via namespaces/seccomp, perfis prontos para 1000+ apps | https://firejail.wordpress.com/ |
| **Bubblewrap** | ✅ Sim | Linux | Sandbox de baixo nível usado pelo Flatpak | https://github.com/containers/bubblewrap |
| **Flatpak** | ✅ Sim | Linux | Apps em sandbox com permissões via portals | https://flatpak.org/ |
| **Snap** | Parcial | Linux | Sandboxing AppArmor da Canonical | https://snapcraft.io/ |
| **AppImage + Firejail** | ✅ Sim | Linux | AppImages portáteis isoladas com Firejail | — |
| **Toolbx / Distrobox** | ✅ Sim | Linux | Containers de desenvolvimento integrados ao host | https://distrobox.it/ |
| **Cuckoo Sandbox** | ✅ Sim | Linux | Sandbox para análise dinâmica de malware | https://cuckoosandbox.org/ |
| **CAPE Sandbox** | ✅ Sim | Linux | Fork moderno do Cuckoo focado em malware atual | https://github.com/kevoreilly/CAPEv2 |
| **Shade Sandbox** | ❌ Não | Windows | Sandbox simples para Windows | — |
| **macOS App Sandbox** | ❌ Não | macOS | Sandboxing nativo para apps da App Store | — |
| **gVisor** | ✅ Sim | Linux | Sandbox de container com kernel userspace (Google) | https://gvisor.dev/ |
| **Kata Containers** | ✅ Sim | Linux | Containers com isolamento de VM leve | https://katacontainers.io/ |

---

## 39. OFFICE SUITES E COLABORAÇÃO PRIVADA

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **LibreOffice** | ✅ Sim | Multi | Suite office completa, sem telemetria, padrão ODF | https://www.libreoffice.org/ |
| **OnlyOffice Docs** | ✅ Sim | Multi + Web | Edição colaborativa, alta compatibilidade com OOXML, auto-hospedado | https://www.onlyoffice.com/ |
| **Collabora Online** | ✅ Sim | Web | LibreOffice em browser, integra com Nextcloud | https://www.collaboraonline.com/ |
| **CryptPad** | ✅ Sim | Web | Suite colaborativa E2EE (docs, planilhas, kanban, formulários) | https://cryptpad.org/ |
| **EtherCalc** | ✅ Sim | Web | Planilha colaborativa em tempo real | https://ethercalc.net/ |
| **HedgeDoc** | ✅ Sim | Web | Notas Markdown colaborativas | https://hedgedoc.org/ |
| **Nextcloud Office** | ✅ Sim | Web | Edição colaborativa via Collabora ou OnlyOffice | https://nextcloud.com/ |
| **Apache OpenOffice** | ✅ Sim | Multi | Antecessor do LibreOffice (manutenção lenta) | https://www.openoffice.org/ |
| **Calligra Suite** | ✅ Sim | Multi | Suite KDE com Words, Sheets, Stage | https://calligra.org/ |
| **WPS Office** | ❌ Não | Multi | Compatibilidade Office. ⚠️ Telemetria, base na China | https://www.wps.com/ |
| **AbiWord** | ✅ Sim | Multi | Processador de texto leve | https://www.abisource.com/ |
| **Gnumeric** | ✅ Sim | Linux | Planilha leve e precisa | http://www.gnumeric.org/ |

---

## 40. EDITORES E FERRAMENTAS DE PDF SEGURAS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Diferencial | Link |
|---|---|---|---|---|
| **PDF Arranger** | ✅ Sim | Multi | Reorganiza/extrai/divide páginas (GUI sobre pikepdf) | https://github.com/pdfarranger/pdfarranger |
| **Stirling-PDF** | ✅ Sim | Web (auto-hospedado) | Suite PDF completa local (split, merge, OCR, redact) | https://github.com/Stirling-Tools/Stirling-PDF |
| **PDF.js** | ✅ Sim | Web | Renderizador PDF do Mozilla, sem plugins externos | https://mozilla.github.io/pdf.js/ |
| **qpdf** | ✅ Sim | CLI | Manipulação avançada de PDF, criptografia, lineariza | https://qpdf.sourceforge.io/ |
| **pdftk** | ✅ Sim | CLI | Toolkit clássico para PDF | — |
| **Sumatra PDF** | ✅ Sim | Windows | Leitor PDF leve sem telemetria | https://www.sumatrapdfreader.org/ |
| **Okular** | ✅ Sim | Multi | Leitor KDE, suporte a anotações, sem telemetria | https://okular.kde.org/ |
| **Xournal++** | ✅ Sim | Multi | Anotações e assinatura em PDFs | https://xournalpp.github.io/ |
| **PDF Redact Tools** | ✅ Sim | CLI | Redação segura de PDFs (Freedom of the Press) | https://github.com/firstlookmedia/pdf-redact-tools |
| **Redacter** | ✅ Sim | CLI | Redação automatizada via OCR | — |
| **ExifTool (PDF)** | ✅ Sim | CLI | Remove metadados de PDFs | https://exiftool.org/ |
| **Adobe Acrobat (Redact)** | ❌ Não | Windows, macOS | Redação verificada em padrão DoD; ⚠️ telemetria | https://www.adobe.com/ |
| **Foxit Reader** | ❌ Não | Multi | Alternativa ao Adobe; ⚠️ telemetria/anúncios | https://www.foxit.com/ |
| **PDFsam Basic** | ✅ Sim | Multi | Split, merge, rotate de PDFs | https://pdfsam.org/ |
| **PrivacyByDefault Redactor** | — | Web | Use offline. ⚠️ Cuidado com PDFs sensíveis em web tools |

---

## 41. TRADUTORES E FERRAMENTAS LINGUÍSTICAS PRIVADAS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **LibreTranslate** | ✅ Sim | Web/API | Tradução open-source auto-hospedável | https://libretranslate.com/ |
| **Argos Translate** | ✅ Sim | Local | Tradução offline desktop/CLI baseada em modelos OpenNMT | https://www.argosopentech.com/ |
| **Bergamot Translate** | ✅ Sim | Local | Tradução in-browser do Mozilla (Firefox Translate) | https://browser.mt/ |
| **Mozilla Translate (Firefox)** | ✅ Sim | Browser | Tradução local nativa no Firefox | — |
| **DeepL** | ❌ Não | Web/Desktop | Alta qualidade. ⚠️ Texto enviado ao servidor | https://www.deepl.com/ |
| **NLLB-200** | ✅ Sim | Modelo | Modelo Meta open-source para 200 idiomas (uso local) | — |
| **OpenNMT** | ✅ Sim | Framework | Treinamento de modelos próprios | https://opennmt.net/ |
| **LanguageTool** | ✅ Sim | Multi | Corretor gramatical auto-hospedável | https://languagetool.org/ |
| **Vosk** | ✅ Sim | Local | Reconhecimento de fala offline para 20+ idiomas | https://alphacephei.com/vosk/ |

---

## 42. MÍDIA: STREAMING, VÍDEO E MÚSICA PRIVADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **Jellyfin** | ✅ Sim | Servidor de mídia | Substituto FOSS ao Plex/Emby, sem rastreio | https://jellyfin.org/ |
| **Kodi** | ✅ Sim | Player | Centro de mídia clássico | https://kodi.tv/ |
| **Plex** | ❌ Não | Servidor | Popular. ⚠️ Telemetria e exigência de conta | — |
| **Emby** | Parcial | Servidor | Antecessor do Jellyfin (closed após v3.6) | — |
| **Funkwhale** | ✅ Sim | Streaming música | Fediverso, federado | https://funkwhale.audio/ |
| **Navidrome** | ✅ Sim | Streaming música | Servidor leve compatível com Subsonic | https://www.navidrome.org/ |
| **Airsonic-Advanced / Gonic** | ✅ Sim | Streaming música | Forks ativos do Subsonic | https://github.com/airsonic-advanced |
| **Mopidy** | ✅ Sim | Streaming música | Player extensível com plugins | https://mopidy.com/ |
| **Music Assistant** | ✅ Sim | Player/HA | Integração com Home Assistant | https://www.music-assistant.io/ |
| **mpv** | ✅ Sim | Player vídeo | Player minimalista poderoso | https://mpv.io/ |
| **VLC** | ✅ Sim | Player vídeo | Player universal, sem telemetria | https://www.videolan.org/ |
| **Audacious / Strawberry / Clementine** | ✅ Sim | Player áudio | Players desktop FOSS | — |
| **NewPipe / LibreTube / Piped / Invidious** | ✅ Sim | Frontend YouTube | Acesso ao YouTube sem rastreio Google | — |
| **FreeTube** | ✅ Sim | Frontend YouTube desktop | Cliente desktop com sponsorblock | https://freetubeapp.io/ |
| **yt-dlp** | ✅ Sim | CLI | Download de mídia de centenas de sites | https://github.com/yt-dlp/yt-dlp |
| **Tubular** | ✅ Sim | Android | Fork do NewPipe com SponsorBlock e ReturnYoutubeDislike | F-Droid |

---

## 43. REDES SOCIAIS E MICROBLOGGING ALTERNATIVOS

### [Camada 4 — Aplicação]

| Plataforma | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **Mastodon** | ✅ Sim | Microblog federado | Maior rede do Fediverso, ActivityPub | https://joinmastodon.org/ |
| **Pleroma / Akkoma** | ✅ Sim | Microblog federado | Servidores leves alternativos a Mastodon | https://akkoma.social/ |
| **Misskey / Sharkey / Firefish** | ✅ Sim | Microblog federado | Forks com recursos extras (reactions, drive) | https://misskey-hub.net/ |
| **GoToSocial** | ✅ Sim | Microblog federado | Servidor leve em Go para single-user | https://gotosocial.org/ |
| **Lemmy** | ✅ Sim | Agregador (Reddit-like) | Comunidades federadas via ActivityPub | https://join-lemmy.org/ |
| **Kbin / Mbin** | ✅ Sim | Agregador federado | Mistura Reddit + microblog | https://kbin.pub/ |
| **Friendica** | ✅ Sim | Rede social federada | Estilo Facebook, conecta-se a múltiplos protocolos | https://friendi.ca/ |
| **Diaspora\*** | ✅ Sim | Rede social federada | Pioneiro federado, pods independentes | https://diasporafoundation.org/ |
| **Bluesky / AT Proto** | ✅ Sim | Microblog | Rede com protocolo AT, federação em desenvolvimento | https://bsky.app/ |
| **Nostr (Damus, Amethyst, etc.)** | ✅ Sim | Protocolo P2P | Notas e relays simples, identidade por chave | https://nostr.com/ |
| **Hubzilla** | ✅ Sim | Rede social/CMS | Identidade nômade entre servidores | https://hubzilla.org/ |
| **Movim** | ✅ Sim | Rede social XMPP | Microblog sobre XMPP | https://movim.eu/ |

---

## 44. PLATAFORMAS DE VÍDEO ALTERNATIVAS

### [Camada 4 — Aplicação]

| Plataforma | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **PeerTube** | ✅ Sim | Federado P2P | Alternativa federada ao YouTube com WebTorrent | https://joinpeertube.org/ |
| **Odysee / LBRY** | Parcial | Blockchain | Vídeos descentralizados via LBRY | https://odysee.com/ |
| **Tilvids** | ✅ Sim | Instância PeerTube | Curadoria de canais | https://tilvids.com/ |
| **Invidious** | ✅ Sim | Frontend YouTube | Proxy web sem JS/cookies do Google | https://invidious.io/ |
| **Piped** | ✅ Sim | Frontend YouTube | Frontend moderno para YouTube | https://piped.video/ |
| **Hyperpipe** | ✅ Sim | Frontend YT Music | Cliente YouTube Music sem rastreio | https://hyperpipe.surge.sh/ |
| **NewPipe / LibreTube** | ✅ Sim | Android | Clientes Android sem Google | — |
| **Owncast** | ✅ Sim | Live streaming | Servidor próprio para streaming ao vivo | https://owncast.online/ |
| **DTube** | ✅ Sim | Blockchain | Vídeos via Hive blockchain + IPFS | https://d.tube/ |

---

## 45. HOSPEDAGEM DE CÓDIGO E COLABORAÇÃO

### [Camada 4 — Aplicação]

| Plataforma | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **Codeberg** | ✅ Sim | Hosting Git | Forge sem fins lucrativos, baseado em Forgejo | https://codeberg.org/ |
| **Forgejo** | ✅ Sim | Auto-hospedado | Fork comunitário do Gitea | https://forgejo.org/ |
| **Gitea** | ✅ Sim | Auto-hospedado | Forge leve em Go | https://gitea.io/ |
| **GitLab CE** | ✅ Sim | Auto-hospedado | DevOps completo, CI/CD integrado | https://about.gitlab.com/ |
| **SourceHut** | ✅ Sim | Hosting/Auto | Foco em correio + listas + builds | https://sourcehut.org/ |
| **Gogs** | ✅ Sim | Auto-hospedado | Antecessor leve do Gitea | https://gogs.io/ |
| **Disroot Git (Forgejo)** | ✅ Sim | Hosting | Coletivo Disroot | https://git.disroot.org/ |
| **Tildegit / Notabug** | ✅ Sim | Hosting | Comunidades alternativas | — |
| **Radicle** | ✅ Sim | P2P | Forge P2P descentralizada com identidade criptográfica | https://radicle.xyz/ |
| **Fossil SCM** | ✅ Sim | SCM/forge | SCM + wiki + tickets em um único binário | https://fossil-scm.org/ |

---

## 46. COMPARTILHAMENTO SEGURO DE SENHAS/SEGREDOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **Bitwarden Send** | ✅ Sim | Texto/arquivo | Expiração e proteção por senha, integrado ao Bitwarden | https://bitwarden.com/products/send/ |
| **OneTimeSecret** | ✅ Sim | Texto | Burn-after-reading clássico | https://onetimesecret.com/ |
| **PasswordPusher (pwpush)** | ✅ Sim | Texto | Auto-hospedável, expiração configurável | https://pwpush.com/ |
| **Yopass** | ✅ Sim | Texto/arquivo | Em Go, fácil de hospedar | https://github.com/jhaals/yopass |
| **Snappass** | ✅ Sim | Texto | Compartilhamento interno (Pinterest) | https://github.com/pinterest/snappass |
| **Hemmelig** | ✅ Sim | Texto/arquivo | Burn-after-reading com anexos | https://hemmelig.app/ |
| **Vaultwarden Send** | ✅ Sim | Texto/arquivo | Vaultwarden auto-hospedado com Send | https://github.com/dani-garcia/vaultwarden |
| **CryptGeon** | ✅ Sim | Texto/arquivo | Notas seguras com expiração | https://cryptgeon.org/ |
| **PrivateBin (burn)** | ✅ Sim | Texto | Pastebin com burn-after-reading | https://privatebin.info/ |
| **Send.tresorit.com** | ❌ Não | Arquivo | E2EE com controle de acesso | https://send.tresorit.com/ |
| **Firefox Send (descontinuado)** | ✅ Sim (legado) | — | Vários forks hosted (ex: send.vis.ee) | — |

---

## 47. FERRAMENTAS FORENSES E ANTI-STALKERWARE

### [Transversal]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **MVT (Mobile Verification Toolkit)** | ✅ Sim | Android, iOS | Forense | Detecta indicadores de spyware tipo Pegasus, da Amnesty | https://mvt.re/ |
| **iVerify** | ❌ Não | iOS, Android | Forense/EDR | Verifica integridade do dispositivo e ameaças | https://www.iverify.io/ |
| **Stalkerware-Indicators** | ✅ Sim | Multi | Lista | Lista de IOCs da Coalition Against Stalkerware | https://github.com/AssoEchap/stalkerware-indicators |
| **TinyCheck** | ✅ Sim | Linux/RPi | Rede | Box que analisa tráfego de um celular suspeito (Kaspersky) | https://github.com/KasperskyLab/TinyCheck |
| **Warden (Android)** | ✅ Sim | Android | Scanner | Detecção de stalkerware | F-Droid |
| **Autopsy** | ✅ Sim | Multi | Forense | Plataforma forense digital baseada em Sleuth Kit | https://www.autopsy.com/ |
| **The Sleuth Kit (TSK)** | ✅ Sim | Multi | Forense | Conjunto CLI para forense de discos | https://www.sleuthkit.org/ |
| **Volatility 3** | ✅ Sim | Multi | Forense de memória | Framework para análise de RAM | https://www.volatilityfoundation.org/ |
| **Velociraptor** | ✅ Sim | Multi | DFIR | EDR e forense em endpoints distribuídos | https://docs.velociraptor.app/ |
| **GRR Rapid Response** | ✅ Sim | Multi | DFIR | Framework forense remoto (Google) | https://github.com/google/grr |
| **Caine Linux** | ✅ Sim | Live | Distro forense | Distro Linux para investigações | https://www.caine-live.net/ |
| **OSForensics** | ❌ Não | Windows | Forense | Suite forense Windows | https://www.osforensics.com/ |

---

## 48. BLOQUEADORES DE ANÚNCIOS E RASTREADORES (STANDALONE)

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **uBlock Origin** | ✅ Sim | Navegador | Extensão | Padrão-ouro, eficiente, modo medium/hard | https://ublockorigin.com/ |
| **uBlock Origin Lite** | ✅ Sim | Navegador (MV3) | Extensão | Versão Manifest V3 para Chrome | — |
| **AdGuard (Desktop/Mobile)** | Parcial | Multi | App/Sistema | Filtra em todo o sistema (não só no browser) | https://adguard.com/ |
| **AdGuard Home** | ✅ Sim | Servidor | DNS | Bloqueio em rede | https://adguard.com/adguard-home/ |
| **Pi-hole** | ✅ Sim | Servidor | DNS | Sinkhole DNS clássico | https://pi-hole.net/ |
| **Blokada** | ✅ Sim | Android, iOS | App | DNS local, planos pagos com cloud | https://blokada.org/ |
| **DNS66** | ✅ Sim | Android | App | Bloqueio via DNS local sem root (descontinuado oficial, ainda funcional) | F-Droid |
| **NetGuard + filtro** | ✅ Sim | Android | Firewall | Firewall + filtro DNS por app | https://netguard.me/ |
| **RethinkDNS** | ✅ Sim | Android | Firewall+DNS | All-in-one moderno | https://rethinkdns.com/ |
| **Brave Shields** | ✅ Sim | Browser | Embutido | Bloqueio nativo no Brave | https://brave.com/ |
| **uMatrix (legado)** | ✅ Sim | Browser | Extensão | Controle granular por origem (descontinuado) | — |

---

## 49. GERENCIADORES DE COOKIES E LIMPEZA DE NAVEGAÇÃO

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **Cookie AutoDelete** | ✅ Sim | Firefox/Chrome | Extensão | Apaga cookies ao fechar aba | https://github.com/Cookie-AutoDelete/Cookie-AutoDelete |
| **Multi-Account Containers** | ✅ Sim | Firefox | Extensão | Isola cookies por container | https://addons.mozilla.org/firefox/addon/multi-account-containers/ |
| **Temporary Containers** | ✅ Sim | Firefox | Extensão | Container descartável por aba | https://github.com/stoically/temporary-containers |
| **Facebook/Google Container** | ✅ Sim | Firefox | Extensão | Isola serviços específicos | — |
| **Forget Me Not** | ✅ Sim | Firefox | Extensão | Limpeza configurável por domínio | — |
| **Self-Destructing Cookies (legado)** | ✅ Sim | Firefox | Extensão | Pioneiro do Cookie AutoDelete | — |
| **BleachBit** | ✅ Sim | Multi | Desktop | Limpa caches, cookies, históricos do sistema | https://www.bleachbit.org/ |
| **PrivaZer** | ❌ Não | Windows | Desktop | Limpeza profunda Windows + sobrescrita | https://privazer.com/ |
| **Tron Script** | ✅ Sim | Windows | Script | Limpeza/manutenção massiva (avançado) | https://www.reddit.com/r/TronScript/ |
| **Stacer** | ✅ Sim | Linux | Desktop | Limpeza/monitoramento Linux | https://oguzhaninan.github.io/Stacer-Web/ |
| **Onyx** | ❌ Não | macOS | Desktop | Manutenção/limpeza macOS | https://www.titanium-software.fr/en/onyx.html |
| **Ferramenta Limpar Dados (Chrome/Firefox)** | — | Browser | Nativo | Cmd+Shift+Del / Ctrl+Shift+Del | — |

---

## 50. MAPAS, NAVEGAÇÃO E LOCALIZAÇÃO PRIVADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **OpenStreetMap (OSM)** | ✅ Sim | Web | Base de mapas | Base livre usada por outras ferramentas | https://www.openstreetmap.org/ |
| **Organic Maps** | ✅ Sim | Android, iOS | Offline | Mapas e navegação OSM sem rastreio | https://organicmaps.app/ |
| **OsmAnd** | ✅ Sim | Android, iOS | Offline | Recursos avançados (rotas, trilhas) | https://osmand.net/ |
| **Magic Earth** | ❌ Não | Multi | App | Navegação amigável com tráfego, política de privacidade decente | https://www.magicearth.com/ |
| **HERE WeGo** | ❌ Não | Multi | App | Mapas offline, base europeia | https://wego.here.com/ |
| **GMaps WV / GMaps Lite** | ✅ Sim | Android | Wrapper | Wrapper privado de Google Maps | F-Droid |
| **Maps.me (legado)** | Parcial | Multi | Offline | Antecessor do Organic Maps | — |
| **Komoot** | ❌ Não | Multi | Trilhas | Trilhas/ciclismo, política razoável | https://www.komoot.com/ |
| **GPSLogger** | ✅ Sim | Android | Logger | Registro privado de trilhas (sem nuvem) | F-Droid |
| **PhonetTrack / OwnTracks** | ✅ Sim | Multi | Localização própria | Compartilhe sua localização via MQTT/HTTPS próprios | https://owntracks.org/ |
| **Traccar** | ✅ Sim | Servidor | Rastreamento | Servidor de rastreamento auto-hospedado | https://www.traccar.org/ |
| **Mozilla Location Service (MLS)** | ✅ Sim | Backend | Geo Wi-Fi | Geolocalização sem Google (descontinuado em 2024 — buscar alternativas) | — |
| **DejaVu (microG)** | ✅ Sim | Android | Geo offline | Backend de localização local | F-Droid |

---

## 51. APPS DE SAÚDE, FITNESS E PERÍODO PRIVADOS

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **Drip** | ✅ Sim | Android, iOS | Ciclo menstrual | Dados 100% locais, sem nuvem (importante pós-Roe v Wade) | https://dripapp.org/ |
| **Periodical** | ✅ Sim | Android | Ciclo menstrual | Local, simples, sem rastreio | F-Droid |
| **Euki** | ✅ Sim | Android, iOS | Saúde reprodutiva | Local, multilíngue | https://eukiapp.com/ |
| **OpenScale** | ✅ Sim | Android | Balança/peso | Funciona offline, suporta balanças BLE | F-Droid |
| **OpenTracks** | ✅ Sim | Android | Atividade | Registro de atividades sem nuvem | F-Droid |
| **FitoTrack** | ✅ Sim | Android | Atividade | Registro local de exercícios | F-Droid |
| **Forrunners** | ✅ Sim | Multi | Corrida | Ferramenta para Garmin sem cloud | — |
| **Gadgetbridge** | ✅ Sim | Android | Wearables | Cliente para wearables (Mi Band, Pebble, Amazfit, etc.) sem app proprietário | https://gadgetbridge.org/ |
| **Loop Habit Tracker** | ✅ Sim | Android | Hábitos | Tracker local de hábitos | F-Droid |
| **Daylio (alternativa FOSS: Mood Diary)** | Parcial | Multi | Humor | Diário de humor local | — |
| **AntennaPod** | ✅ Sim | Android | Podcasts | Sem rastreio | https://antennapod.org/ |
| **OpenFoodFacts** | ✅ Sim | Multi | Alimentos | Base aberta de produtos alimentares | https://world.openfoodfacts.org/ |

---

## 52. LEITORES DE FEED (RSS) E READ-IT-LATER

### [Camada 4 — Aplicação]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **FreshRSS** | ✅ Sim | Auto-hospedado | Servidor RSS | Leve, multi-usuário, API Fever/GReader | https://freshrss.org/ |
| **Tiny Tiny RSS** | ✅ Sim | Auto-hospedado | Servidor RSS | Clássico veterano | https://tt-rss.org/ |
| **Miniflux** | ✅ Sim | Auto-hospedado | Servidor RSS | Minimalista em Go | https://miniflux.app/ |
| **Newsboat** | ✅ Sim | CLI | Cliente RSS | Cliente terminal rápido | https://newsboat.org/ |
| **NetNewsWire** | ✅ Sim | macOS, iOS | Cliente | Cliente nativo Apple | https://netnewswire.com/ |
| **Feeder** | ✅ Sim | Android | Cliente | Cliente offline-first | F-Droid |
| **Read You** | ✅ Sim | Android | Cliente | Material You moderno | F-Droid |
| **RSS Guard** | ✅ Sim | Multi | Cliente | Suporte a APIs (TT-RSS, Nextcloud News) | https://github.com/martinrotter/rssguard |
| **QuiteRSS / Liferea** | ✅ Sim | Multi | Cliente | Clientes desktop clássicos | — |
| **Wallabag** | ✅ Sim | Auto-hospedado | Read-it-later | Alternativa FOSS ao Pocket | https://www.wallabag.org/ |
| **Omnivore** | ✅ Sim | Multi | Read-it-later | Open-source, anotações | https://omnivore.app/ |
| **Karakeep (ex-Hoarder)** | ✅ Sim | Auto-hospedado | Bookmarks | Salvar links com IA local | https://karakeep.app/ |
| **Linkding** | ✅ Sim | Auto-hospedado | Bookmarks | Bookmark manager simples | https://github.com/sissbruecker/linkding |
| **Shaarli** | ✅ Sim | Auto-hospedado | Bookmarks | Bookmark manager clássico em PHP | https://github.com/shaarli/Shaarli |

---

## 53. OFUSCAÇÃO DE TRÁFEGO E ANTI-CENSURA

### [Camada 2/3]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **obfs4 / lyrebird** | ✅ Sim | Pluggable transport | Disfarça tráfego Tor como random | — |
| **meek** | ✅ Sim | Pluggable transport | Domain fronting (Azure/CDN) | — |
| **WebTunnel** | ✅ Sim | Pluggable transport | Tor disfarçado de tráfego HTTPS | https://webtunnel.torproject.org/ |
| **Snowflake** | ✅ Sim | Pluggable transport | WebRTC peers como bridges | https://snowflake.torproject.org/ |
| **V2Ray (Project V) / V2Fly** | ✅ Sim | Proxy | Múltiplos protocolos (VMess, VLESS, Trojan) | https://www.v2fly.org/ |
| **Xray-core** | ✅ Sim | Proxy | Fork avançado do V2Ray | https://xtls.github.io/ |
| **Shadowsocks** | ✅ Sim | Proxy | Proxy criptografado popular contra GFW | https://shadowsocks.org/ |
| **ShadowsocksR (legado)** | ✅ Sim | Proxy | Fork com mais ofuscações | — |
| **Trojan-GFW** | ✅ Sim | Proxy | Tráfego indistinguível de HTTPS | https://trojan-gfw.github.io/trojan/ |
| **Naïve Proxy** | ✅ Sim | Proxy | Baseado em Chrome network stack | https://github.com/klzgrad/naiveproxy |
| **Hysteria 2** | ✅ Sim | Proxy | UDP-based, alta velocidade em redes lossy | https://v2.hysteria.network/ |
| **Cloak** | ✅ Sim | Wrapper | Disfarça outros proxies como HTTPS | https://github.com/cbeuw/Cloak |
| **Outline VPN** | ✅ Sim | VPN/proxy | Baseado em Shadowsocks (Jigsaw/Google) | https://getoutline.org/ |
| **Lantern** | Parcial | Proxy | Anti-censura focado em mercados restritos | https://lantern.io/ |
| **Psiphon** | Parcial | Proxy/VPN | Anti-censura clássico | https://psiphon.ca/ |
| **GoodbyeDPI / Zapret / SpoofDPI** | ✅ Sim | DPI bypass | Burlam DPI sem servidor remoto | https://github.com/ValdikSS/GoodbyeDPI |
| **dnstt** | ✅ Sim | Túnel DNS | Túnel TCP sobre DoH/DoT (anti-censura) | https://www.bamsoftware.com/software/dnstt/ |

---

## 54. CRIPTOGRAFIA PÓS-QUÂNTICA E FERRAMENTAS AVANÇADAS

### [Camada 4]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **liboqs** | ✅ Sim | Lib | Biblioteca Open Quantum Safe (Kyber, Dilithium, SPHINCS+) | https://openquantumsafe.org/ |
| **OQS-OpenSSL / OQS-OpenSSH** | ✅ Sim | Fork | OpenSSL/SSH com algoritmos PQC | https://openquantumsafe.org/ |
| **Signal PQXDH** | ✅ Sim | Protocolo | Acordo de chaves híbrido (X25519 + Kyber) já em produção | https://signal.org/docs/specifications/pqxdh/ |
| **PQ3 (Apple iMessage)** | ❌ Não | Protocolo | Acordo PQ híbrido + ratchet em iMessage | — |
| **Cloudflare Post-Quantum TLS** | ✅ Sim | TLS | Suporte experimental em produção | https://blog.cloudflare.com/post-quantum-for-all/ |
| **age + age-plugin-pqc** | ✅ Sim | Arquivos | Plugin PQ para age | — |
| **wolfSSL/wolfCrypt PQ** | Parcial | Lib | Algoritmos PQ em embarcados | — |
| **Botan** | ✅ Sim | Lib | Biblioteca cripto C++ com PQC | https://botan.randombit.net/ |
| **Tink** | ✅ Sim | Lib | Lib do Google com APIs seguras por padrão | https://github.com/tink-crypto/tink |
| **NaCl / libsodium** | ✅ Sim | Lib | API simples para curvas modernas | https://libsodium.org/ |
| **Cryptography.io (Python)** | ✅ Sim | Lib | Lib pythônica recomendada | https://cryptography.io/ |
| **HashiCorp Vault** | ✅ Sim | Cofre | Cofre de segredos para infra, suporte HSM | https://www.vaultproject.io/ |
| **Bitwarden Secrets Manager** | ✅ Sim | Cofre | Secrets para devs/infra | https://bitwarden.com/ |
| **Doppler / Infisical** | Parcial | Cofre | Infisical é open-source | https://infisical.com/ |
| **OpenSSF Sigstore (cosign)** | ✅ Sim | Assinatura | Assinatura keyless de artefatos/SW | https://www.sigstore.dev/ |

---

## 55. AUDITORIA DE APPS E ANÁLISE DE PERMISSÕES

### [Transversal]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **Exodus Privacy** | ✅ Sim | Android/Web | Análise estática | Lista rastreadores e permissões em apps Android | https://exodus-privacy.eu.org/ |
| **TrackerControl** | ✅ Sim | Android | Tempo real | Bloqueio de rastreadores via VPN local | https://trackercontrol.org/ |
| **MobSF (Mobile Security Framework)** | ✅ Sim | Multi | Análise | Análise estática/dinâmica para Android/iOS | https://mobsf.live/ |
| **Pithus** | ✅ Sim | Web | Análise | Sandbox público para APKs | https://beta.pithus.org/ |
| **App Manager** | ✅ Sim | Android | Auditoria | Inspeção avançada de apps Android | F-Droid |
| **Bouncer** | ❌ Não | Android | Permissões | Concede permissões temporárias | Play Store |
| **AppCensus** | — | Web | Análise | Estudos sobre rastreio em apps mobile | https://appcensus.io/ |
| **Privacy Indicator (iOS 14+/Android 12+)** | — | Nativo | UI | Indicadores nativos de mic/câmera/clipboard | — |
| **Oversight (macOS)** | ✅ Sim | macOS | Mic/cam | Notifica quando mic/câmera são usados | https://objective-see.org/products/oversight.html |
| **ReiKey (macOS)** | ✅ Sim | macOS | Keyloggers | Detecta keyloggers no macOS | https://objective-see.org/products/reikey.html |
| **KnockKnock (macOS)** | ✅ Sim | macOS | Persistência | Verifica softwares persistentes | https://objective-see.org/products/knockknock.html |
| **Autoruns (Sysinternals)** | ❌ Não | Windows | Persistência | Lista tudo que inicia com o Windows | — |
| **Process Hacker / System Informer** | ✅ Sim | Windows | Monitor | Substituto avançado do Task Manager | https://systeminformer.sourceforge.io/ |
| **HiddenVM Analyzer** | ✅ Sim | Multi | VM detection | Verifica detecção de VM por malware | — |

---

## 56. SERVIDORES VPN AUTO-HOSPEDADOS

### [Camada 3]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **WireGuard** | ✅ Sim | VPN moderna | Padrão atual: rápido, simples, baseado em Curve25519 | https://www.wireguard.com/ |
| **OpenVPN** | ✅ Sim | VPN clássica | Maduro, TLS, ampla compatibilidade | https://openvpn.net/ |
| **OpenVPN Access Server** | Parcial | VPN | Versão empresarial OpenVPN | — |
| **strongSwan** | ✅ Sim | IKEv2/IPsec | Implementação robusta IPsec | https://www.strongswan.org/ |
| **Libreswan** | ✅ Sim | IPsec | Fork de Openswan | https://libreswan.org/ |
| **PiVPN** | ✅ Sim | Wrapper | Setup automatizado WireGuard/OpenVPN em Linux | https://www.pivpn.io/ |
| **Algo VPN** | ✅ Sim | Provisionador | Provisiona VPN WireGuard em VPS automaticamente | https://github.com/trailofbits/algo |
| **Streisand** | ✅ Sim | Provisionador | Provisiona múltiplos protocolos anti-censura | https://github.com/StreisandEffect/streisand |
| **Outline Server** | ✅ Sim | Shadowsocks | Servidor Shadowsocks gerenciado (Jigsaw) | https://getoutline.org/ |
| **SoftEther** | ✅ Sim | Multi-proto | Suporta L2TP/IPsec/SSTP/OpenVPN/SoftEther | https://www.softether.org/ |
| **Tailscale** | Parcial | Mesh | Rede mesh sobre WireGuard (controle plano fechado) | https://tailscale.com/ |
| **Headscale** | ✅ Sim | Mesh | Implementação open-source do plano de controle Tailscale | https://headscale.net/ |
| **NetBird** | ✅ Sim | Mesh | Alternativa FOSS completa | https://netbird.io/ |
| **Nebula** | ✅ Sim | Mesh | Mesh VPN escalável (Slack) | https://github.com/slackhq/nebula |
| **ZeroTier** | Parcial | SDN | Rede virtual P2P | https://www.zerotier.com/ |
| **Innernet** | ✅ Sim | WireGuard | Rede WireGuard gerenciada por CRDT | https://github.com/tonarino/innernet |
| **WireGuard Easy (wg-easy)** | ✅ Sim | UI | UI Docker simples para WG | https://github.com/wg-easy/wg-easy |

---

## 57. HONEYPOTS E DETECÇÃO DE INTRUSÃO PESSOAL

### [Camada 1/3/4]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **Canarytokens** | ✅ Sim | Tokens | Tokens (URL, doc Office, AWS, etc.) que avisam quando acessados | https://canarytokens.org/ |
| **OpenCanary** | ✅ Sim | Honeypot | Versão FOSS dos Canary Tools | https://github.com/thinkst/opencanary |
| **T-Pot** | ✅ Sim | Bundle | Multi-honeypot da Telekom Security | https://github.com/telekom-security/tpotce |
| **Cowrie** | ✅ Sim | SSH/Telnet | Honeypot SSH/Telnet para capturar atacantes | https://github.com/cowrie/cowrie |
| **Dionaea** | ✅ Sim | Multi-protocolo | Honeypot para coletar malware | https://github.com/DinoTools/dionaea |
| **Honeyd** | ✅ Sim | Network | Honeypot virtual de rede clássico | https://www.honeyd.org/ |
| **Glastopf** | ✅ Sim | Web | Honeypot web (legado) | — |
| **HonSSH / Kippo** | ✅ Sim | SSH | Honeypots SSH | — |
| **Suricata + ELK** | ✅ Sim | IDS/Stack | IDS com visualização Elastic | https://suricata.io/ |
| **Wazuh** | ✅ Sim | XDR/SIEM | EDR/HIDS open-source | https://wazuh.com/ |
| **Security Onion** | ✅ Sim | Distro NSM | Distro Linux para NSM/SIEM | https://securityonionsolutions.com/ |
| **OSSEC** | ✅ Sim | HIDS | HIDS clássico | https://www.ossec.net/ |
| **CrowdSec** | ✅ Sim | Colaborativo | Detecção colaborativa de IPs maliciosos | https://www.crowdsec.net/ |
| **Fail2ban** | ✅ Sim | Bloqueio | Bane IPs após tentativas falhas em logs | https://www.fail2ban.org/ |

---

## 58. COMPARTILHAMENTO DE TELA E ACESSO REMOTO SEGURO

### [Camada 4]

| Ferramenta | Open-Source | Plataformas | Tipo | Diferencial | Link |
|---|---|---|---|---|---|
| **RustDesk** | ✅ Sim | Multi | Acesso remoto | Alternativa FOSS ao TeamViewer/AnyDesk, auto-hospedável | https://rustdesk.com/ |
| **MeshCentral** | ✅ Sim | Multi | Acesso remoto | Servidor web auto-hospedado para gerência remota | https://meshcentral.com/ |
| **Apache Guacamole** | ✅ Sim | Web | Gateway | Acesso a SSH/RDP/VNC via navegador | https://guacamole.apache.org/ |
| **TigerVNC / TightVNC** | ✅ Sim | Multi | VNC | Implementações VNC clássicas (use com SSH tunnel) | https://tigervnc.org/ |
| **NoMachine** | ❌ Não | Multi | Remote desktop | Performance alta, gratuito para uso pessoal | https://www.nomachine.com/ |
| **xrdp** | ✅ Sim | Linux | RDP | Servidor RDP para Linux | https://www.xrdp.org/ |
| **AnyDesk** | ❌ Não | Multi | Remote desktop | Comercial popular | — |
| **TeamViewer** | ❌ Não | Multi | Remote desktop | Comercial popular. ⚠️ Histórico de incidentes | — |
| **Chrome Remote Desktop** | ❌ Não | Multi | Remote desktop | Simples, requer conta Google | — |
| **OpenSSH (ssh -X / sshfs)** | ✅ Sim | Multi | SSH/X11 | Túneis seguros e GUI remota | https://www.openssh.com/ |
| **Mosh** | ✅ Sim | Multi | SSH resiliente | SSH para conexões instáveis | https://mosh.org/ |
| **Tactical RMM** | ✅ Sim | Multi | RMM | Ferramenta auto-hospedada de RMM | https://docs.tacticalrmm.com/ |

---

## 59. GERENCIAMENTO DE IDENTIDADE E SSO PRIVADO

### [Camada 4]

| Ferramenta | Open-Source | Tipo | Diferencial | Link |
|---|---|---|---|---|
| **Keycloak** | ✅ Sim | IdP/SSO | OIDC/SAML/LDAP, padrão da indústria FOSS | https://www.keycloak.org/ |
| **Authentik** | ✅ Sim | IdP/SSO | UI moderna, fluxos customizáveis | https://goauthentik.io/ |
| **Authelia** | ✅ Sim | SSO/2FA | Camada de auth em frente a reverse proxies | https://www.authelia.com/ |
| **Zitadel** | ✅ Sim | IdP/SSO | OIDC + SaaS auto-hospedável | https://zitadel.com/ |
| **Ory Kratos / Hydra** | ✅ Sim | IdP/Stack | Stack modular para identidade | https://www.ory.sh/ |
| **Casdoor** | ✅ Sim | IdP/SSO | UI completa com social logins | https://casdoor.org/ |
| **LemonLDAP::NG** | ✅ Sim | SSO | SSO veterano francês | https://lemonldap-ng.org/ |
| **FreeIPA** | ✅ Sim | Identity | Identity management para Linux/UNIX | https://www.freeipa.org/ |
| **OpenLDAP** | ✅ Sim | Diretório | LDAP server clássico | https://www.openldap.org/ |
| **Samba AD** | ✅ Sim | AD | Implementação livre de AD | https://www.samba.org/ |
| **vouch-proxy / oauth2-proxy** | ✅ Sim | Proxy auth | Adiciona OIDC a qualquer reverse proxy | https://github.com/oauth2-proxy/oauth2-proxy |
| **Pomerium** | ✅ Sim | ZTNA | Proxy zero-trust com policy engine | https://www.pomerium.com/ |
| **Cloudflare Access (Zero Trust)** | ❌ Não | ZTNA | ZTNA gerenciado | https://www.cloudflare.com/zero-trust/ |
| **passkeys.io / SimpleWebAuthn** | ✅ Sim | WebAuthn | Suporte a passkeys em apps próprios | https://simplewebauthn.dev/ |

---

## 60. FERRAMENTAS DE CONSCIENTIZAÇÃO E EDUCAÇÃO

### [Transversal]

| Recurso | Tipo | Diferencial | Link |
|---|---|---|---|
| **EFF Surveillance Self-Defense** | Guia | Guias de autodefesa digital, em PT-BR | https://ssd.eff.org/pt-br |
| **Privacy Guides** | Diretório | Recomendações curadas de ferramentas | https://www.privacyguides.org/ |
| **Awesome Privacy** | Diretório | Lista colaborativa de ferramentas | https://awesome-privacy.xyz/ |
| **Awesome Selfhosted** | Diretório | Lista de software para auto-hospedagem | https://awesome-selfhosted.net/ |
| **Privacy Tools (clássico)** | Diretório | Listas históricas (use com cautela, datado) | https://www.privacytools.io/ |
| **PRISM Break** | Diretório | Alternativas a serviços vigiados | https://prism-break.org/ |
| **Reset The Net** | Campanha | Campanha histórica EFF | https://resetthenet.org/ |
| **Security Planner (Consumer Reports)** | Quiz | Plano personalizado de segurança | https://securityplanner.consumerreports.org/ |
| **Citizen Lab** | Pesquisa | Pesquisas sobre vigilância e censura | https://citizenlab.ca/ |
| **Access Now Helpline** | Suporte | Linha direta para ativistas em risco | https://www.accessnow.org/help/ |
| **CryptoParty** | Movimento | Workshops presenciais de cripto | https://www.cryptoparty.in/ |
| **Tactical Tech (Data Detox Kit)** | Curso | Curso de "detox" digital | https://datadetoxkit.org/ |
| **Tor Project — Training** | Material | Materiais oficiais para treinamentos | https://community.torproject.org/training/ |
| **CISA Stop Ransomware** | Guia | Guia oficial dos EUA contra ransomware | https://www.cisa.gov/stopransomware |
| **CERT.br** | Guia (BR) | Cartilha de Segurança para Internet | https://cartilha.cert.br/ |
| **gov.br Cibersegurança** | Guia (BR) | Recomendações oficiais do governo brasileiro | https://www.gov.br/governodigital/pt-br/seguranca-e-protecao-de-dados |
| **ANPD (BR)** | Regulador | Modelos LGPD e orientações | https://www.gov.br/anpd/ |
| **HackTricks / PayloadsAllTheThings** | Wiki | Recursos para defensores entenderem ataques | https://book.hacktricks.xyz/ |
| **TryHackMe / HackTheBox / OverTheWire** | Plataforma | Treinamento prático ofensivo/defensivo | https://tryhackme.com/ |
| **OpenSSF Best Practices Badge** | Padrão | Checklist de boas práticas de segurança em SW | https://www.bestpractices.dev/ |
| **OWASP Top 10 / ASVS / Cheat Sheets** | Padrão | Referências obrigatórias para AppSec | https://owasp.org/ |
| **MITRE ATT&CK** | Framework | Framework de táticas e técnicas adversárias | https://attack.mitre.org/ |
| **NIST CSF 2.0** | Framework | Framework de cibersegurança do NIST | https://www.nist.gov/cyberframework |
| **CIS Controls / Benchmarks** | Padrão | Controles e baselines de hardening | https://www.cisecurity.org/ |

---

## DIRETRIZES GERAIS

### Regra 3-2-1 de Backup
Mantenha 3 cópias dos dados, em 2 tipos de mídia diferentes, com 1 cópia offsite.

### Higiene de Senhas
- Use gerenciador de senhas (nunca reutilize senhas)
- Ative 2FA em todas as contas (preferencialmente TOTP ou FIDO2, nunca SMS)
- Senhas com 14+ caracteres, aleatórias

### Modelo de Ameaça
Antes de escolher ferramentas, avalie: Quem são seus adversários? Quais dados proteger? Qual seu nível de tolerância a inconveniência?

### Defense in Depth
Nenhuma ferramenta isolada resolve tudo. Combine: navegador seguro + VPN + DNS criptografado + 2FA + gerenciador de senhas + criptografia de disco.

### Atualizações
Ferramentas desatualizadas são piores do que não tê-las. Mantenha TUDO atualizado.

### Princípio do Menor Privilégio
Apps e usuários devem ter apenas as permissões estritamente necessárias. Revise permissões de apps mensalmente, especialmente em mobile.

### Compartimentalização
Separe identidades por contexto (trabalho, pessoal, financeiro, anonimato). Use perfis de navegador, containers, contas/aliases de e-mail e até dispositivos diferentes quando o modelo de ameaça exigir.

### Verificação de Integridade
Sempre verifique assinaturas GPG/SHA256 de software baixado, especialmente de ferramentas críticas (Tor, Tails, VeraCrypt, sistemas operacionais).

### Plano de Resposta a Incidentes Pessoal
Tenha definido: (1) como revogar acessos rapidamente, (2) lista de contas críticas e onde estão os 2FA backup codes, (3) contato de confiança, (4) procedimento de wipe remoto de dispositivos.

### Avalie a Cadeia de Suprimentos
Prefira ferramentas open-source auditadas, com builds reprodutíveis e múltiplos mantenedores. Desconfie de ferramentas adquiridas recentemente por grandes grupos sem histórico transparente.

### Higiene de Metadados
Lembre-se: o conteúdo pode estar criptografado, mas metadados (quem, quando, onde, com quem) muitas vezes não estão. Considere isso ao escolher ferramentas.

---

> **Referência:** Este documento é material de apoio para o CyberShield e deve ser mantido atualizado conforme novas ferramentas, auditorias e incidentes sejam publicados. Última revisão: Abril 2026 (v4.0).