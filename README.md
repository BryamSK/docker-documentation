# Show information and documentation of running Docker services at Linux OS startup
## Add bash in update-motd.d

cd /etc/update-motd.d/ && touch 99-service && chmod +x 99-serices

vim 99-serices

```code
#!/bin/sh
SERVICE=DOCKER
COMPOSE=$(docker compose version)
DOCKER=$(docker -v)
STATS=$(docker stats --no-stream)
PRINTF='# Servidor '$SERVICIO'
| Programa       | version                                |
| :--------------| :------------------------------------- |
| Docker         | '$DOCKER'   |
| Docker Compose | '$COMPOSE'         |


## Service Management '$SERVICE'
-Detener e iniciar
        systemct restart docker
        systemct stop docker
        systemct stary docker

## Servicios en ejecución
| Servicio       | Port      | Descripcion          | Service Name          |Ruta      |
| :------------- | :-------- | :------------------- | :-------------------- |:-------- |
| **Service**    | port      | Servidor Descripcion | Service.service       |/PATH/    |

**** [Container List] ****
'$STATS'
**** [Container End] ****

## Documentación

'
printf '%s\n' "$PRINTF"

```

## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://bryamsk.github.io/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bryam-herrera-6a06b7a6/)
