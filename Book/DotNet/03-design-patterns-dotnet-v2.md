# 🎯 Design Patterns em .NET/C# — Resumo para Entrevista

> Resumo direto ao ponto. Sem código. Links para o documento completo com exemplos.

---

## 🧭 Como Escolher um Pattern

| Problema | Categoria |
|---|---|
| Criação de objetos | **Creational** (Factory, Builder, Singleton) |
| Composição de classes/objetos | **Structural** (Decorator, Adapter, Facade) |
| Interação/comportamento entre objetos | **Behavioral** (Strategy, Observer, Command) |

**Regra de ouro:** Use pattern para reduzir acoplamento real, não por moda. Prefira DI nativa do .NET antes de criar factories complexas.

[🔗 Documento completo com fluxo de decisão](./03-design-patterns-dotnet.md#-como-escolher-um-pattern)

---

## 🏗️ Criacionais

| Pattern | Quando usar |
|---|---|
| **Singleton** | Recurso único por processo (cache, config). No ASP.NET Core, prefira `AddSingleton` no DI. |
| **Factory Method** | Criação varia conforme contexto/entrada. Ex: `INotificador` → Email ou SMS. |
| **Abstract Factory** | Famílias de objetos relacionados. Ex: tema claro/escuro, provedores de banco. |
| **Builder** | Objeto complexo com muitas combinações opcionais. Ex: relatório com partes configuráveis. |
| **Prototype** | Clonar objetos custosos de criar. |

[🔗 Documento completo com exemplos criacionais](./03-design-patterns-dotnet.md#-padrões-criacionais)

---

## 🧩 Estruturais

| Pattern | Quando usar |
|---|---|
| **Adapter** | Integrar API legada/externa com contrato novo. |
| **Facade** | Simplificar subsistema complexo. Ex: `CheckoutFacade` que orquestra estoque, pagamento e entrega. |
| **Decorator** | Adicionar comportamento sem alterar a classe base. Ex: logging, retry, cache em cima de um service. |
| **Composite** | Estruturas em árvore. Ex: menu, categorias, permissões. |
| **Proxy** | Controle de acesso, cache, lazy loading, circuit breaker. |

[🔗 Documento completo com exemplos estruturais](./03-design-patterns-dotnet.md#-padrões-estruturais)

---

## 🔄 Comportamentais

| Pattern | Quando usar |
|---|---|
| **Strategy** | Trocar algoritmo dinamicamente. Ex: cálculo de frete (econômico vs expresso). |
| **Observer** | Notificar múltiplos assinantes sobre eventos. Ex: Domain Events, message bus. |
| **Command** | Encapsular ação como objeto. Útil para filas, retry, auditoria, undo. |
| **State** | Regras mudam conforme estado interno. Ex: fluxo de pedido (Pendente → Confirmado → Cancelado). |
| **Template Method** | Fluxo padrão com etapas variáveis. Ex: importador de arquivos. |
| **Chain of Responsibility** | Pipeline de validações/regras encadeadas. |

[🔗 Documento completo com exemplos comportamentais](./03-design-patterns-dotnet.md#-padrões-comportamentais)

---

## ☁️ Padrões Arquiteturais Modernos em .NET

| Pattern | Quando usar |
|---|---|
| **Repository + Unit of Work** | Domínio rico com EF Core. **Evite** em CRUD simples (DbContext já basta). |
| **CQRS** | Alta leitura vs escrita com regras complexas. Modelos de leitura e escrita separados. |
| **Mediator (MediatR)** | Desacopla controller de serviços. Facilita pipelines (log, validação, transação). |
| **Outbox** | Garante consistência ao publicar eventos na mesma transação do banco. Worker posterior publica no broker. |
| **Saga** | Transação distribuída em microserviços com compensação em caso de falha. |

[🔗 Documento completo com padrões modernos](./03-design-patterns-dotnet.md#-padrões-arquiteturais-modernos-em-net)

---

## 🚫 Anti-Patterns Comuns

- **God Class:** classe que faz tudo.
- **Anemic Domain Model:** entidades só com getters/setters, sem comportamento.
- **Singleton indiscriminado:** estado global difícil de testar.
- **Repository para tudo:** abstração desnecessária em CRUD simples.
- **Overengineering:** pattern sem problema real.

---

## 💡 Dicas para Entrevista

- **Strategy é o mais cobrado.** Saiba explicar com exemplo de frete ou desconto.
- **Decorator vs Proxy:** Decorator adiciona comportamento; Proxy controla acesso. Ambos usam composição.
- **Singleton no .NET moderno:** Quase nunca precisa implementar na mão — `services.AddSingleton` resolve.
- **CQRS não é para todo projeto.** Só faz sentido quando leitura e escrita têm requisitos significativamente diferentes.
- **Outbox Pattern** é essencial em microserviços para evitar perda de eventos entre o banco e o message broker.
- **Comece simples:** Clean Architecture leve + DI + testes. Patterns só onde a dor é real.

[🔗 Documento completo com todos os patterns](./03-design-patterns-dotnet.md)

---

*Documento atualizado em Julho de 2026*
