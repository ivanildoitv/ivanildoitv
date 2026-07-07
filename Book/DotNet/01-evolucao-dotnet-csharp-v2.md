# 📘 Evolução .NET e C# — Resumo para Entrevista

> Resumo direto ao ponto. Sem código. Links para o documento completo com exemplos.

---

## 🧭 Linha do Tempo

| Era                | Período   | Destaque                                     |
| ------------------ | --------- | -------------------------------------------- |
| **.NET Framework** | 2002–2019 | Windows-only. Versão final: 4.8              |
| **.NET Core**      | 2016–2019 | Multiplataforma, open source, modular        |
| **.NET Unificado** | 2020+     | Versão única (5, 6 LTS, 7, 8 LTS, 9, 10 LTS) |

[🔗 Documento completo com timeline detalhada](./01-evolucao-dotnet-csharp.md#-linha-do-tempo)

---

## 🏛️ .NET Framework → .NET Core → .NET Moderno

| Aspecto      | .NET Framework | .NET Core             | .NET 10                    |
| ------------ | -------------- | --------------------- | -------------------------- |
| Plataforma   | Windows only   | Windows, Linux, macOS | Windows, Linux, macOS, ARM |
| Distribuição | MSI global     | NuGet side-by-side    | NuGet + NativeAOT          |
| Performance  | Baseline       | 2-3x mais rápido      | **5-6x mais rápido**       |
| Startup      | ~500ms         | ~100ms                | ~50ms (AOT)                |
| Open Source  | ❌              | ✅                     | ✅                          |
| Cloud Native | ❌              | Parcial               | ✅ Containers, K8s          |

[🔗 Documento completo com comparações](./01-evolucao-dotnet-csharp.md#-comparação-direta-versões-lts)

---

## 🎯 Evolução do C# — O Que Mais Cai em Entrevista

| Versão      | Ano  | Feature-chave                                                   |
| ----------- | ---- | --------------------------------------------------------------- |
| **C# 2.0**  | 2005 | **Generics**, Nullable types                                    |
| **C# 3.0**  | 2007 | **LINQ**, Lambdas, Extension methods                            |
| **C# 5.0**  | 2012 | **async/await**                                                 |
| **C# 6.0**  | 2015 | String interpolation, Null-conditional (`?.`)                   |
| **C# 7.0**  | 2017 | Tuples, Pattern matching, Out vars                              |
| **C# 8.0**  | 2019 | **Nullable reference types**, Switch expressions, Async streams |
| **C# 9.0**  | 2020 | **Records**, Init-only, Top-level statements                    |
| **C# 10.0** | 2021 | Global usings, File-scoped namespaces, Minimal APIs             |
| **C# 11.0** | 2022 | Raw strings, Generic math, Required members                     |
| **C# 12.0** | 2023 | **Primary constructors**, Collection expressions                |
| **C# 13.0** | 2024 | Params collections                                              |
| **C# 14.0** | 2025 | Extension members, Field keyword, Discriminated unions          |

[🔗 Documento completo com exemplos de cada versão](./01-evolucao-dotnet-csharp.md#-tabela-resumo-c)

---

## 🚀 Performance Acumulada

.NET 10 é **~5-6x mais rápido** que .NET Framework 4.8, com **menos memória** e **startup ~50ms** com NativeAOT.

## 📦 Evolução ASP.NET

Web Forms (2002) → MVC (2009) → Web API (2012) → **ASP.NET Core** (2016) → Razor Pages (2017) → **Minimal APIs** (2021) → **Blazor Full Stack** (2023)

## 🗃️ Evolução EF Core

EF 4.0 (2010) → EF 6.0 (2013) → **EF Core** (2016) → EF Core 8 com **JSON nativo** (2023)

[🔗 Documento completo com ASP.NET e EF Core](./01-evolucao-dotnet-csharp.md#-evolução-do-aspnet)

---

## 💡 Dicas para Entrevista

- **.NET Core vs Framework:** Saiba explicar que .NET Core é multiplataforma, modular, open source e muito mais performático. .NET 5+ unificou tudo.
- **async/await:** É C# 5.0. Pergunta clássica de entrevista — entenda que não cria threads, apenas coordena Tasks.
- **Records (C# 9):** Imutáveis, value equality, `with` para mutation não-destrutiva.
- **Primary constructors (C# 12):** Disponíveis agora para classes, não só records.
- **NativeAOT:** Compila para nativo sem JIT. Startup instantâneo, aplicações menores (~10MB).
- **LTS vs STS:** .NET 6, 8, 10 são LTS (3 anos de suporte). .NET 7, 9 são STS (18 meses).
- **Quando migrar:** Se precisa de performance, containers/ Linux, ou features modernas. Se o legado está estável e roda só em Windows, pode esperar.

[🔗 Documento completo com checklist de migração](./01-evolucao-dotnet-csharp.md#-quando-migrar)

---

*Documento atualizado em Julho de 2026*
