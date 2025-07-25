# Proyecto Ansible - InnovaSys 🚀

Este proyecto automatiza la configuración de un servidor Ubuntu 24.04 para la startup ficticia **InnovaSys**, utilizando Ansible desde un nodo de control Linux Lite.

## Objetivo

Configurar de forma automatizada:

- ✅ Un servidor web Apache con una página de bienvenida personalizada generada desde una plantilla Jinja2.
- ✅ Un recurso compartido Samba autenticado para el equipo de desarrollo, accesible solo con usuario y contraseña.

## Estructura del proyecto

ansible_innovasys/
├── hosts
├── site.yml
├── roles/
│ ├── apache/
│ │ ├── tasks/
│ │ ├── handlers/
│ │ ├── templates/
│ │ └── vars/
│ └── samba/
│ ├── tasks/
│ ├── handlers/


## Requisitos

- Linux Lite como nodo de control con Ansible instalado
- Ubuntu Server 24.04 como nodo gestionado
- Conexión SSH configurada (clave sin contraseña)
- Red interna en VirtualBox (por ejemplo 192.168.10.0/24)

## Ejecución

En el nodo de control:

ansible-playbook -i hosts site.yml --ask-become-pass


## Accesos de prueba
Web Intranet
Acceder desde el navegador a:
`http://192.168.10.100`


## Carpeta compartida Samba
Conectarse desde el gestor de archivos (Linux Lite) a:
`smb://192.168.10.100/Proyectos`

Usar:
Usuario: devuser1
Contraseña: Innova.2025
