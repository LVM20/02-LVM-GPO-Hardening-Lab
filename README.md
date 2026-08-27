# 🛡️ Projeto 02 — Group Policy & Windows Hardening Lab

Laboratório corporativo virtualizado desenvolvido para praticar **Group Policy, Windows Hardening, segurança de endpoints, auditoria e administração centralizada** em um ambiente Windows baseado em **Active Directory**.

O projeto representa a segunda etapa da infraestrutura da **LVM Technologies**, utilizando o domínio criado no Projeto 01 para aplicar políticas de segurança de forma centralizada às estações Windows.

O objetivo foi aproximar o ambiente de uma infraestrutura corporativa real, estabelecendo controles de segurança e preparando os endpoints para as etapas posteriores de **Wazuh, Sysmon, Threat Hunting e Incident Response**.

> **Aviso:** todas as configurações foram realizadas em ambiente virtualizado e controlado, exclusivamente para fins educacionais.

---

## 🎯 Objetivo

O objetivo deste projeto foi implementar uma camada de **Hardening e controle centralizado** utilizando Group Policy Objects (GPOs).

Durante o projeto foram praticados:

* Criação e gerenciamento de GPOs;
* Aplicação de políticas de segurança;
* Centralização de configurações;
* Password Policy;
* Account Lockout Policy;
* Login Banner;
* Corporate Wallpaper;
* Windows Defender;
* Windows Firewall;
* User Restrictions;
* Advanced Audit Policy;
* Validação das políticas nos endpoints;
* Auditoria de eventos de segurança;
* Preparação da infraestrutura para monitoramento através de SIEM.

---

# 🏗️ Ambiente do laboratório

O laboratório utiliza a infraestrutura criada no **Projeto 01 — Active Directory Corporate Lab**.

### Domínio

```text
lvm.local
```

### Rede

```text
10.10.10.0/24
```

### Controlador de domínio

```text
DC01
10.10.10.10
```

---

## 🖥️ Infraestrutura

| Host     | Função                               | Endereço IP   |
| -------- | ------------------------------------ | ------------- |
| **DC01** | Active Directory + DNS + File Server | `10.10.10.10` |
| **WS01** | Recursos Humanos                     | `10.10.10.20` |
| **WS02** | Financeiro                           | `10.10.10.21` |
| **WS03** | Tecnologia da Informação             | `10.10.10.22` |
| **WS04** | Diretoria                            | `10.10.10.23` |

As estações Windows foram utilizadas para validar a aplicação das políticas de segurança centralizadas através do domínio.

---

# 🧱 Arquitetura

A estrutura de políticas foi construída sobre o Active Directory:

```text
                         LVM Technologies
                               │
                         Active Directory
                               │
                              DC01
                         10.10.10.10
                               │
                        Group Policy
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
        WS01                 WS02                 WS03
         RH               Financeiro                TI
   10.10.10.20          10.10.10.21          10.10.10.22
          │                    │                    │
          └────────────────────┼────────────────────┘
                               │
                              WS04
                           Diretoria
                         10.10.10.23
```

As configurações foram distribuídas centralmente pelo domínio, permitindo padronizar controles de segurança entre os endpoints.

---

# 🔧 Group Policy Objects

Foram utilizadas políticas relacionadas a diferentes áreas de segurança:

```text
LVM.local
│
├── Default Domain Policy
│
├── Password Policy
├── Account Lockout Policy
├── Login Banner
├── Corporate Wallpaper
├── Windows Defender
├── Windows Firewall
├── User Restrictions
└── Advanced Audit Policy
```

As GPOs permitiram centralizar configurações que, em um ambiente corporativo, poderiam ser aplicadas a múltiplos computadores e usuários simultaneamente.

---

# 🔐 Políticas de segurança implementadas

## 🔑 Password Policy

Foi configurada uma política corporativa de senhas contendo controles como:

* Complexidade de senha;
* Comprimento mínimo;
* Histórico de senhas;
* Expiração de senha.

### Objetivo

Reduzir a utilização de credenciais fracas e aumentar a segurança da autenticação dos usuários do domínio.

---

## 🚫 Account Lockout Policy

Foi configurado o bloqueio de contas após múltiplas tentativas de autenticação inválidas.

Foram considerados:

* Número de tentativas inválidas;
* Tempo de bloqueio;
* Reset do contador de tentativas.

### Objetivo

Reduzir o risco de ataques baseados em tentativas repetidas de autenticação.

---

## 🏢 Login Banner

Foi implementado um aviso corporativo apresentado antes da autenticação.

### Objetivo

Informar ao usuário que o equipamento pertence ao ambiente corporativo e que sua utilização está sujeita às políticas da organização.

---

## 🖼️ Corporate Wallpaper

Foi implementada a padronização visual das estações através de Group Policy.

### Objetivo

Demonstrar a capacidade de aplicar configurações centralizadas aos endpoints do domínio.

---

## 🛡️ Windows Defender

Foram aplicadas configurações centralizadas relacionadas ao Windows Defender.

Entre os controles utilizados:

* Proteção em tempo real;
* Configurações de proteção;
* Gerenciamento através de Group Policy.

### Objetivo

Garantir uma configuração de segurança padronizada nos endpoints Windows.

---

## 🔥 Windows Firewall

Foram configurados os perfis:

```text
Domain
Private
Public
```

Entre as configurações utilizadas:

* Firewall habilitado;
* Bloqueio de conexões de entrada;
* Registro de eventos;
* Registro de pacotes descartados.

### Objetivo

Reduzir a superfície de ataque dos endpoints e aumentar a visibilidade sobre conexões bloqueadas.

---

## 👤 User Restrictions

Foram aplicadas restrições para usuários comuns.

Entre os controles utilizados:

* Restrição do Prompt de Comando;
* Restrição do Painel de Controle;
* Limitação de configurações administrativas.

### Objetivo

Reduzir alterações não autorizadas e limitar o acesso de usuários comuns a recursos administrativos.

---

# 📊 Advanced Audit Policy

Foram configuradas categorias de auditoria do Windows relacionadas a:

* Account Logon;
* Logon/Logoff;
* Account Management;
* Detailed Tracking;
* Policy Change;
* Directory Service Access.

Essas configurações aumentaram a quantidade de informações disponíveis no **Windows Event Log**, criando uma base de telemetria para os projetos posteriores de monitoramento.

---

# 🧪 Validação e testes

Após a implementação das GPOs, foram realizados testes diretamente nos endpoints para verificar se as políticas estavam sendo aplicadas corretamente.

### Password Policy

Foram realizados testes para validar:

* Requisitos de complexidade;
* Comprimento mínimo;
* Histórico de senhas;
* Políticas de expiração.

### Account Lockout

Foi validado:

* Bloqueio após tentativas inválidas;
* Contagem das tentativas;
* Aplicação da política aos usuários.

### Login Banner

Foi validada a apresentação do banner antes da autenticação.

### Corporate Wallpaper

Foi validada a aplicação automática do papel de parede corporativo.

### Windows Defender

Foi validado:

* Estado da proteção;
* Aplicação das configurações;
* Gerenciamento centralizado.

### Windows Firewall

Foram validados:

* Perfis de firewall;
* Estado do firewall;
* Bloqueio de conexões;
* Geração de logs.

### User Restrictions

Foram testadas:

* Restrição do Prompt de Comando;
* Restrição do Painel de Controle;
* Aplicação das configurações aos usuários.

### Advanced Audit Policy

Foi utilizado o Event Viewer para validar a geração dos eventos de auditoria.

---

# 📡 Auditoria e telemetria

A configuração das políticas de auditoria teve como objetivo aumentar a visibilidade sobre atividades realizadas nos endpoints.

A telemetria posteriormente utilizada nos projetos de segurança inclui eventos relacionados a:

```text
Authentication
     ↓
Logon / Logoff
     ↓
Account Management
     ↓
Process Creation
     ↓
Policy Changes
```

Essa camada de auditoria foi importante para preparar o ambiente para a implementação posterior do **Wazuh SIEM e Sysmon**.

---

# ⚙️ Funcionalidades implementadas

* ✅ Password Policy
* ✅ Account Lockout Policy
* ✅ Login Banner
* ✅ Corporate Wallpaper
* ✅ Windows Defender
* ✅ Windows Firewall
* ✅ User Restrictions
* ✅ Advanced Audit Policy
* ✅ Centralização das configurações através de GPO
* ✅ Hardening das estações Windows
* ✅ Auditoria de eventos de segurança
* ✅ Preparação para monitoramento por SIEM

---

# 📸 Evidências

As evidências do projeto estão organizadas no diretório:

```text
evidencias/
```

As capturas incluem evidências relacionadas a:

* Estrutura das GPOs;
* Password Policy;
* Account Lockout;
* Login Banner;
* Corporate Wallpaper;
* Windows Defender;
* Windows Firewall;
* User Restrictions;
* Advanced Audit Policy;
* Event Viewer;
* Testes de validação.

---

# 📄 Relatório técnico

O relatório técnico completo está disponível em:

```text
/relatorio
```

O documento apresenta os detalhes da implementação, configurações realizadas, testes, evidências e resultados obtidos durante o projeto.

---

# ⚠️ Limitações

Como se trata de um laboratório educacional, o ambiente possui limitações em relação a uma infraestrutura corporativa de grande escala.

Entre elas:

* Número reduzido de endpoints;
* Estrutura simplificada de usuários e departamentos;
* Ausência de múltiplos controladores de domínio;
* Ausência de infraestrutura redundante;
* Políticas aplicadas em ambiente controlado;
* Ausência de uma baseline corporativa completa.

O objetivo principal foi desenvolver conhecimento prático em **Group Policy e Windows Hardening**, e não reproduzir integralmente uma infraestrutura empresarial de produção.

---

# 📈 Resultados

Ao final do projeto foi possível validar:

* ✅ Administração centralizada através de GPO;
* ✅ Políticas de senha;
* ✅ Bloqueio de contas após tentativas inválidas;
* ✅ Banner corporativo;
* ✅ Padronização visual;
* ✅ Configurações centralizadas do Windows Defender;
* ✅ Windows Firewall;
* ✅ Restrições para usuários comuns;
* ✅ Auditoria avançada de eventos;
* ✅ Aplicação das políticas nos endpoints;
* ✅ Validação através do Event Viewer;
* ✅ Preparação do ambiente para Wazuh e Sysmon.

---

# 🧠 Competências desenvolvidas

Durante o projeto foram praticadas competências relacionadas a:

### Windows Administration

* Group Policy;
* Administração centralizada;
* Windows Server;
* Gerenciamento de endpoints;
* Troubleshooting.

### Windows Security

* Password Policy;
* Account Lockout;
* Windows Defender;
* Windows Firewall;
* Security Auditing;
* Event Viewer.

### Active Directory

* GPO;
* Domain Policies;
* User Policies;
* Computer Policies;
* Administração centralizada.

### Blue Team

* Windows Hardening;
* Security Baseline;
* Audit Policy;
* Security Monitoring;
* Preparação de telemetria.

---

# 🚀 Próximas evoluções

O ambiente desenvolvido neste projeto serviu como base para as etapas seguintes do laboratório.

As próximas evoluções incluem:

* Wazuh SIEM;
* Sysmon;
* Threat Hunting;
* Windows Detection;
* Incident Response;
* Vulnerability Management;
* Identity & Access Management;
* Network Security;
* Detection Engineering;
* Security Automation.

---

# 🗂️ Estrutura do projeto

```text
02-LVM-GPO-Windows-Hardening/
│
├── README.md
│
├── evidencias/
│
└── relatorio/
    └── relatorio_gpos.pdf
```

---

# 🏁 Conclusão

O **Projeto 02 — Group Policy & Windows Hardening Lab** adicionou uma camada de segurança centralizada à infraestrutura criada no Projeto 01.

A utilização de **Group Policy** permitiu aplicar políticas de segurança de maneira padronizada aos endpoints Windows, incluindo controles relacionados a **senhas, bloqueio de contas, Windows Defender, Windows Firewall, restrições de usuários e auditoria de eventos**.

A implementação também demonstrou a importância de combinar **administração centralizada e hardening** com mecanismos de auditoria capazes de gerar telemetria para futuras investigações.

Além de fortalecer a infraestrutura, o projeto preparou os endpoints para a próxima etapa do laboratório: **monitoramento através de Wazuh e Sysmon**, permitindo evoluir da configuração preventiva para a detecção e investigação de comportamentos suspeitos.

---

## 📌 Status

```text
Projeto: Group Policy & Windows Hardening Lab
Status: Concluído
Ambiente: Laboratório corporativo virtualizado
Domínio: lvm.local
DC: DC01
Resultado: Políticas de segurança implementadas e validadas
```

---

## 👨‍💻 Autor

**Leonardo Poncham**

**Foco:** Cybersecurity | Windows | Active Directory | Hardening | Blue Team
