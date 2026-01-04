# SQL 

Docker basicamente é uma forma de que execute uma emulação de um ambiente pré-fabricado isoladamente e muito leve, como banco de dados, servidores, etc.

Exemplo, pra eu subir um banco de dados Postgree, posso simplesmente:

```bash
docker pull postgres:14
```

Isso faz com que eu apenas baixe, não crie nem rode nada, para poder trabalhar com ele:

```bash
docker run -e POSTGRES_PASSWORD=lol --name=pg --rm -d -p 5432:5432 postgres:14
```

POSTGRES_PASSWORD: é a senha do banco de dados, e --name, é literalmente o nome.

o --rm: sinaliza para que o container se exclua depois, ou seja, perde tudo dentro dele.. é tipo usado apenas para estudos, testes, etc..

# Primeiro plano vs Segundo plano

Por padrão, ao iniciar um container ele roda em primeiro plano

Nesse modo, o terminal fica ocupado pelo container, e você acompanha a execução diretamente pela saída no console, tipo ver os logs, se você fecha, mata o processo.

Para rodar em segundo plano, usa-se `--detach` ou `-d`, e o container passa a rodar sem ocupar a sua janela do terminal.

```bash
docker exec -u postgres -it pg psql
```

- `docker exec`: executa um comando em um container que já está em execução (diferente do `docker run`, que cria um novo).
    
- `-u postgres`: roda o comando como o usuário `postgres` dentro do container (útil porque esse é o usuário padrão de administração do Postgres).
    
- `-it`: combina modo interativo (`-i`) + alocação de TTY (`-t`), deixando a sessão "usável" como terminal.
    
- `pg`: é o nome do container (no seu caso, você criou com `--name=pg`).
    
- `psql`: é o cliente de linha de comando do PostgreSQL; é ele que abre o "console" para você rodar queries.
