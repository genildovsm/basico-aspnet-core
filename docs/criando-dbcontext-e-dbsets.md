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

        public DbSet<Project> Projects {get; set; }

        protected override void OnModelCreating(ModelBuilder modelBuilder)
        {
            // Todas as classes que implementam a interface IEntityTypeConfiguration<T>
            // serão lidas e configuradas automaticamente
            modelBuilder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());
        }
    }
}
~~~

[Home](../README.md) | [Configuração das Entidades](/docs/configuracao-das-entidades.md)
