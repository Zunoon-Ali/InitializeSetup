Here’s a full `.md` (Markdown) guide for setting up an **ASP.NET Core** project with prerequisites, setup instructions, and common usage.

---

````md
# 🚀 ASP.NET Core Project Setup Guide

A step-by-step guide to set up and run an ASP.NET Core web application using .NET SDK.

---

## ✅ Prerequisites

| Tool / Software         | Purpose                          | Recommended Version |
|-------------------------|----------------------------------|---------------------|
| **.NET SDK**            | Core framework and CLI tools     | .NET 6+ or .NET 8   |
| **Visual Studio Code**  | Lightweight code editor          | Latest              |
| **Visual Studio**       | Full-featured IDE (optional)     | 2022+ (with .NET support) |
| **C# Extensions (VS Code)** | C# language support         | Latest              |
| **Node.js + NPM**       | Frontend tooling (optional)      | Latest              |

---

## 🧰 Installation Steps

### 1. Install .NET SDK

Download from: [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)

Check installation:

```bash
dotnet --version
````

---

## 🛠️ Create New ASP.NET Core Project

### For Web App (MVC)

```bash
dotnet new mvc -n MyWebApp
cd MyWebApp
```

### For Web API

```bash
dotnet new webapi -n MyApiApp
cd MyApiApp
```

---

## 🗃️ Project Structure

```
MyWebApp/
├── Controllers/        # C# Controllers
├── Models/             # Data Models
├── Views/              # Razor Views (for MVC)
├── wwwroot/            # Static files (CSS, JS)
├── appsettings.json    # App config
├── Program.cs          # Entry point
└── Startup.cs (pre .NET 6) # Configuration (for older versions)
```

---

## ▶️ Run the Application

```bash
dotnet run
```

By default:

* WebApp: `https://localhost:5001`
* Web API: Swagger UI available at `/swagger`

---

## ✏️ Add a Controller (Example)

```bash
dotnet new controller -name HomeController
```

Example: `Controllers/HomeController.cs`

```csharp
public class HomeController : Controller
{
    public IActionResult Index()
    {
        return View();
    }
}
```

---

## ⚙️ Common .NET CLI Commands

| Command                     | Description            |
| --------------------------- | ---------------------- |
| `dotnet new`                | Create a new project   |
| `dotnet build`              | Compile the project    |
| `dotnet run`                | Run the app            |
| `dotnet watch run`          | Auto-reload on changes |
| `dotnet add package <name>` | Add NuGet package      |
| `dotnet publish`            | Publish for deployment |

---

## 🔧 Configuration: `appsettings.json`

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```

---

## 🌐 Routing Example (in `Program.cs` for .NET 6+)

```csharp
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

---

## 📦 Add Entity Framework Core (Optional)

For database support:

```bash
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
```

---

## 📚 Learn More

* 🔗 [Official Docs](https://learn.microsoft.com/en-us/aspnet/core/)
* 🔗 [Dotnet CLI Guide](https://learn.microsoft.com/en-us/dotnet/core/tools/)
* 🔗 [Entity Framework Docs](https://learn.microsoft.com/en-us/ef/core/)

---

**You're ready to build high-performance web apps with ASP.NET Core! 🎉**

```

---

Let me know if you also want `.md` files for:

- ASP.NET + React or Angular
- ASP.NET Identity (Login/Register)
- Entity Framework Database First
- Hosting on IIS or Azure

Just say the word!
```
