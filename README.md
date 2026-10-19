## Hi, I'm Hlib 👋

Senior .NET backend engineer from Kyiv, Ukraine, with 10+ years of building web products from scratch to production, most recently as a backend lead.

- Co-founder & lead engineer of a pre-launch consumer fintech product (private repo): a .NET 10 modular monolith plus web and admin apps, built with an agentic Claude Code workflow (architecture guides, glossary and ADRs as agent context, custom skills, build-breaking guardrails)
- Back at Developex part-time, on AI-powered self-service reporting for a B2B client
- Before that, backend lead on a restaurant POS platform at Developex: took over a stalled Ruby-to-.NET rewrite, re-architected it into a modular monolith, delivered multi-tenancy, Auth0 and delivery-aggregator integrations, and hired for the team
- 5+ years as a lead .NET engineer at Dedicated Lab, a software studio serving US clients
- Into DDD, modular monoliths, CQRS and clean, boring-in-a-good-way architecture
- Most of my work lives in private client repos, so this profile is quieter than my commit history

### Open source

The libraries below grew out of patterns I enforced on production projects.

**[Hlibz.Redoc.AspNetCore.Extensions](https://github.com/hlib-zinchenko/Hlibz.Redoc.AspNetCore.Extensions)**
[![NuGet](https://img.shields.io/nuget/v/Hlibz.Redoc.AspNetCore.Extensions.svg)](https://www.nuget.org/packages/Hlibz.Redoc.AspNetCore.Extensions)
[![NuGet Downloads](https://img.shields.io/nuget/dt/Hlibz.Redoc.AspNetCore.Extensions.svg)](https://www.nuget.org/packages/Hlibz.Redoc.AspNetCore.Extensions)

Add-ons for [Redoc.AspNetCore](https://github.com/jonashendrickx/Redoc.AspNetCore)'s ReDoc UI:

- **Dark theme.** One line, and it fixes the colors ReDoc hardcodes outside its own theme config.
- **Light/System/Dark selector.** Everyone reading your API docs gets the theme they prefer.
- **Document picker.** Several OpenAPI documents in one app, with a dropdown to switch between
  them, like Swagger UI's definition selector.

```csharp
app.UseReDoc(options => options.UseDarkTheme());

// or, for several OpenAPI documents:
app.UseReDocDocuments(
    [new ReDocDocument("public", "Public API"), new ReDocDocument("admin", "Admin API")],
    docs => docs.ConfigureReDoc = (redoc, _) => redoc.UseDarkTheme());
```

**[Hlibz.EntityFrameworkCore.ModelRules](https://github.com/hlib-zinchenko/Hlibz.EntityFrameworkCore.ModelRules)**
[![NuGet](https://img.shields.io/nuget/v/Hlibz.EntityFrameworkCore.ModelRules.svg)](https://www.nuget.org/packages/Hlibz.EntityFrameworkCore.ModelRules)
[![NuGet Downloads](https://img.shields.io/nuget/dt/Hlibz.EntityFrameworkCore.ModelRules.svg)](https://www.nuget.org/packages/Hlibz.EntityFrameworkCore.ModelRules)

Your team's conventions, enforced on the EF Core model. If an entity breaks one, the model fails to build, at startup or in a unit test:

- **14 rules** for shadow properties, snake_case naming, decimal precision, string lengths,
  nullability, enum storage, schemas, query filters, delete behaviors, redundant indexes and
  identifier lengths.
- **Aggregate boundaries.** Roots refer to each other by key only, never delete each other by
  cascade, and each has a concurrency token.
- **EF Core 8, 9 and 10**, provider-neutral. It's tested on PostgreSQL, SQL Server, SQLite and
  MySQL, and against real databases in Docker.

```csharp
protected override void ConfigureConventions(ModelConfigurationBuilder configurationBuilder)
{
    configurationBuilder.UseModelRules(rules => rules
        .NoShadowProperties()
        .NamesFollow(NamingStyle.SnakeCase)
        .DecimalsHavePrecision()
        .StringsHaveMaxLength()
        .NoCascadeDeleteAcrossAggregates<IAggregateRoot>());
}
```

### Side projects

**[Flashcards PWA](https://hlib-zinchenko.github.io/flashcards-pwa/)** ([repo](https://github.com/hlib-zinchenko/flashcards-pwa))
Offline-first flashcards app that installs to an iPhone home screen, with no App Store, account or server. I built it for my partner after no existing app fit how she studies, and I keep improving it from her feedback. I chose a PWA over a native app to skip the developer fee and review cycle. Svelte 5, TypeScript, IndexedDB, with tests, CI and tag-based releases. Built with Claude Code.

### Tech I work with

- **Architecture:** DDD, CQRS, Clean Architecture, modular monoliths, REPR, event-driven, multi-tenancy
- **Backend:** C#, .NET, ASP.NET Core, EF Core, MassTransit, MediatR, FluentValidation, Hangfire, Quartz, SignalR, Serilog, Roslyn analyzers
- **Data:** PostgreSQL, MS SQL, MySQL
- **Cloud & DevOps:** AWS (EC2, ECS, RDS, S3, SES, SNS, CloudWatch), Docker, GitLab CI, GitHub Actions, Azure DevOps
- **Integrations:** Auth0, Stripe, Stream (delivery aggregators)
- **Testing:** xUnit, Moq, Testcontainers
- **Frontend (logic side):** Vue.js, TypeScript
- **AI:** Claude Code (agentic workflows, custom skills), LLM integration, prompt design

### Find me

[LinkedIn](https://linkedin.com/in/hzinchenko)
