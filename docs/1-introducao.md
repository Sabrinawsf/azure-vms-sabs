# ☁️ Introdução ao Microsoft Azure

## O que é o Azure?

O Microsoft Azure é uma plataforma de computação em nuvem que oferece uma ampla variedade de serviços, como:

- Máquinas Virtuais (VMs)
- Armazenamento em nuvem
- Redes virtuais
- Banco de dados
- Inteligência artificial, entre outros

Esses serviços podem ser usados para **criar, testar, hospedar e gerenciar aplicações** por meio dos datacenters da Microsoft distribuídos globalmente.

---

## Modelos de Serviço na Nuvem

O Azure opera com os seguintes modelos de serviço:

- **IaaS (Infraestrutura como Serviço):** Você gerencia o sistema operacional, os aplicativos, a segurança e os dados. O Azure gerencia o hardware físico, a rede e o datacenter.
- **PaaS (Plataforma como Serviço):** O Azure também gerencia o sistema operacional e middleware. Você foca no desenvolvimento da aplicação.
- **SaaS (Software como Serviço):** O Azure fornece o aplicativo completo pronto para uso, como o Microsoft 365.

---

## Responsabilidade Compartilhada

### ⚖️ Quem faz o quê?

| Elemento                         | Responsabilidade do Cliente | Responsabilidade da Microsoft |
|----------------------------------|------------------------------|-------------------------------|
| Dados e Acesso                   | ✅                            | ❌                            |
| Sistema Operacional              | ✅                            | ❌                            |
| Configuração da Rede             | ✅                            | ❌                            |
| Infraestrutura Física (energia, hardware) | ❌                          | ✅                            |
| Segurança Física do Datacenter  | ❌                            | ✅                            |

🔐 **Importante:** O backup e a segurança do sistema operacional **devem ser configurados por você**. O Azure fornece as ferramentas, mas **não ativa por padrão**.

---

## Principais Vantagens do Azure

- ✅ Escalabilidade sob demanda
- ✅ Alta disponibilidade (SLA de até 99,99%)
- ✅ Redução de custos com infraestrutura local
- ✅ Segurança avançada
- ✅ Flexibilidade para Windows e Linux

---

## Casos de Uso Comuns

- Hospedagem de aplicações web e APIs
- Execução de cargas de trabalho corporativas (banco de dados, ERPs)
- Desenvolvimento e testes
- Backup e recuperação de desastres
- Análise de dados em larga escala

---

## Próxima etapa

➡️ Continue para: [Planejamento de Máquinas Virtuais](2-planejamento-vms.md)
