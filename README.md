## Hi, I'm Hlib 👋

Backend-focused C#/.NET engineer from Kyiv, Ukraine, with 10+ years of building web products from scratch to production.

- Senior .NET engineer, previously backend team lead on a restaurant POS platform
- Into DDD, modular monoliths, CQRS and clean, boring-in-a-good-way architecture
- Currently building a pre-launch fintech product with a business partner (private repo), using an AI-driven workflow with Claude Code
- Most of my work lives in private client repos, so this profile is quieter than my commit history

### Open source

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

Previously published as `Hlibz.Redoc.AspNetCore.DarkTheme`.

### Tech I work with

- **Backend:** C#, .NET, ASP.NET Core, EF Core, MassTransit, FluentValidation, Hangfire, Quartz
- **Data:** PostgreSQL, MS SQL, MySQL
- **Cloud & DevOps:** AWS (S3, SES, SNS, RDS, ECS, CloudWatch), Docker, GitLab CI, GitHub Actions
- **Testing:** xUnit, Moq, Testcontainers
- **Frontend (logic side):** Vue.js, TypeScript
- **AI:** Claude Code

### Find me

[LinkedIn](https://linkedin.com/in/hzinchenko)
