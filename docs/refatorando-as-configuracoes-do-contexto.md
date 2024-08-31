### Refatorando as configurações do Contexto

É possível criar classes que implementam a interface **IEntityTypeConfiguration<T>**, onde **T** é a classe a ser configurada, e migrar o código para ela.

Criar uma pasta **Infrastructure/Persistence/Configurations**, e dentro dela criar os arquivos de configuração para cada DbSet.

~~~c#
using Projeto.Core.Entities;
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;
using System;

namespace Projeto.Infrastructure.Persistence.Configurations
{
    public class ProjectConfigurations : IEntityTypeConfiguration<Project>
    {
        public void Configure(EntityTypeBuilder<Project> builder)
        {
            builder
            .HasKey(p => p.Id);

            builder
            .HasOne(p => p.FreeLancer)
            .HasMany(f => f.FreelanceProjects)
            .HasForeignKey(p => p.IdFreelancer)
            .OnDelete(DeleteBehavior.Restrict);

            builder
            .HasOne(p => p.Client)
            .WithMany(f => f.OwnedProjects)
            .HasForeignKey(p => p.IdClient)
            .OnDelete(DeleteBehavior.Restrict);
        }
    }
}

~~~

[Home](../README.md) 
