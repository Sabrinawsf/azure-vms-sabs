# 🔄 Alta Disponibilidade e Conjuntos no Azure

A alta disponibilidade garante que sua aplicação continue funcionando mesmo em casos de falhas ou manutenções. No Azure, isso é possível com conjuntos de disponibilidade, zonas de disponibilidade e escalabilidade.

---

## 🛠️ 1. Tipos de Manutenção e Falha

### 🔧 Manutenção Planejada
- Realizada pela Microsoft para atualizar a plataforma.
- Impacto mínimo ou nulo.
- Ações recomendadas: nenhuma.

### 🚨 Manutenção de Hardware Não Planejada
- A plataforma detecta falhas iminentes.
- Ação: **migração ao vivo da VM**.

### ⚠️ Tempo de Inatividade Inesperado
- Falhas inesperadas na VM.
- Ação: **reparo automático pela plataforma**.

---

## 🧱 2. Conjuntos de Disponibilidade (Availability Sets)

Agrupam VMs para que sejam distribuídas fisicamente entre:

- **Domínios de Falha (Fault Domains):** racks físicos diferentes.
- **Domínios de Atualização (Update Domains):** grupos que são atualizados separadamente durante manutenções.

### Vantagens:

- SLA de 99,95% com 2 ou mais VMs.
- Maior resiliência a falhas de hardware e atualizações.

### Boas práticas:

- Use discos gerenciados.
- Coloque cada camada do aplicativo (web, app, banco) em conjuntos separados.
- Combine com um **balanceador de carga**.

---

## 🌍 3. Zonas de Disponibilidade

- **Localizações físicas (data centers) distintas** dentro de uma região do Azure.
- Alta disponibilidade geográfica.
- SLA de 99,99%.

### Benefícios:

- Protege contra falhas de data center completo.
- Inclui alimentação, resfriamento e rede independentes.

---

## 📊 4. Escalabilidade: Vertical vs Horizontal

| Tipo de Escala | Definição                                      | Exemplo |
|----------------|------------------------------------------------|---------|
| Escala Vertical | Aumentar o poder de uma única VM (mais CPU, RAM) | Trocar de SKU |
| Escala Horizontal | Adicionar mais instâncias da mesma VM           | Usar VMSS |

📌 **Nota:** Escala vertical é manual. Escala horizontal pode ser automatizada com regras de auto scale.

---

## 📦 5. Virtual Machine Scale Sets (VMSS)

Permite criar e gerenciar um grupo de VMs idênticas, com:

- **Auto Scaling** baseado em métricas (ex: uso de CPU)
- **Balanceamento de carga automático**
- Redução de custos com instâncias **Spot**

### Exemplo de regras de escala:

- CPU > 85% → adiciona VM
- CPU < 15% → remove VM

### Parâmetros configuráveis:

- Tamanho da instância
- Número mínimo, máximo e padrão de VMs
- Estratégia de balanceamento

---

## 💬 Exemplos práticos

- Serviço com falhas frequentes:
  > ✅ Solução: Criar conjunto de disponibilidade + balanceador de carga.

- App independente escalável:
  > ✅ Solução: Criar um VMSS com auto scaling configurado.

---

## Próxima etapa

➡️ Continue para: [Escalabilidade e Auto Scaling](5-escalabilidade.md)
