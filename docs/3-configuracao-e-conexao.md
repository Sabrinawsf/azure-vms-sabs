# 🔗 Conexão com Máquinas Virtuais no Azure

Após criar sua Máquina Virtual (VM), você precisará configurá-la para acesso remoto. Essa conexão pode ser feita por diferentes métodos, dependendo do sistema operacional (Linux ou Windows) e das políticas de segurança da organização.

---

## 🌐 1. Comportamento Padrão de Segurança de Rede

- O **tráfego de saída** é permitido automaticamente.
- O **tráfego de entrada é bloqueado**, exceto quando explicitamente liberado.
- Para permitir conexões (SSH, RDP), você precisa criar **regras NSG** (Network Security Group).

---

## 🐧 2. Conectando-se a VMs Linux

### 🔑 Autenticação

| Método               | Recomendado? | Observações |
|----------------------|--------------|-------------|
| Senha                | ❌           | Menos seguro, deve ser evitado |
| Chave SSH            | ✅           | Mais seguro e recomendado |
| Chave privada com senha | ✅       | Ideal para acesso restrito e seguro |

> **Dica:** Gere um par de chaves SSH localmente e forneça a chave pública durante a criação da VM.

> ### 💻 Conexão via Terminal
> ```bash
ssh -i chave_privada.pem usuario@ip-da-vm'''


3. Conectando-se a VMs Windows
Requer liberação da porta 3389 (RDP) no NSG.

O acesso é feito via Cliente de Área de Trabalho Remota do Windows.

⚠️ Atenção: Expor essa porta diretamente à internet não é recomendado em ambientes de produção.

🛡️ 4. Acesso Seguro com Azure Bastion
O Azure Bastion permite conectar-se a uma VM diretamente pelo portal Azure, sem abrir portas como SSH ou RDP.

Vantagens:
Sem necessidade de IP público.

Não expõe portas sensíveis à internet.

Acesso via navegador, direto pelo portal.

Quando usar?
Quando políticas de segurança proíbem a exposição de portas SSH/RDP.

Para ambientes corporativos com foco em segurança e controle de acesso.

Exemplo de Caso Real
🔐 Sua organização tem uma política que proíbe portas SSH expostas.
✅ Solução recomendada: Configurar o Azure Bastion.

Próxima etapa
➡️ Continue para: [Alta Disponibilidade e Conjuntos](4-disponibilidade.md)




