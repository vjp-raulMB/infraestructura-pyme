# Monitorización del sistema

## Objetivo

Implementar un sistema de monitorización sencillo que permita supervisar:

* Uso de CPU
* Uso de RAM
* Espacio en disco
* Estado de Apache
* Estado de MariaDB
* Conexiones de red

## Herramienta elegida

Se utilizará **Netdata** por su facilidad de instalación y monitorización en tiempo real.

## Instalación de Netdata

1. Actualizar paquetes:

   ```bash
   sudo apt update
   ```

2. Instalar Netdata:

   ```bash
   bash <(curl -Ss https://my-netdata.io/kickstart.sh)
   ```

## Verificación del servicio

```bash
sudo systemctl status netdata
```

## Acceso web

La interfaz web estará disponible en:
[http://IP_SERVIDOR:19999](http://IP_SERVIDOR:19999)

## Apertura de puerto en UFW

```bash
sudo ufw allow 19999/tcp
```

## Métricas importantes

| Métrica | Descripción |
| :--- | :--- |
| **CPU** | Carga del procesador |
| **RAM** | Memoria utilizada |
| **Disk** | Espacio en disco |
| **Apache** | Estado del servidor web |
| **MariaDB** | Actividad de base de datos |

## Recomendaciones

* Limitar acceso a Netdata por IP
* Monitorizar logs semanalmente
* Configurar alertas futuras

bash <(curl -Ss https://my-netdata.io/kickstart.sh)

http://IP_SERVIDOR:19999