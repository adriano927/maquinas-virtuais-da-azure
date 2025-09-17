# maquinas-virtuais-da-azure
As Máquinas Virtuais (VMs) da Azure são um dos recursos mais usados dentro do modelo de IaaS (Infraestrutura como Serviço), permitindo a criação de ambientes altamente configuráveis na nuvem, semelhantes a servidores físicos tradicionais, mas com escalabilidade, flexibilidade e cobrança sob demanda.

🔹 Conceitos Fundamentais

IaaS (Infraestrutura como Serviço): o usuário gerencia o sistema operacional, aplicativos, middleware e dados; a Microsoft gerencia hardware e infraestrutura.

Tamanho da VM (SKU): define a capacidade de CPU, memória, armazenamento e rede.

Famílias de VM: otimizadas para diferentes cargas de trabalho (ex.: General Purpose, Compute Optimized, Memory Optimized, GPU, High Performance Computing).

Imagens: sistemas operacionais prontos para uso (Windows Server, Linux, distribuições específicas, etc.).

Discos:

OS Disk (sistema operacional)

Data Disks (armazenamento adicional)

Temporary Disk (armazenamento volátil, geralmente no drive D: em Windows)

🔹 Cenários de Uso

Hospedar aplicações legadas que não foram migradas para PaaS.

Criar ambientes de teste/desenvolvimento rapidamente.

Rodar aplicações personalizadas que exigem controle total do sistema operacional.

Executar bancos de dados em cenários IaaS (quando PaaS não é aplicável).

Suporte a cargas de trabalho que precisam de GPU (machine learning, renderização, IA).

🔹 Benefícios

✔️ Flexibilidade de sistema operacional (Windows/Linux)
✔️ Escalabilidade (aumentar ou reduzir recursos sob demanda)
✔️ Integração nativa com rede virtual, balanceadores e storage
✔️ Alta disponibilidade por meio de Availability Sets e Availability Zones
✔️ Backup e monitoramento integrados com ferramentas da Azure

🔹 Custos e Otimização

Preço baseado em consumo (horas rodadas + recursos utilizados).

Opções de Reserved Instances (1 ou 3 anos) para reduzir custos até 70%.

Uso de Azure Hybrid Benefit para economizar licenças Windows/SQL.

Auto-shutdown em VMs de desenvolvimento/teste para evitar cobrança desnecessária.

🔹 Alta Disponibilidade e Escalabilidade

Availability Set: distribui VMs em diferentes domínios de falha e atualização.

Availability Zones: garante resiliência ao rodar VMs em diferentes datacenters da mesma região.

VM Scale Sets: permite criar e gerenciar um conjunto de VMs idênticas, com escalabilidade automática.

🔹 Gerenciamento e Automação

Portal Azure – interface gráfica.

Azure CLI e PowerShell – automação de criação e gerenciamento.

ARM Templates / Bicep – infraestrutura como código.

Terraform – automação multiplataforma para ambientes híbridos/multicloud.

# Criar um grupo de recursos
az group create --name rg-vm-exemplo --location eastus

# Criar uma VM Linux
az vm create \
  --resource-group rg-vm-exemplo \
  --name vm-linux01 \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys

