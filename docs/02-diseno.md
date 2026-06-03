# Diseño de infraestructura

## Arquitectura general

Internet
↓
Router/Firewall
↓
Servidor Ubuntu 22.04
├── Apache2 + PHP
├── MariaDB
├── SSH
├── UFW
└── Netdata

## Versiones de software

| Componente    | Versión   | Función           |
| ------------- | --------- | ----------------- |
| Ubuntu Server | 22.04 LTS | Sistema operativo |
| Apache        | 2.4.57    | Servidor web      |
| PHP           | 8.2       | Backend           |
| MariaDB       | 10.11     | Base de datos     |

## Puertos necesarios

| Puerto | Servicio |
| ------ | -------- |
| 22     | SSH      |
| 80     | HTTP     |
| 443    | HTTPS    |
| 19999  | Netdata  |
