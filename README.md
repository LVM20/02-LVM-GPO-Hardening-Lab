# 🛡️ LVM Technologies – Group Policy (GPO) & Windows Hardening Lab

## 📌 Descrição

Este projeto simula a implementação de políticas de segurança em um ambiente corporativo baseado em **Windows Server 2025** e **Active Directory**, utilizando **Group Policy Objects (GPOs)** para centralizar configurações, fortalecer a segurança das estações de trabalho e padronizar o ambiente.

O laboratório foi desenvolvido como continuidade do **Active Directory Corporate Lab**, aproximando a infraestrutura de práticas comuns encontradas em organizações que utilizam tecnologias Microsoft.

---

# 🎯 Objetivo

Implementar políticas de grupo para fortalecer a segurança do ambiente Windows e preparar a infraestrutura para futuras etapas de monitoramento, detecção e resposta a incidentes.

Principais objetivos:

* Aplicar políticas de senha e autenticação
* Implementar hardening em estações Windows
* Centralizar configurações de segurança
* Configurar auditoria de eventos
* Preparar o ambiente para integração com Sysmon e Wazuh

---

# 🖥️ Ambiente

| Máquina  | Função                                  |
| -------- | --------------------------------------- |
| **DC01** | Windows Server 2025 (Domain Controller) |
| **WS01** | Windows 10 ingressado no domínio        |

**Domínio**

```text
lvm.local
```

---

# 🔧 GPOs Implementadas

## Default Domain Policy

* ✅ Password Policy
* ✅ Account Lockout Policy

---

## GPOs do Domínio

* ✅ Login Banner
* ✅ Corporate Wallpaper
* ✅ Windows Defender
* ✅ Windows Firewall

---

## GPOs da OU Workstations

* ✅ User Restrictions
* ✅ Advanced Audit Policy

---

# 🔐 Principais Configurações

## Password Policy

* Complexidade de senha
* Comprimento mínimo
* Histórico de senhas
* Tempo de expiração

---

## Account Lockout

* Bloqueio de contas após múltiplas tentativas inválidas
* Redefinição automática do contador
* Proteção contra ataques de força bruta

---

## Login Banner

Implementação de aviso corporativo exibido antes da autenticação dos usuários.

---

## Corporate Wallpaper

Padronização visual das estações através de papel de parede corporativo aplicado por GPO.

---

## Windows Defender

* Proteção em tempo real
* Configuração centralizada via Group Policy

---

## Windows Firewall

Configuração dos perfis:

* Domínio
* Privado
* Público

Implementações:

* Firewall habilitado
* Bloqueio de conexões de entrada
* Registro de logs
* Registro de pacotes descartados

---

## User Restrictions

Aplicação de restrições para usuários comuns:

* Bloqueio do Prompt de Comando
* Bloqueio do Painel de Controle

---

## Advanced Audit Policy

Configuração de auditoria para geração de eventos de segurança.

Categorias implementadas:

* Logon da Conta
* Logon/Logoff
* Gerenciamento de Contas
* Monitoração Detalhada
* Alteração de Política
* Acesso ao Serviço de Diretório

Preparando o ambiente para monitoramento com SIEM.

---

# ✅ Validação

Foram realizados testes para validar todas as configurações implementadas.

Validações realizadas:

* Login utilizando contas do domínio
* Aplicação da Password Policy
* Bloqueio de contas
* Exibição do Login Banner
* Aplicação do Wallpaper Corporativo
* Windows Defender ativo
* Windows Firewall ativo
* Restrições de usuários funcionando
* Auditoria gerando eventos de segurança

---

# 📸 Evidências

As capturas de tela do laboratório encontram-se disponíveis na pasta:

```text
docs/
```

Incluindo:

* Estrutura das GPOs
* Password Policy
* Account Lockout
* Login Banner
* Corporate Wallpaper
* Windows Defender
* Windows Firewall
* Advanced Audit Policy
* Testes de validação

---

# 📄 Documentação

O relatório técnico completo deste projeto encontra-se disponível em:

```text
docs/relatorio_gpos.pdf
```

---

# 🚀 Próximos Projetos

* 🔄 Sysmon Lab
* 🔄 Wazuh SIEM
* 🔄 Detection Engineering
* 🔄 Incident Response
* 🔄 Vulnerability Management

---

# 👨‍💻 Autor

**Leonardo Poncham**

Este projeto faz parte da construção de um laboratório corporativo voltado ao desenvolvimento de competências em **Blue Team**, **Windows Infrastructure**, **Active Directory** e **SOC Operations**.
