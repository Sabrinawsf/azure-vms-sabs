# 💡 Dicas, Erros Comuns e Questões Frequentes no Azure VM

Este documento reúne dicas essenciais, erros comuns e respostas a perguntas frequentes para ajudar na administração segura e eficiente de máquinas virtuais no Azure.

---

## 🔧 1. Desired State Configuration (DSC)

- **O que é:** Uma extensão para garantir que as VMs estejam configuradas conforme o padrão desejado.
- **Importante:**  
  - Deve ser implantada em VMs Linux e Windows.  
  - Automatiza a configuração e manutenção dos servidores.
- **Dica:** Use DSC para padronizar configurações e evitar divergências manuais.

---

## 🔐 2. Métodos de Autenticação

| Contexto                         | Método recomendado                    |
|---------------------------------|-------------------------------------|
| VMs Linux em produção            | Par de chaves SSH                    |
| VMs Linux em ambientes restritos | Chave privada com senha             |
| VMs Windows                     | RDP com senha forte ou Azure Bastion |

- **Evite o uso de senhas simples ou exposição de portas SSH/RDP ao público.**

---

## 🛡️ 3. Uso do Azure Bastion

- Permite acesso seguro via portal, sem abrir portas SSH ou RDP.
- Ideal para políticas de segurança restritivas.
- Facilita o acesso remoto sem IP público.

---

## ⚠️ 4. Backup e Recuperação

- A Microsoft não configura backup automaticamente para suas VMs.
- **Você é responsável por configurar e gerenciar backups.**
- Use Azure Backup para criar políticas de recuperação e retenção.

---

## ❌ 5. Erros Comuns e Como Evitar

| Erro                                | Solução                              |
|------------------------------------|------------------------------------|
| SSH não conecta                     | Verifique regras NSG e chaves SSH  |
| RDP não funciona                   | Confirme IP, NSG, e firewall local |
| Máquina desliga inesperadamente    | Verifique alertas de manutenção e limites de quota |
| Usar Spot em produção               | Evite Spot para workloads críticas |

---

## 📊 6. Políticas e Responsabilidades

- Microsoft garante a infraestrutura física, energia e rede.
- Usuário gerencia SO, atualizações, segurança e backups.
- Configure NSGs para controlar tráfego e proteger suas VMs.

---

## 🤔 7. Perguntas Frequentes (FAQ)

**Q:** Qual a vantagem do Azure Bastion?  
**A:** Acesso seguro sem expor portas à internet.

**Q:** O que são domínios de falha e atualização?  
**A:** Domínios de falha isolam hardware para evitar pontos únicos de falha; domínios de atualização permitem atualizações em partes da infraestrutura sem downtime total.

**Q:** Como o auto scaling ajuda no custo?  
**A:** Escala as VMs conforme a demanda, evitando custos com recursos ociosos.

**Q:** Posso usar máquinas Spot em produção?  
**A:** Não recomendado, pois podem ser desalocadas a qualquer momento.

---

## Próxima etapa

➡️ Explore também: [Referências e Recursos Úteis](7-referencias.md)
