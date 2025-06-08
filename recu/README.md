# 📘 API REST con Persistencia de Datos usando SQLite (ASP.NET Core)

## 🎯 Objetivo de la práctica

- Reutilizar el proyecto de ejemplo del tutorial oficial de Microsoft:
  [Tutorial: Crear una API Web con ASP.NET Core](https://learn.microsoft.com/es-es/aspnet/core/tutorials/first-web-api)
- Sustituir la persistencia en memoria por **SQLite** mediante **Entity Framework Core**.
- Crear un **modelo propio** distinto al ejemplo original.
- Probar los endpoints con Swagger y archivo `.http`.

---

## 🧱 Estructura implementada

- Se ha definido un modelo personalizado: `Libro.cs`, con propiedades `Id`, `Titulo`, `Autor` y `Año`.
- Se ha creado un controlador `LibrosController.cs` que gestiona operaciones CRUD sobre libros.
- Se ha configurado una base de datos `SQLite` llamada `todo.db` para almacenar los datos de forma persistente.

---

## ⚙️ Pasos técnicos destacados

1. **Paquete SQLite** instalado:
   ```bash
   dotnet add package Microsoft.EntityFrameworkCore.Sqlite

2. **Inyeccion del DbContext en Program.cs**:
builder.Services.AddDbContext<AppDbContext>(options =>
    options.UseSqlite(builder.Configuration.GetConnectionString("DefaultConnection")));


3. **Inyeccion del DbContext en Program.cs**:
"ConnectionStrings": {
  "DefaultConnection": "DataSource=recu.db"
}

4. **Migraciones EF Core ejecutadas para crear la base de datos**:
dotnet tool install --global dotnet-ef
dotnet ef migrations add InitialCreate
dotnet ef database update

5. **Pruebas funcionales con Swagger desde**:
http://localhost:5063/swagger/index.html

6. **Archivo libros.http añadido para facilitar pruebas REST**


## RESULTADO

La API ahora permite crear, consultar, actualizar y eliminar libros, almacenándolos de forma persistente en la base de datos recu.db.