
#Adding Repositories

Usually a repository represent a table structure from the database. But in this mapper the repository is more a representation of the expected result from executing a query. To create a repository first w need to create it's **Plain Old CLR Object (POCO)** class. In the example below I'll use a simple user structure to clarify.

Example:
```
public class User
{
    public int? Id { get; set; }

    public string UserName { get; set; }

    public string FirstName { get; set; }

    public string LastName { get; set; }
}
```

To declare this `User` class in our context class. Please see [Creating a Context](https://github.com/AndrewFahmy/SqlMapper/blob/master/docs/context.md) first for further understanding

```
public class Context : ContextBase<SqlConnection>
{
    public Context(string connectionString) : base(connectionString)
    {
    }


    public IRepository<User> Users { get; set; }
}
```

And that's it now you can use this repository in your application. To See all available repository methods to use please see [Repository Level Methods](https://github.com/AndrewFahmy/SqlMapper/blob/master/docs/repository_methods.md)
