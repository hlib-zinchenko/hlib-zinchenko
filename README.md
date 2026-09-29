## Hi, I'm Hlib 👋

Backend-focused C#/.NET engineer from Kyiv, Ukraine, with 10+ years of building web products from scratch to production.

- Co-founder & lead engineer of a pre-launch consumer fintech product (private repo), built end to end with an AI-driven workflow in Claude Code
- Previously led backend teams: a modular-monolith rewrite of a restaurant POS platform at Developex, and 5+ years as a lead .NET engineer at Dedicated Lab
- Into DDD, modular monoliths, CQRS and clean, boring-in-a-good-way architecture
- Most of my work lives in private client repos, so this profile is quieter than my commit history

### Open source

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

### Tech I work with

- **Architecture:** DDD, CQRS, Clean Architecture, modular monoliths, REPR, multi-tenancy
- **Backend:** C#, .NET, ASP.NET Core, EF Core, MassTransit, MediatR, FluentValidation, Hangfire, Quartz, SignalR, Serilog
- **Data:** PostgreSQL, MS SQL, MySQL
- **Cloud & DevOps:** AWS (EC2, ECS, RDS, S3, SES, SNS, CloudWatch), Docker, GitLab CI, GitHub Actions, Azure DevOps
- **Integrations:** Auth0, Stripe, Stream (delivery aggregators)
- **Testing:** xUnit, Moq, Testcontainers
- **Frontend (logic side):** Vue.js, TypeScript
- **AI:** Claude Code, prompt design for LLM features

### Find me

[LinkedIn](https://linkedin.com/in/hzinchenko)
