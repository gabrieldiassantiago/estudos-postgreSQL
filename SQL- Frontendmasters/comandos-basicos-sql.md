# Comandos Básicos SQL

## Criando um Banco de Dados

```sql
CREATE DATABASE recipeguru;
```

Desta forma, você cria um banco de dados dentro do Postgres. Isto é, exemplo: ifood, uber... e dentro dele, você terá as tabelas e relações.

## Criando uma Tabela
  id INTEGER PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
  title VARCHAR ( 255 ) UNIQUE NOT NULL
);
```

> **Nota:** INT, INT4 ou INTEGER são a mesma coisa. Da mesma forma, DEC, FIXED e DECIMAL são a mesma coisa.

**Resumindo:** `VARCHAR(255)` é uma string de comprimento máximo de 255 caracteres e `INTEGER` é um número inteiro, tipo (2) dois.

Assim, temos uma mesa, uma tabela é o repositório real de dados. Pense em um banco de dados como uma pasta e em uma tabela como uma planilha. Você pode ter muitas planilhas em uma pasta. O mesmo acontece com as tabelas.

## Alterando uma Tabela

### Adicionando uma Coluna

```sql
ALTER TABLE ingredients ADD COLUMN image VARCHAR ( 255 );
```

Isso altera a tabela, e cria uma coluna chamada `image`, do tipo string, máximo 255 caracteres.

### Removendo uma Coluna

Da mesma forma, podemos abandoná-la também:

```sql
ALTER TABLE ingredients DROP COLUMN image;
```

Traduzindo: altere tabela ingredientes e delete a coluna images dentro da tabela correspondente



