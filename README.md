# Entity Framework Datasheet

## Datasheet.pdf and README.md with a Entity Framework description and examples.

Datasheet on Entity Framework (EF) that helps other students implement advanced Object Relational Mapping (ORM). It breaks down create, read, update and delete (CRUD) operation utilisation as well as how to query data.

### Code Examples: ###
**Installation**<br>
EF Core provider package corresponding with PostgreSQL database
```
dotnet add package Microsoft.EntityFrameworkCore.PostgreSQL
```

**Context Class**<br>
The `ExampleContext` class is derived from `DbContext` which makes it a context class. It includes three entities `Cats`, `Dogs` & `Fish`.  
```
public class ExampleContext : DbContext
{
    public ExampleContext()
    {

    }

    public DbSet<Cat> Cats { get; set; }
    public DbSet<Dog> Dogs { get; set; }
    public DbSet<Meal> Meals { get; set; }
}
```
**CRUD Operations**<br>
```
using var petContext = new ExampleContext();

// Create - Adding a dog
petContext.Add(new Dog { Name = "Charlie"});
petContext.SaveChanges();

// Read - Querying for a cat
var cat = petContext.Single(c => c.Name = "Mittens");

// Update - Adding a meal to a cat
cat.Meals.Add(new Meal { Food = "Tuna", Weight = "50grams" });
petContext.SaveChanges();

// Delete - removing cat from the database
petContext.Remove(cat);
petContext.SaveChanges();
```