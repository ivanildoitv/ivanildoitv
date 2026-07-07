# Visão Geral — OCI (Resumo para Entrevista)

## 1. O que é a OCI?
- Plataforma de cloud computing da Oracle com **50+ regiões** e **200+ serviços** (IaaS, PaaS, SaaS)
- **Diferenciais**: Autonomous Database, OKE (Kubernetes), preço previsível (sem custo de egress), VCN de alta performance, compartments com IAM granular, AI/ML nativo, multicloud (Oracle DB@AWS/Azure/GCP)

## 2. Catálogo de Recursos

### Compute
- **VM & Bare Metal** — shapes flex (custom OCPU/memória), otimizados por uso geral, GPU, HPC, E/S densa
- **OKE** — Kubernetes gerenciado (Enhanced, Virtual Node, Basic), integração nativa com VCN/IAM/LB
- **Functions** — serverless baseado no Fn Project
- **Container Instances** — contêineres serverless sem K8s
- **OCVS** — VMware SDDC sobre bare metal OCI
- **Compute Cloud@Customer / Roving Edge** — OCI no datacenter do cliente / edge computing

### Storage
- **Block Volume** — SSD persistente com backup, clonagem, replicação cross-region
- **Object Storage** — S3-compatível, tiers Standard/Infrequent/Archive, ideal para data lakes
- **File Storage** — NFSv3 compartilhado; **Lustre** para HPC
- **Local NVMe SSD** — baixa latência, alta taxa de transferência
- **Archive Storage / Data Transfer** — longo prazo / transferência física offline

### Networking, Edge & Connectivity
- **VCN** — rede privada definida por software, subnets públicas/privadas, gateways (Internet/NAT/Service)
- **Load Balancer** (L7) e **Network Load Balancer** (L4)
- **FastConnect** — conexão privada dedicada (1-100 Gbps)
- **VPN IPSec**, **DNS & Traffic Management**, **WAF**, **Network Firewall** (Palo Alto NGFW)
- **Bastion** — acesso SSH/RDP gerenciado
- **Zero Trust Packet Routing (ZPR)** — microssegmentação baseada em identidade

### Database
- **Autonomous Database (ADB)** — Oracle DB autogerenciável (OLTP, DW, JSON), tuning/patching/backup automáticos
- **Exadata** — máxima performance em infra dedicada, Exascale ou Cloud@Customer
- **Base Database** — Oracle DB manual (RAC, single-node, Data Guard)
- **MySQL HeatWave** — MySQL + acelerador de consultas in-memory + ML
- **OCI Database with PostgreSQL** — PostgreSQL gerenciado
- **NoSQL Database**, **OCI Cache (Redis)**, **OpenSearch**, **Globally Distributed Database**
- **GoldenGate** — replicação/streaming em tempo real
- **Data Safe** — masking, auditing, avaliação de riscos

### Analytics, AI & Machine Learning
- **Data Science** — Jupyter notebooks gerenciados, treinamento, catálogo e deploy de modelos
- **AI Data Platform (Workbench)** — lakehouse unificado (Spark + Delta Lake + arquitetura medalhão + MLOps)
- **Data Flow** — Apache Spark serverless
- **Data Integration** — ETL/ELT no-code, 100+ conectores, proteção contra schema drift
- **Generative AI** — LLMs gerenciados (Cohere, Meta Llama, fine-tuning) + Agentes multi-agente RAG
- **AI Services** — Language (NLP), Speech, Vision, Document Understanding
- **Analytics Cloud (OAC)** — BI empresarial com dashboards e análises aumentadas

### Integration & Messaging
- **Streaming** — Kafka-compatível, **Queue** — filas gerenciadas, **Events** — event-driven triggers
- **API Gateway** — rate limiting, autenticação, transformações
- **Integration 3** — iPaaS corporativo, **Process Automation** — BPM low-code

### Security, Identity & Compliance
- **IAM** — RBAC, federação (SAML, SCIM, OAuth), Identity Domains
- **Vault** — gerenciamento de chaves/criptografia com suporte HSM
- **Cloud Guard** — CSPM, detecção de ameaças e anomalias de configuração
- **Security Zones** — políticas obrigatórias por compartment
- **Vulnerability Scanning** — varredura em hosts, contêineres e redes
- **Bastion**, **ZPR**, **Network Firewall**, **WAF**
- **Autonomous Linux** — patching automatizado e compliance contínuo

### Observability & Management
- **Monitoring** — métricas e alarmes; **Logging** — logs centralizados; **Log Analytics** — análise com ML
- **APM** — tracing distribuído, métricas de aplicação, synthetics
- **Ops Insights** — planejamento de capacidade; **Stack Monitoring** — observabilidade full-stack
- **Resource Manager** — Terraform gerenciado

### Developer Services
- **DevOps** — CI/CD completo (repos, build, deploy)
- **Resource Manager** (Terraform), **APEX** (low-code), **Visual Builder**, **Digital Assistant**

### Governance & Administration
- **Audit** — logs de API; **Cloud Advisor** — recomendações de custo/segurança/performance
- **Budgets** e **Cost Management** (FinOps); **Compartment Quotas**; **Tagging**

### Migration, Hybrid & Edge
- **Cloud Migrations** — orquestração rehost/replatform
- **Full Stack Disaster Recovery** — DR automatizado
- **Dedicated Region / Compute Cloud@Customer / Alloy** — OCI no datacenter do cliente

### Multicloud
- **Oracle Database@AWS/Azure/GCP** — Oracle DB rodando dentro de outras clouds
- **Interconnect** direto com AWS/Azure/GCP

## 3. Stack de Engenharia de Dados (Arquitetura)
- **Ingestão**: Streaming (Kafka), Queue, Object Storage (Landing Zone), Data Integrator (SaaS)
- **Transformação**: Data Flow (Spark serverless), Functions, Data Integration (ETL/ELT no-code), AI Data Platform (Spark + Delta Lake)
- **Armazenamento**: Data Lake medalhão — Bronze (brutos), Silver (limpos), Gold (agregados)
- **Orquestração**: Prefect (Server + Workers no OKE)
- **ML**: MLflow (Tracking + Model Registry), Data Science Notebooks, Generative AI
- **CI/CD**: OCI DevOps + OCIR
- **Infra**: OKE, VCN, MySQL/PostgreSQL (metadados), Vault, IAM

## 4. Conceitos-chave para entrevista
- **Compartments** — unidade de isolamento lógico; tudo na OCI pertence a um compartment
- **Políticas IAM** — permitem ações em recursos de compartments específicos ("Allow group X to manage instances in compartment Y")
- **Shapes Flex** — você define OCPUs e memória, paga só pelo que usa
- **OCI é a única cloud com Autonomous Database** — banco que se autogere (tuning, patching, backup)
- **OKE Enhanced** — suporte a GPU, node pools, integração nativa com VCN e IAM
- **Preço previsível** — sem cobrança de egress entre serviços OCI
- **FastConnect** — alternativa ao Direct Connect / ExpressRoute
