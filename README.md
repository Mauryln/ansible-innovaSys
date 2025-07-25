# Proyecto Ansible - InnovaSys

Este proyecto automatiza la configuración de un servidor Ubuntu 24.04 con dos servicios:

- Un servidor web Apache con una página de bienvenida personalizada
- Un servidor Samba con acceso autenticado al recurso compartido "Proyectos"

## Estructura del proyecto

- `site.yml`: Playbook principal
- `hosts`: Inventario con la IP del servidor gestionado
- `roles/apache`: Rol para instalar y configurar Apache
- `roles/samba`: Rol para instalar y configurar Samba

## Requisitos

- Ansible instalado en el nodo de control
- Clave SSH sin contraseña para conexión
- Ubuntu Server 24.04 como nodo gestionado

## Ejecución

```bash
ansible-playbook -i hosts site.yml --ask-become-pass
