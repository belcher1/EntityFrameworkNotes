# Entity Framework Datasheet

## Datasheet.pdf and README.md with a Entity Framework description and examples.

Datasheet on Entity Framework (EF) that helps other students implement advanced Object Relational Mapping (ORM). It breaks down create, read, update and delete (CRUD) operation utilisation as well as how to query data.

Code Examples:
**Installation**
EF Core provider package corresponding with PostgreSQL database
```
dotnet add package Microsoft.EntityFrameworkCore.PostgreSQL
```

**Context Class**
The `ExampleContext` class is derived from `DbContext` which makes it a context class. It includes three entities `Entity1`, `Entity2` & `Entity3`.  
```
public class ExampleContext : DbContext
{
    public ExampleContext()
    {

    }

    public DbSet<Entity1> { get; set; }
    public DbSet<Entity2> { get; set; }
    public DbSet<Entity3> { get; set; }
}
```