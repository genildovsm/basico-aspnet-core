### Configuração das Entidades

Método OnModelCreating

~~~c#
...

protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.Entity<T>()...
}

...
~~~

Configuraçãoes mais comuns:

| CONFIGURAÇÃO | DESCRIÇÃO |
| :--- | :--- |
| **ToTable** | Define o nome da tabela do banco de dados |
| **HasKey** | Define a chave primária |
| **HasData** | Define um conjunto de dados iniciais |
| **Property** | Configura as propriedades |
| **HasMaxLength** | Tamanho máximo |
| **HasColumnName** | Nome da coluna da tabela |
| **IsRequired** | Define que o campo não pode ser nulo |
| **HasDefaultValueSql** | Define um valor padrão inicial usando uma expressão SQL |

[Home](../README.md) | [Refatorando as configurações do Contexto](/docs/refatorando-as-configuracoes-do-contexto.md)
