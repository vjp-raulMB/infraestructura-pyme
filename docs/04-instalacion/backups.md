# Política de copias de seguridad

## Objetivo
Garantizar la recuperación de la información crítica de la empresa.

## Elementos a respaldar
* Bases de datos MariaDB
* Archivos web
* Configuración de Apache
* Configuración SSH y UFW

## Herramientas utilizadas
* `mysqldump`
* `rsync`
* `cron`

## Backup de bases de datos
```bash
mysqldump -u root -p web_empresa > /backups/web_empresa.sql
mysqldump -u root -p gestion_interna > /backups/gestion_interna.sql
```

## Backup de archivos web
```bash
rsync -avz /var/www/html /backups/web/
```

## Automatización con cron
1. Editar tareas programadas:
   ```bash
   crontab -e
   ```
2. Tarea diaria a las 02:00:
   ```cron
   0 2 * * * /usr/local/bin/backup.sh
   ```

## Rotación de backups
Se conservarán:
* 7 copias diarias
* 4 copias semanales
* 3 copias mensuales

## Almacenamiento externo
Las copias se sincronizarán a un servidor secundario mediante `rsync`.

## Restauración básica
```bash
mysql -u root -p web_empresa < web_empresa.sql
```

## Recomendaciones
* Probar restauraciones periódicamente
* Verificar integridad de copias
* Cifrar backups sensibles
