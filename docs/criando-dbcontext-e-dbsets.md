### Criando o DbContext e DbSet's

Instalar os pacotes:

- Microsoft.EntityFrameworkCore.SqlServer
- Microsoft.EntityFrameworkCore.Tools

Instalação via linha de comando:

~~~sh
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
~~~

Criar a classe de contexto.

~~~c#
using Projeto.Core.Entities;
using Microsoft.EntityFrameworkCore;
using System;
using System.Collections.Generic;

namespace Projeto.Infrastructure.Persistence
{
    public class ProjetoDbContext : DbContext
    {
        public ProjetoDbContext(DbContextOptions<ProjetoDbContext> options) : base(options)
        {

        }

        public DbSet<Category> Categories {get; set; }
        public DbSet<Product> Products {get; set; }
        public DbSet<User> Users {get; set; }
        public DbSet<UserGroup> UserGroups {get; set; }
    }
}
~~~

[Home](../README.md) | [Configuração das Entidades](/docs/configuracao-das-entidades.md)
