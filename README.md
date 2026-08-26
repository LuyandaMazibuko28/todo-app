# TodoApp — Simple CRUD ASP.NET Core MVC App

A minimal but complete task manager built with:
- **ASP.NET Core 8.0 MVC** (Razor views, no client-side framework needed)
- **Entity Framework Core** with **SQLite** (file-based, zero setup)

## Features
- List all tasks (Index)
- View task details
- Create a new task
- Edit an existing task
- Delete a task (with confirmation)
- One-click toggle for marking a task complete/incomplete
- Server-side validation (required title, max lengths)

## Prerequisites
- [.NET 8 SDK](https://dotnet.microsoft.com/download) installed

## Run it

```bash
cd TodoApp
dotnet restore
dotnet run
```

Then open the URL shown in the console (usually `https://localhost:5001` or `http://localhost:5000`).

The SQLite database file (`todoapp.db`) is created automatically on first run in the project folder — no migrations or manual setup needed (`Database.EnsureCreated()` handles it in `Program.cs`).

## Project structure

```
TodoApp/
├── Controllers/
│   └── TodoItemsController.cs   # All CRUD actions
├── Models/
│   └── TodoItem.cs              # Task entity + validation attributes
├── Data/
│   └── AppDbContext.cs          # EF Core DbContext
├── Views/
│   ├── TodoItems/                # Index, Create, Edit, Details, Delete
│   └── Shared/_Layout.cshtml
├── wwwroot/css/site.css         # Styling
├── Program.cs                   # App startup & DI wiring
└── appsettings.json
```

## Extending it
Some easy next steps if you want to keep playing with it:
- Add categories/tags (many-to-many relationship)
- Add search/filter on the Index page
- Swap SQLite for SQL Server by changing the connection string and `UseSqlite` → `UseSqlServer`
- Add a REST API alongside the MVC views (add a `[ApiController]` alongside the existing controller)
- Add user accounts with ASP.NET Core Identity so tasks are per-user
