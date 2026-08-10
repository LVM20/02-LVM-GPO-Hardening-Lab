# 🛡️ LVM Technologies - Group Policy (GPO) & Windows Hardening Lab


---

# 📌 Sobre o Projeto

Este projeto simula a implementação de políticas de segurança em um ambiente corporativo utilizando **Windows Server 2025**, **Active Directory** e **Group Policy Objects (GPOs)**.

Como continuidade do projeto **LVM Technologies - Active Directory Lab**, este laboratório fortalece a segurança da infraestrutura através da centralização de configurações, aplicação de políticas corporativas e implementação de práticas de hardening utilizadas em ambientes Microsoft.

O objetivo é aproximar o laboratório de um ambiente corporativo real e preparar a infraestrutura para futuras integrações com **Sysmon**, **Wazuh SIEM**, **Detection Engineering** e **Incident Response**.

---

# 🎯 Objetivos

- Implementar políticas de segurança utilizando Group Policy.
- Centralizar configurações administrativas.
- Aplicar Hardening nas estações Windows.
- Configurar auditoria de eventos de segurança.
- Padronizar o ambiente corporativo.
- Preparar a infraestrutura para monitoramento com Wazuh e Sysmon.

---

# 🖥️ Infraestrutura

| Host | Função | IP |
|------|---------|-------------|
| DC01 | Active Directory + DNS + File Server | 10.10.10.10 |
| WS01 | Recursos Humanos | 10.10.10.20 |
| WS02 | Financeiro | 10.10.10.21 |
| WS03 | Tecnologia da Informação | 10.10.10.22 |
| WS04 | Diretoria | 10.10.10.23 |

---

# 🌐 Ambiente

### Domínio

```text
lvm.local
```

### Rede

```text
10.10.10.0/24
```

---

# 🏢 Estrutura Organizacional

```text
LVM Technologies

├── Diretoria
├── RH
├── Financeiro
└── TI
```

---

# 🔧 Group Policy Objects (GPOs)

```text
LVM.local

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

---

# 🔐 Implementações

## 🔑 Password Policy

- Complexidade de senha
- Comprimento mínimo
- Histórico de senhas
- Expiração de senha

**Objetivo**

- Reduzir o uso de senhas fracas.
- Melhorar a segurança da autenticação.

---

## 🚫 Account Lockout Policy

- Bloqueio após múltiplas tentativas inválidas
- Reset automático do contador
- Proteção contra ataques de força bruta

---

## 🏢 Login Banner

Implementação de aviso corporativo exibido antes da autenticação dos usuários.

---

## 🖼️ Corporate Wallpaper

Padronização visual das estações Windows utilizando GPO.

---

## 🛡️ Windows Defender

Configuração centralizada de:

- Proteção em tempo real
- Configurações corporativas
- Gerenciamento via Group Policy

---

## 🔥 Windows Firewall

Perfis configurados:

- Domain
- Private
- Public

Implementações:

- Firewall habilitado
- Bloqueio de conexões de entrada
- Registro de logs
- Registro de pacotes descartados

---

## 👤 User Restrictions

Aplicação de restrições para usuários comuns.

Exemplos:

- Bloqueio do Prompt de Comando
- Bloqueio do Painel de Controle
- Restrição de configurações administrativas

---

## 📊 Advanced Audit Policy

Categorias configuradas:

- Account Logon
- Logon/Logoff
- Account Management
- Detailed Tracking
- Policy Change
- Directory Service Access

Essas auditorias serão utilizadas posteriormente para integração com **Sysmon** e **Wazuh SIEM**.

---

# 🧪 Testes Realizados

Foram realizados testes para validar todas as configurações implementadas.

### Password Policy

- Senhas complexas obrigatórias
- Histórico de senhas funcionando

### Account Lockout

- Bloqueio após múltiplas tentativas inválidas

### Login Banner

- Banner corporativo exibido antes do login

### Corporate Wallpaper

- Papel de parede aplicado automaticamente

### Windows Defender

- Proteção ativa
- Configurações centralizadas

### Windows Firewall

- Perfis ativos
- Firewall habilitado

### User Restrictions

- Prompt de Comando bloqueado
- Painel de Controle bloqueado

### Auditoria

- Eventos registrados corretamente no Event Viewer

---

# ✅ Funcionalidades Implementadas

- ✔ Password Policy
- ✔ Account Lockout
- ✔ Login Banner
- ✔ Corporate Wallpaper
- ✔ Windows Defender
- ✔ Windows Firewall
- ✔ User Restrictions
- ✔ Advanced Audit Policy
- ✔ Hardening das estações Windows
- ✔ Preparação para monitoramento via SIEM

---

# 📸 Evidências

As capturas de tela do laboratório encontram-se disponíveis em:

```text
evidencias/
```

Incluindo:

- Estrutura das GPOs
- Password Policy
- Account Lockout
- Login Banner
- Corporate Wallpaper
- Windows Defender
- Windows Firewall
- Advanced Audit Policy
- Testes de validação

---

# 🛠️ Tecnologias Utilizadas

- Windows Server 2025
- Windows 10 Pro
- Active Directory
- DNS
- Group Policy
- Windows Defender
- Windows Firewall
- Event Viewer
- VirtualBox
- Ubuntu Linux

---

# 🚀 Roadmap

- ✅ Projeto 1 – Active Directory Lab
- ✅ Projeto 2 – Group Policy & Windows Hardening
- ⏳ Projeto 3 – Wazuh + Sysmon
- ⏳ Projeto 4 – Detection Engineering
- ⏳ Projeto 5 – Incident Response
- ⏳ Projeto 6 – Vulnerability Management
- ⏳ Projeto 7 – Suricata IDS/IPS
- ⏳ Projeto 8 – pfSense Firewall

---

# 📄 Documentação

O relatório técnico completo deste projeto encontra-se disponível em:

```text
relatorio/relatorio_gpos.pdf
```

---

# 👨‍💻 Autor

**Leonardo Poncham**

---

# ⭐ Objetivo do Laboratório

Este projeto faz parte da construção de um laboratório corporativo voltado ao desenvolvimento de competências em:

- Blue Team
- SOC Operations
- Windows Infrastructure
- Active Directory
- Windows Hardening
- Cyber Defense

Os próximos projetos expandirão esta infraestrutura com monitoramento de eventos, SIEM, detecção de ameaças, gerenciamento de vulnerabilidades e resposta a incidentes.
