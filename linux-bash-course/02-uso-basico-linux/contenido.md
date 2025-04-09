
# 🖥️ Uso Básico de Linux

Bienvenido a la segunda sección del curso. Aquí aprenderás los fundamentos más importantes para comenzar a trabajar con Linux desde la terminal. Al finalizar esta sección, tendrás soltura con los comandos esenciales, gestión de usuarios, procesos, paquetes, red y más.

---

## 🧭 Navegación por el sistema de archivos

### 🔹 Comandos esenciales:
```bash
pwd         # Muestra la ruta actual
ls          # Lista archivos del directorio
ls -la      # Lista todo con detalles
cd [ruta]   # Cambia de directorio
cd ~        # Ir al directorio personal
cd ..       # Subir un nivel
```

---

## 📂 Gestión de archivos y directorios

```bash
touch archivo.txt            # Crear un archivo vacío
mkdir nueva_carpeta          # Crear carpeta
cp origen.txt copia.txt      # Copiar archivo
mv viejo.txt nuevo.txt       # Mover o renombrar
rm archivo.txt               # Borrar archivo
rm -r carpeta/               # Borrar carpeta y contenido
```

---

## 📦 Gestión de paquetes

### 🔸 APT (Debian/Ubuntu)
```bash
sudo apt update              # Actualizar lista de paquetes
sudo apt upgrade             # Actualizar paquetes
sudo apt install nombre      # Instalar paquete
sudo apt remove nombre       # Eliminar paquete
sudo apt purge nombre        # Eliminar + config
```

### 🔸 DPKG (instalación manual)
```bash
sudo dpkg -i paquete.deb
sudo dpkg -r nombre
```

### 🔸 Flatpak & Snap
```bash
flatpak install flathub nombre
snap install nombre
```

---

## 🧑‍💻 Usuarios y permisos

```bash
whoami                       # Usuario actual
id                           # Ver UID, GID
sudo su                     # Cambiar a superusuario
adduser nuevo                # Crear usuario
passwd usuario               # Cambiar contraseña
deluser usuario              # Eliminar usuario

chmod +x archivo.sh          # Dar permisos de ejecución
chown usuario:grupo archivo  # Cambiar propietario
```

---

## 📄 Ver y editar archivos

```bash
cat archivo.txt              # Ver contenido
less archivo.txt             # Vista paginada
head -n 10 archivo.txt       # Primeras 10 líneas
tail -n 10 archivo.txt       # Últimas 10 líneas
nano archivo.txt             # Editar con Nano
```

---

## 🛠️ Pipes, grep y redirecciones

```bash
ls -la | grep ".txt"         # Buscar archivos .txt
cat archivo | less           # Pipe a less
echo "Hola" > saludo.txt     # Redirección a archivo
echo "Mundo" >> saludo.txt   # Añadir al archivo
```

---

## 🌐 Comandos de red

```bash
ip a                         # Ver IPs
ping 8.8.8.8                 # Comprobar conexión
curl ifconfig.me             # Obtener IP pública
wget http://sitio.com        # Descargar archivo
scp archivo usuario@ip:/ruta # Copiar por SSH
```

---

## ⚙️ Procesos

```bash
ps aux                       # Ver todos los procesos
top                          # Monitorizar en tiempo real
htop                         # Versión mejorada de top
kill PID                     # Finalizar proceso
killall nombre               # Finalizar todos con ese nombre
```

---

## 📑 MAN y ayuda

```bash
man comando                  # Manual de comando
comando --help               # Ayuda básica
```

---

## 🧪 Ejercicios sugeridos

1. Crea, edita y elimina archivos desde la terminal.
2. Instala una app con `apt`, otra con `flatpak`.
3. Crea un usuario nuevo y cambia su contraseña.
4. Visualiza los procesos activos y mata uno ficticio.
5. Usa `grep` para buscar palabras en archivos.

---

Este bloque de conocimiento es esencial para cualquier usuario o administrador de sistemas Linux. Practica todo lo posible en tu VM y no tengas miedo de equivocarte. ¡Sigue aprendiendo!

