# Container de Exemplo com Docker, Docker-compose, PHP8, Nginx, MySQL e driver pdo_sqlsrv

Você precisa ter o Docker e o Docker Compose instalados em seu servidor para continuar usando este ambiente PHP.

Os três contêineres de serviço separados a seguir serão usados:

- Um serviço `app` rodando PHP 8 FPM.
- Um serviço `db` executando MySQL.
- Um serviço `nginx` que usa o serviço` app` para analisar o código PHP antes de servir o aplicativo ao usuário final.

## Administrando o ambiente

- Defina as variáveis de ambiente MySQL criando um arquivo `.env` baseado no arquivo` .env.example`. (se preferir, salve o arquivo .env.exemple como .env)

- Crie a imagem do aplicativo com o seguinte comando:

```bash
docker-compose build app
```

- Quando a compilação for concluída, você pode executar o ambiente em modo de segundo plano com:

```bash
docker-compose up --build -d
```

- To show information about the state of your active services, run:

```bash
docker-compose ps
```

Você pode usar o comando `docker-compose exec` para executar comandos nos contêineres de serviço, como um` ls -l` para mostrar informações detalhadas sobre os arquivos no diretório do aplicativo:

```bash
docker-compose exec app ls -l
```

- Agora vá para o seu navegador e acesse o nome de domínio ou endereço IP do seu servidor na porta `8000`:` http: // server_domain_or_IP:8000`. Caso você esteja executando este demo em sua máquina local, use `http://localhost:8000` para acessar o aplicativo de seu navegador.

- Você pode usar o comando logs para verificar os logs gerados por seus serviços:

```bash
docker-compose logs nginx
```

- Se você deseja pausar seu ambiente Docker Compose enquanto mantém o estado de todos os seus serviços, execute:

```bash
docker-compose pause
```

- Você pode então retomar seus serviços com:

```bash
docker-compose unpause
```

- Para desligar seu ambiente Docker Compose e remover todos os seus contêineres, redes e volumes, execute:

```bash
docker-compose down
```
- Para pausar sem remover os container e volumes:

```bash
docker-compose stop
```

- Para iniciar novamente os containers:

```bash
docker-compose start
```
