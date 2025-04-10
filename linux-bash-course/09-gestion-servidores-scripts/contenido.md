
# 🖥️ Gestión de Servidores con Scripts de Bash

Esta sección está orientada a la automatización de tareas en servidores usando Bash, incluyendo configuración de FTP, SSH y copias de seguridad. Ideal para administradores de sistemas o entornos auto-gestionados.

---

## 🧪 Instalación de Ubuntu Server

Puedes instalar Ubuntu Server en una máquina virtual (VirtualBox o Proxmox) como entorno de laboratorio:

1. Descarga ISO desde [ubuntu.com](https://ubuntu.com/download/server)
2. Asigna al menos 2GB de RAM y 2 CPU
3. Durante la instalación selecciona:
   - OpenSSH Server
   - Standard Utilities

---

## 🌐 Cómo Crear un Servidor FTP con VSFTPD

Instalación:
```bash
sudo apt update && sudo apt install vsftpd -y
```

Habilita el servicio:
```bash
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
```

Archivo de configuración:
```bash
sudo nano /etc/vsftpd.conf
```

Recomendaciones:
- Habilita `local_enable=YES`
- Desactiva `anonymous_enable=NO`
- Usa `chroot_local_user=YES` para aislar a los usuarios

---

## 🔁 Automatización de Servidores FTP (Parte 1 y 2)

Crear usuarios con acceso restringido:
```bash
sudo useradd -m usuarioftp
sudo passwd usuarioftp
```

Script para reiniciar servicio automáticamente:
```bash
#!/bin/bash
systemctl restart vsftpd
echo "FTP reiniciado correctamente"
```

---

## 🔐 Cómo Crear un Servidor SSH con OpenSSH

Instalación:
```bash
sudo apt install openssh-server
```

Verifica el estado:
```bash
sudo systemctl status ssh
```

---

## 🔐 Acceso Automático vía SSH (clave pública)

Desde tu cliente:
```bash
ssh-keygen
ssh-copy-id usuario@IP_SERVIDOR
```

Esto permite conectarte sin usar contraseña, ideal para scripts automatizados.

---

## 💾 Automatización de Copias de Seguridad vía SSH

Ejemplo con `rsync`:
```bash
#!/bin/bash
rsync -avz /home/usuario/backup/ usuario@192.168.1.10:/mnt/servidor/
```

Se puede ejecutar con `cron` para hacerlo periódico:
```bash
crontab -e
# Añadir:
0 2 * * * /ruta/script-backup.sh
```

---

## 🧪 Ejercicios sugeridos

1. Crea un script que cree usuarios para FTP y configure sus permisos.
2. Automatiza el reinicio de servicios `ssh` y `vsftpd` si están inactivos.
3. Configura copias automáticas con `rsync` vía SSH.
4. Implementa scripts que generen backups comprimidos (`tar.gz`).
5. Usa `scp` para enviar archivos desde un cliente al servidor.

---

Dominar estas herramientas y prácticas te permitirá administrar servidores de forma profesional, segura y automatizada.
