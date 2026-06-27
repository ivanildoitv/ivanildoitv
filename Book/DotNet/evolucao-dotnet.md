# 📘 Evolução do .NET — Do .NET 3.5 ao .NET 10

- Documento técnico em Markdown com diagramas Mermaid

## 🧭 Linha do Tempo Geral

```mermaid
timeline
    title Evolução do .NET (2007–2025)

    section Era .NET Framework (Windows-only)
        2007 : .NET 3.5 (LINQ, WCF, WF)
        2010 : .NET 4.0 (TPL, PLINQ)
        2012 : .NET 4.5 (async/await)

    section Era .NET Core (Multiplataforma e Open Source)
        2016 : .NET Core 1.0 (multiplataforma)
        2019 : .NET Core 3.1 (WPF/WinForms)

    section Era Unificada (.NET Moderno e Cross-Platform)
        2020 : .NET 5 (unificação)
        2021 : .NET 6 LTS (Minimal APIs)
        2022 : .NET 7 (performance)

    section Era Performance e IA (Cloud Native)
        2023 : .NET 8 LTS (NativeAOT estável)
        2024 : .NET 9 (C# 13)
        2025 : .NET 10 LTS (C# 14, AVX10.2)
```

## 🏛️ Evolução Arquitetural

```mermaid
flowchart LR
    A[".NET Framework<br>Windows-only"] --> B[".NET Core<br>Multiplataforma"]
    B --> C[".NET Unificado<br>(.NET 5+)"]
    C --> D[".NET 8 LTS<br>Cloud Native + AOT"]
    D --> E[".NET 10 LTS<br>Performance + PQC + AOT"]
```

## 📚 Evolução por Versão

## 🔷 .NET 3.5 (2007)

- Introdução do LINQ
- C# 3.0 (lambdas, var, extension methods)
- WCF, WF, ASP.NET AJAX

## 🔷 .NET 4.0 → 4.8 (2010–2019)
- TPL (Task Parallel Library)
- PLINQ
- async/await (C# 5)
- Web API
- Última versão: 4.8 (suporte contínuo, sem evolução)

## 🟧 Era .NET Core

### 🟧 .NET Core 1.0 (2016)

- Multiplataforma
- CLI moderna
- ASP.NET Core 1.0

### 🟧 .NET Core 2.x

- Razor Pages
- EF Core amadurecendo

### 🟧 .NET Core 3.0 / 3.1

- WPF e WinForms (Windows)
- gRPC
- C# 8

## 🟩 Era .NET Unificado (5 → 10)

```mermaid
graph TD
    A[.NET 5] --> B[.NET 6 LTS]
    B --> C[.NET 7]
    C --> D[.NET 8 LTS]
    D --> E[.NET 9]
    E --> F[.NET 10 LTS]
```     

## 🔵 Comparação Direta: .NET 7 vs 8 vs 9 vs 10

## 📊 Tabela Comparativa
| Versão  | Tipo | Foco                    | Destaques                                             |
| ------- | ---- | ----------------------- | ----------------------------------------------------- |
| .NET 7  | STS  | Performance             | JIT otimizado, containers, ASP.NET Core mais rápido   |
| .NET 8  | LTS  | Cloud-native            | NativeAOT estável, EF Core 8, WASM multithread        |
| .NET 9  | STS  | Incremental             | C# 13, melhorias em JSON, networking, AOT             |
| .NET 10 | LTS  | Performance + AOT + PQC | AVX10.2, C# 14, AOT maduro, criptografia pós‑quântica |


## 🔥 .NET 7 (2022)

- Foco em performance
- Melhorias no JIT
- ASP.NET Core mais rápido
- EF Core 7 com bulk operations
- NativeAOT ainda experimental

## 🟢 .NET 8 (2023 – LTS)

- NativeAOT estável
- ASP.NET Core com pipeline otimizado
- EF Core 8 com JSON nativo
- WASM com multithreading
- System.Text.Json mais rápido

## 🟡 .NET 9 (2024)

- C# 13
- Melhorias em AOT
- Novo modelo de hosting no ASP.NET Core
- Melhorias em networking, threading e JSON

## 🔴 .NET 10 (2025 – LTS)

- C# 14
- Suporte a AVX10.2 e ARM SVE
- NativeAOT maduro
- Criptografia pós‑quântica
- Test runner unificado
- Melhorias no JIT e GC

## ⚙️ Evolução do C# (3 → 14)

```mermaid
---
config:
  theme: base
  themeVariables:
    background: "#fafafa"
    primaryColor: "#dae8fc"
    primaryTextColor: "#1a1a1a"
    primaryBorderColor: "#6c8ebf"
    lineColor: "#666666"
    secondaryColor: "#fff2cc"
    tertiaryColor: "#d5e8d4"
    cScale0: "#e8d5f5"
    cScale1: "#dae8fc"
    cScale2: "#d5e8d4"
    cScale3: "#ffe6cc"
    cScaleLabel0: "#1a1a1a"
    cScaleLabel1: "#1a1a1a"
    cScaleLabel2: "#1a1a1a"
    cScaleLabel3: "#1a1a1a"
---
timeline
    title Evolução do C#
    section Era Funcional (2007-2012)
        2007 : C# 3 (LINQ, lambdas)
        2010 : C# 4 (dynamic)
        2012 : C# 5 (async/await)
    section Era da Expressividade (2015-2019)
        2015 : C# 6 (interpolação)
        2017 : C# 7 (tuplas, pattern matching)
        2019 : C# 8 (nullable)
    section Era Moderna (2020-2022)
        2020 : C# 9 (records)
        2021 : C# 10 (global usings)
        2022 : C# 11 (raw strings)
    section Era Atual (2023-2025)
        2023 : C# 12 (primary constructors)
        2024 : C# 13 (params collections)
        2025 : C# 14 (extension members, field keyword)
```     

## 🚀 Evolução de Performance

```mermaid
graph LR
    A[JIT RyuJIT] --> B[.NET 6<br>Profile-guided optimization]
    B --> C[.NET 7<br>Loop & devirtualization]
    C --> D[.NET 8<br>AOT estável]
    D --> E[.NET 10<br>AVX10.2 + GC otimizado]
```   

## 🧩 Evolução do ASP.NET Core

```mermaid
flowchart LR
    A["ASP.NET MVC"] --> B["ASP.NET Core 1.0"]
    B --> C["Minimal APIs (.NET 6)"]
    C --> D["Pipeline otimizado (.NET 8)"]
    D --> E["Hosting simplificado (.NET 9)"]
    E --> F["Performance extrema (.NET 10)"]
``` 

## 📦 Evolução do EF Core

```mermaid
graph TD
    A[EF Core 1] --> B[EF Core 3]
    B --> C[EF Core 5]
    C --> D[EF Core 7<br>Bulk ops]
    D --> E[EF Core 8<br>JSON nativo]
    E --> F[EF Core 9<br>Melhorias em LINQ]
```     
## 📄 Conclusão

| O .NET evoluiu de uma plataforma Windows‑only para um ecossistema multiplataforma, unificado, cloud‑native e altamente otimizado, com foco crescente em:

- Performance extrema
- AOT
- IA e cloud
- Segurança pós‑quântica
- Ferramentas modernas
- C# cada vez mais expressivo
- O .NET 10 representa o maior salto desde o .NET 6.


