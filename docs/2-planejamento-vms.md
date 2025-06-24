# 🛠️ Planejamento de Máquinas Virtuais no Azure

Antes de criar uma Máquina Virtual (VM) no Azure, é fundamental realizar um bom planejamento para garantir desempenho, segurança e economia. Esta etapa inicial define o sucesso da sua infraestrutura na nuvem.

---

## 🧭 1. Comece pela Rede

Antes mesmo da criação da VM:

- Planeje **qual rede virtual (VNet)** será usada.
- Configure **sub-redes** apropriadas.
- Avalie a necessidade de **grupos de segurança de rede (NSG)**.
- Verifique se será necessário acesso remoto (SSH/RDP) e defina regras.

---

## 🧾 2. Nome da Máquina Virtual

- Use **nomes padronizados e descritivos**.
  - Exemplo: `vm-web-prod-br01`
- Nomear bem ajuda no gerenciamento, automação e cobrança.

---

## 🌍 3. Escolha da Região (Location)

A escolha da região impacta:

- **Desempenho:** escolha a região mais próxima dos usuários finais.
- **Conformidade:** algumas regiões são exigidas por leis locais (ex: LGPD).
- **Custo:** os preços variam entre regiões.

📍 **Dica:** Consulte o [mapa de regiões do Azure](https://azure.microsoft.com/pt-br/explore/global-infrastructure/geographies/)

---

## ⚙️ 4. Dimensionamento da Máquina Virtual (SKU)

### Tipos de SKUs:

| Série | Indicação |
|-------|-----------|
| B     | Baixo custo, cargas intermitentes |
| D     | Uso geral, aplicações de produção |
| E     | Memória otimizada |
| F     | CPU otimizada |
| N     | Processamento gráfico (GPU) |

📌 Escolha com base em:
- CPU
- Memória
- Tipo de carga de trabalho

---

## 💽 5. Armazenamento da Máquina Virtual

Cada VM pode ter:

- **Disco do SO:** Armazena o sistema operacional.
- **Disco temporário:** Armazenamento volátil (limpo em reinicializações).
- **Discos de dados (opcionais):** Para armazenar arquivos e aplicações.

### Tipos de disco:

| Tipo        | Indicado para           |
|-------------|--------------------------|
| HDD         | Arquivos de baixo custo |
| SSD         | Uso geral               |
| SSD Premium | Alto desempenho         |
| Ultra SSD   | Workloads críticos      |

---

## 🔐 6. Autenticação

### Máquinas Linux
- **Recomendado:** Par de chaves SSH.
- Evite senhas, especialmente em produção.

### Máquinas Windows
- RDP com senha forte.
- Azure Bastion (veremos adiante) é o método mais seguro para acesso remoto.

---

## ✅ Boas Práticas

- Sempre **tagueie** suas VMs com informações como ambiente, dono e projeto.
- Planeje o uso de **extensões**, como o **Desired State Configuration (DSC)**, para manter a configuração padronizada.
- Evite o uso de **máquinas Spot** em ambientes de produção, pois podem ser desalocadas a qualquer momento.

---

## Próxima etapa

➡️ Continue para: [Configuração e Conexão](3-configuracao-e-conexao.md)
