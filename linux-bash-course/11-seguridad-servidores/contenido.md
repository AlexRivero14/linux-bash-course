
# 🔐 Seguridad en Servidores Linux

En esta sección aprenderás a proteger servicios esenciales como SSH y FTP, así como a aplicar buenas prácticas para asegurar servidores web Apache frente a amenazas comunes.

---

## 🛡️ Protección del Protocolo SSH

- Desactiva el login como root:
```bash
sudo nano /etc/ssh/sshd_config
# Cambiar:
PermitRootLogin no
```

- Cambiar el puerto por defecto:
```bash
Port 2222
```

- Limita usuarios permitidos:
```bash
AllowUsers usuario1 usuario2
```

- Aplica clave pública/privada y desactiva contraseñas:
```bash
PasswordAuthentication no
```

Reinicia el servicio:
```bash
sudo systemctl restart ssh
```

---

## 🔐 Protección del Protocolo FTP

- Desactiva FTP anónimo en `/etc/vsftpd.conf`:
```bash
anonymous_enable=NO
local_enable=YES
chroot_local_user=YES
```

- Usa SFTP como alternativa más segura (ya incluido con SSH).

---

## 🌐 Securización de Servidores Web Apache

### Parte 1: Instalar y configurar Apache

```bash
sudo apt update && sudo apt install apache2 -y
sudo ufw allow 'Apache Full'
```

### Parte 2: Seguridad básica

- Oculta versión del servidor:
```bash
sudo nano /etc/apache2/conf-available/security.conf
ServerSignature Off
ServerTokens Prod
```

- Limita el acceso a directorios:
```bash
<Directory /var/www/html>
    Options -Indexes
</Directory>
```

### Parte 3: Restringir acceso a archivos sensibles

Bloquear por extensión:
```apache
<FilesMatch "\.(htaccess|env|git|log)$">
    Require all denied
</FilesMatch>
```

### Parte 4: Prevenir Fuzzing Web

Bloquear ataques por user-agent o patrones:

```bash
sudo apt install libapache2-mod-security2
sudo a2enmod security2
```

Editar reglas de seguridad OWASP o personalizadas para bloquear fuzzers (`dirb`, `gobuster`, etc.).

---

## ✅ Buenas prácticas adicionales

- Actualiza siempre con:
```bash
sudo apt update && sudo apt upgrade
```

- Instala y configura un firewall:
```bash
sudo apt install ufw
sudo ufw enable
sudo ufw allow ssh
```

- Revisa logs:
```bash
sudo tail -f /var/log/auth.log
```

---

La seguridad de un servidor es una capa fundamental de cualquier infraestructura. Automatizar buenas prácticas desde el inicio es clave para evitar vulnerabilidades.
