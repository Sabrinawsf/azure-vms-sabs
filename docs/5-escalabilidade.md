# 📈 Escalabilidade e Auto Scaling no Azure

Escalar sua infraestrutura no Azure permite que ela cresça (ou reduza) conforme a demanda. Isso garante economia, desempenho e disponibilidade.

---

## ⚖️ Tipos de Escalabilidade

| Tipo                | Descrição                                                                 |
|---------------------|---------------------------------------------------------------------------|
| Escalabilidade Vertical (scale-up/down) | Aumentar ou reduzir recursos de uma VM individual (ex: mudar de D2 para D4) |
| Escalabilidade Horizontal (scale-out/in) | Aumentar ou reduzir o número de VMs em uma aplicação |


### ✅ Quando usar:

- **Vertical:** Quando seu app depende de uma única VM potente.
- **Horizontal:** Quando seu app pode funcionar com várias instâncias em paralelo (ex: serviços web, APIs).

---

## 📦 Virtual Machine Scale Set (VMSS)

O **VMSS** permite gerenciar automaticamente um conjunto de VMs idênticas com base em regras de utilização.

### Recursos do VMSS:

- Criação de até **1000 VMs idênticas**
- Integração com **Load Balancer**
- Suporte a **instâncias Spot**
- **Auto Scaling** com base em métricas (CPU, memória etc.)

---

## ⚙️ Parâmetros do Auto Scaling

| Parâmetro        | Descrição                              |
|------------------|----------------------------------------|
| Mínimo           | Número mínimo de instâncias (ex: 1)     |
| Máximo           | Número máximo de instâncias (ex: 10)    |
| Padrão (default) | Número inicial (ex: 2)                  |
| Regras           | Ações baseadas em métricas              |

### Exemplo de regra:

- Se CPU > 85% por 5 minutos → Adiciona 1 VM  
- Se CPU < 15% por 10 minutos → Remove 1 VM

---

## 💡 Instâncias Spot

- Usam **capacidade não utilizada do Azure** com grande desconto.
- Boa opção para cargas **intermitentes e não críticas**.
- **Desvantagem:** Podem ser desalocadas a qualquer momento.

---

## 📐 Estratégias Avançadas

- **Balanceamento de carga automático**
- **Distribuição por zonas de disponibilidade**
- Uso de **templates ARM ou Bicep** para automação

---

## 💬 Cenário Prático

> A empresa quer reduzir custos e escalar automaticamente quando o uso de CPU aumentar.  
> ✅ Solução ideal: VMSS com instâncias Spot + regras de Auto Scaling.

---

## ⚠️ Cuidados

- Defina bem os limites mínimo/máximo para evitar custos excessivos.
- Monitore constantemente com o **Azure Monitor**.
- Use instâncias Spot apenas para workloads tolerantes à interrupção.

---

## Próxima etapa

➡️ Continue para: [Dicas, Erros Comuns e Questões Frequentes](6-dicas.md)
