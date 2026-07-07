# ☁️ AWS — Resumo para Entrevista

> Resumo direto ao ponto. Links para o documento detalhado com diagramas e exemplos Terraform.

---

## 🌍 O que é AWS?

Maior provedora de nuvem do mundo (2006+). 200+ serviços, infraestrutura global com **regiões**, **zonas de disponibilidade (AZs)** e **600+ edge locations**.

[🔗 Detalhado: infraestrutura global](./01-visao-geral-aws-detalhado.md#-infraestrutura-global)

---

## 🏗️ Modelos de Serviço

| Modelo | Você gerencia | AWS gerencia |
|---|---|---|
| **IaaS** | App, dados, runtime, SO | Virtualização, servidores, rede |
| **PaaS** | App e dados | Runtime, SO, infra |
| **SaaS** | Nada | Tudo |

[🔗 Detalhado: modelos de serviço](./01-visao-geral-aws-detalhado.md#-modelos-de-serviço-em-nuvem)

---

## 🛠️ Principais Serviços

| Categoria | Serviços-chave |
|---|---|
| **Compute** | EC2 (VMs), Lambda (serverless), ECS/EKS (contêineres) |
| **Storage** | S3 (objetos), EBS (blocos), EFS (arquivos NFS), Glacier (archive) |
| **Database** | RDS (relacional gerenciado), Aurora (5x performance), DynamoDB (NoSQL serverless), ElastiCache (Redis) |
| **Networking** | VPC (rede isolada), CloudFront (CDN), Route 53 (DNS), ELB (load balancer), API Gateway |
| **Security** | IAM (identidade), KMS (criptografia), WAF + Shield (proteção), CloudTrail (auditoria) |
| **Serverless** | Lambda + API Gateway + SQS (fila) + SNS (pub/sub) + Step Functions (orquestração) + EventBridge (event bus) |
| **ML/AI** | SageMaker (ML full), Bedrock (LLMs), Rekognition (visão), Polly/Transcribe (áudio) |

[🔗 Detalhado: serviços por categoria com diagramas](./01-visao-geral-aws-detalhado.md#-principais-serviços-por-categoria)

---

## 📜 Infraestrutura como Código (Terraform)

A estrutura típica de projeto Terraform para AWS:

```
infra/
├── environments/ (dev, staging, prod)
│   └── main.tf, variables.tf, terraform.tfvars
├── modules/ (networking, compute, database)
└── provider.tf
```

**Exemplos de recursos provisionados:**
- **VPC** — rede isolada com subnets públicas/privadas, NAT Gateway
- **EC2** — instâncias com Security Group e user_data
- **RDS** — PostgreSQL/MySQL com multi-AZ, encryption, backup
- **S3** — bucket com versioning, encryption, bloqueio de acesso público
- **Lambda + API Gateway** — função serverless exposta via HTTP
- **DynamoDB** — tabela NoSQL pay-per-request
- **ECS Fargate** — contêineres serverless com load balancer

[🔗 Detalhado: todos os exemplos Terraform](./01-visao-geral-aws-detalhado.md#-infraestrutura-como-código-com-terraform)

---

## 🏛️ Well-Architected Framework

6 pilares: **Operational Excellence**, **Security**, **Reliability**, **Performance Efficiency**, **Cost Optimization**, **Sustainability**.

---

## 🤝 Responsabilidade Compartilhada

- **AWS:** Segurança *da* nuvem (hardware, datacenter, hipervisor)
- **Cliente:** Segurança *dentro* da nuvem (dados, IAM, patches do SO, firewalls)

---

## 💡 Dicas para Entrevista

- **EC2 vs Lambda:** EC2 para workloads previsíveis e que precisam de SO completo. Lambda para eventos, filas, APIs esporádicas.
- **S3 é o serviço mais antigo e mais usado.** 11 noves de durabilidade. Classes de storage para otimizar custo.
- **DynamoDB** é a resposta da AWS para alta escala NoSQL. Latência de milissegundos, serverless, pay-per-request.
- **VPC** é a base de qualquer arquitetura AWS. Saiba explicar subnets públicas vs privadas, NAT Gateway, Security Groups vs NACLs.
- **IAM Policies** são JSON. Princípio do menor privilégio sempre.
- **Well-Architected** é frequentemente perguntado. Decore os 6 pilares.
- **Terraform vs CloudFormation:** Terraform é multi-cloud e HCL; CloudFormation é AWS-only e JSON/YAML. Na prática, Terraform é mais usado no mercado.

[🔗 Documento detalhado completo](./01-visao-geral-aws-detalhado.md)

---

*Documento atualizado em Julho de 2026*
