# ASP.NET
## [nuget package](https://www.nuget.org/packages)
### Use MySQL
- add package   
  .NET CLI (terminal)
```
> dotnet add package Mysql.EntityFrameworkCore --verion 7.0.2
or
> dotnet add [Project Name] package Mysql.EntityFrameworkCore --verion 7.0.2

version 7.0.2 : MySQL8.0.33
```

- add db info   
  file name : appsttings.json
```json
"ConnectionStrings": {
  "DB": "Server=localhost; port=3306; Database=xxx; user=xxx; password=xxxx"
}
```

- add code : Program.cs
```c#
    var dbConnection = builder.Configuration.GetConnectionString("DB") ?? throw new InvalidOperationException("Connection string 'DB' not found. file_name=appsettings.json. root_key=ConnectionString");
    builder.Services.AddDbContextPool<DBContext>(options =>
        options.UseMySQL(dbConnection));

```
