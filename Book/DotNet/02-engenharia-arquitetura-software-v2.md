# 🏗️ Engenharia e Arquitetura de Software com .NET/C# — Resumo para Entrevista

> Resumo direto ao ponto. Sem código. Links para o documento completo com exemplos.

---

## 🎯 SOLID

| Princípio | Definição |
|---|---|
| **S** — Single Responsibility | Cada classe tem **uma única responsabilidade**. Uma só razão para mudar. |
| **O** — Open/Closed | Aberto para **extensão**, fechado para **modificação**. Use interfaces/herança. |
| **L** — Liskov Substitution | Subtipos devem ser **substituíveis** por seus supertipos sem quebrar o programa. |
| **I** — Interface Segregation | Interfaces **específicas** para cada cliente. Não force métodos não usados. |
| **D** — Dependency Inversion | Dependa de **abstrações**, não de implementações concretas. Use DI. |

[🔗 Documento completo com exemplos de SOLID](./02-engenharia-arquitetura-software.md#-princípios-fundamentais)

---

## 🏛️ Arquiteturas

| Arquitetura | Conceito | Quando usar |
|---|---|---|
| **MVC** | Separa Model (dados), View (interface), Controller (lógica) | Apps web tradicionais ASP.NET Core |
| **DDD** | Design guiado pelo domínio do negócio (Entities, Value Objects, Aggregates, Domain Events) | Domínios complexos com regras de negócio ricas |
| **Clean Architecture** | Camadas concêntricas, dependências apontam para dentro (Domain → Application → Infrastructure → Presentation) | Apps que precisam ser framework-agnostic e testáveis |
| **Hexagonal (Ports & Adapters)** | Core independe de infra via portas (interfaces) e adaptadores (implementações) | Máxima separação entre domínio e tecnologia externa |
| **Microserviços** | Serviços independentes, cada um com seu banco, comunicação via API/mensageria | Equipes grandes, escalabilidade independente, deploys isolados |

[🔗 Documento completo com exemplos de arquiteturas](./02-engenharia-arquitetura-software.md#-arquiteturas-de-software)

---

## 📌 Dicas para Entrevista

**SOLID é o mais cobrado.** Saiba explicar cada letra com um exemplo prático (ex: SRP = classe `Usuario` não salva no banco).

**Clean Architecture vs Hexagonal:** Ambos isolam o domínio. Clean Architecture enfatiza camadas concêntricas; Hexagonal enfatiza portas/adaptadores. Na prática, são muito similares.

**Microserviços:** Saiba defender quando **não** usar (time pequeno, domínio simples, latência crítica). Monolito bem feito vence microserviço mal dividido.

**DDD:** Os conceitos-chave são: Entity (tem identidade), Value Object (imutável, sem identidade), Aggregate Root (entidade raiz que garante consistência), Domain Event (algo que aconteceu no domínio), Repository (abstração de persistência).

[🔗 Documento completo com todas as implementações](./02-engenharia-arquitetura-software.md)

---

*Documento atualizado em Julho de 2026*
