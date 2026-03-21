# Painel de Implantação DPSP + PedBot

Painel estático servido via nginx em container Docker.

## Requisitos

- Docker
- Docker Compose

## Subir localmente

```bash
docker compose up -d
```

Acesse em: http://localhost

## Build manual

```bash
docker build -t dpsp-painel .
docker run -d -p 80:80 --name dpsp-painel dpsp-painel
```

## Deploy em servidor público

### VPS (Ubuntu/Debian)

```bash
# Instalar Docker
curl -fsSL https://get.docker.com | sh

# Clonar / copiar os arquivos para o servidor
# Subir o container
docker compose up -d
```

O painel estará disponível na porta 80 do servidor.
Para HTTPS, recomenda-se colocar um proxy reverso (ex: Nginx externo ou Caddy) na frente.

### Parar

```bash
docker compose down
```

### Atualizar o painel

Edite o `index.html` e rode:

```bash
docker compose up -d --build
```
# estrategia-implantacao
