# Microsoft-50anos.1.1
Configurando um banco de dados com AZURE
 1. O que é uma VM no Azure?
Uma VM (Máquina Virtual) no Azure é um computador virtual hospedado na nuvem, criado a partir de imagens (templates) de sistemas operacionais. Ela permite executar aplicações, serviços e bancos de dados como se fosse um servidor físico.

No caso de bancos de dados, você pode instalar e configurar sistemas como:

SQL Server

MySQL

PostgreSQL

Oracle (em imagens compatíveis)

Azure também oferece serviços gerenciados de banco de dados (como Azure SQL Database), mas neste caso estamos focando em VMs autogerenciadas.

🔷 2. Por que usar uma VM com banco de dados?
Controle total do sistema operacional e do SGBD (Sistema de Gerenciamento de Banco de Dados)

Pode ser configurado para ambientes de produção, teste ou desenvolvimento

Suporte a aplicações legadas ou altamente personalizadas

Requisitos específicos de configuração de hardware/software

🔷 3. Etapas para criar uma VM com banco de dados no Azure
✅ a) Escolha da Imagem
Windows Server ou Linux (Ubuntu, Red Hat, etc.)

Imagens com o banco de dados já pré-instalado (como "SQL Server 2019 on Windows Server")

✅ b) Tamanho da VM
Escolha baseada em CPU, memória e disco:

Exemplos: B-series (baixo custo), D-series (uso geral), E-series (memória otimizada)

Para bancos de dados, priorizar memória e IOPS (E ou M series)

✅ c) Disco
Disco do sistema operacional (geralmente SSD)

Disco de dados (para armazenar os arquivos do banco)

Tipos: HDD, SSD padrão, SSD premium

Separar disco de log e disco de dados para melhor performance

✅ d) Rede
Atribuição de IP público (opcional)

Segurança por meio de NSG (Network Security Group) para abrir portas específicas (como 1433 para SQL Server)

✅ e) Usuário e Autenticação
Usuário administrador da VM

Senha forte ou chave SSH (para Linux)

Autenticação adicional no banco de dados

🔷 4. Pós-Criação: Configurações e Boas Práticas
🔐 Segurança
Configurar firewall e NSG para permitir acesso apenas de IPs confiáveis

Usar Azure Defender para proteção avançada

Ativar criptografia de disco

🛠️ Manutenção e Monitoramento
Instalar Azure Monitor e Log Analytics para rastrear performance

Configurar backup automático do banco de dados (manualmente ou via script)

Atualizações automáticas do sistema operacional

☁️ Alta Disponibilidade e Desempenho
Usar Availability Sets ou Availability Zones para alta disponibilidade

Habilitar diagnóstico de disco e balanceamento de carga se necessário

Avaliar replicação entre regiões (Geo-Replication)

🔷 5. Custos
O custo de uma VM com banco de dados inclui:

Tempo de uso (por hora)

Tamanho da VM (CPU/RAM)

Armazenamento (disco)

Tráfego de rede

Licenciamento do banco de dados (ex: SQL Server com licenciamento incluído ou BYOL – Bring Your Own License)

Use a calculadora de preços do Azure para prever o custo total.
