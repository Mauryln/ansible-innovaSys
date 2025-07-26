# Proyecto Ansible - InnovaSys 🚀

Este proyecto automatiza la configuración de un servidor **Ubuntu Server 24.04** para la startup ficticia **InnovaSys**, utilizando **Ansible** desde un nodo de control **Linux Lite**.

---

### 🎯 Objetivo

Configurar de forma totalmente automatizada:

- ✅ Un **servidor web Apache** con una **página de bienvenida personalizada** generada desde una **plantilla Jinja2**.
- ✅ Un **recurso compartido Samba** protegido con autenticación, exclusivo para el equipo de desarrollo.

---

### 📁 Estructura del Proyecto

```
ansible_innovasys/
├── hosts                  # Inventario de Ansible
├── site.yml               # Playbook principal
└── roles/
    ├── apache/
    │   ├── tasks/
    │   ├── handlers/
    │   ├── templates/
    │   └── vars/
    └── samba/
        ├── tasks/
        ├── handlers/
```

---

### 🛠️ Requisitos

- Nodo de control: **Linux Lite** con **Ansible instalado**
- Nodo gestionado: **Ubuntu Server 24.04**
- Conexión SSH configurada sin contraseña (con clave pública)
- Red interna en VirtualBox (ejemplo: `192.168.10.0/24`)

---

### ▶️ Ejecución del Proyecto

En el nodo de control, ejecutar:

```bash
ansible-playbook -i hosts site.yml --ask-become-pass
```

---

### 🔍 Verificación

#### 🌐 Web Intranet
Accede desde el navegador a:

```
http://192.168.10.100
```

Debería verse una página con el mensaje:

```html
<h1>Bienvenidos a la Intranet de InnovaSys</h1>
```

#### 📁 Carpeta Compartida Samba

Desde el **gestor de archivos de Linux Lite**:

```
smb://192.168.10.100/Proyectos
```

Usa estas credenciales:

- **Usuario:** `devuser1`
- **Contraseña:** `Innova.2025`

Debes poder **crear archivos** dentro del recurso compartido.

---

### 📸 Capturas de Pantalla

- ✅ Página web personalizada cargando correctamente.
- ✅ Acceso exitoso al recurso Samba con autenticación.
- ✅ Comprobación del contenido del directorio compartido.

> Las capturas se encuentran en el informe PDF adjunto.

---

### 📦 Repositorio

Repositorio del proyecto:  
🔗 [https://github.com/Mauryln/ansible-innovaSys](https://github.com/Mauryln/ansible-innovaSys)

---

### ✅ Estado: Entregado y Verificado

Este proyecto fue verificado en un entorno VirtualBox con las siguientes IPs de prueba:

- **Servidor Ubuntu:** `192.168.10.100`
- **Cliente Linux Lite:** `192.168.10.151`
