
# 🔐 Gestión de Permisos y Tratamiento de la Información

En esta sección te sumergirás en el sistema de permisos de archivos de Linux, el cual permite un control preciso sobre quién puede leer, escribir o ejecutar cualquier archivo o directorio. También verás herramientas útiles para ordenar información, buscar archivos y manipular la entrada/salida.

---

## 🧾 Permisos en Linux

Cada archivo/directorio tiene asociados **tres tipos de permisos** para tres tipos de usuarios:

- **Usuario** (owner)
- **Grupo** (group)
- **Otros** (others)

### 🛠️ Comando `chmod` (gestión de permisos)

```bash
chmod +x archivo.sh         # Añade permiso de ejecución
chmod -r archivo.txt        # Quita permiso de lectura
chmod u+x script.sh         # Añade ejecución solo al propietario
```

### 🔢 Modo numérico

```bash
chmod 755 archivo.sh        # rwxr-xr-x
chmod 644 documento.txt     # rw-r--r--
```

| Número | Permisos  |
|--------|-----------|
| 7      | rwx       |
| 6      | rw-       |
| 5      | r-x       |
| 4      | r--       |
| 3      | -wx       |
| 2      | -w-       |
| 1      | --x       |
| 0      | ---       |

---

## 👥 Gestión de Grupos

```bash
groupadd desarrolladores
usermod -aG desarrolladores usuario
groups usuario
```

---

## 🗂️ Comprimir y descomprimir archivos

```bash
tar -cvf archivo.tar carpeta/
tar -xvf archivo.tar

gzip archivo.txt
gunzip archivo.txt.gz

zip archivo.zip archivo.txt
unzip archivo.zip
```

---

## 🔍 Buscar archivos y redirigir errores

```bash
find / -name "archivo.txt" 2>/dev/null       # Evitar errores de permisos
find . -type f -size +1M                     # Archivos mayores a 1 MB
```

---

## 🔄 Comando `xargs`

```bash
ls *.log | xargs rm                          # Elimina todos los .log
find . -name "*.bak" | xargs -I {} mv {} backups/
```

---

## 📥 stdout, stderr y stdin

```bash
comando > salida.txt                         # stdout
comando 2> errores.txt                       # stderr
comando &> todo.txt                          # stdout + stderr
```

---

## 📊 Ordenar información (textos)

```bash
sort archivo.txt
sort -r archivo.txt                         # Reverso
head -n 5 archivo.txt
tail -n 5 archivo.txt
wc -l archivo.txt                           # Contar líneas
uniq archivo.txt
```

---

## ⭐ Permisos Especiales

### Sticky Bit
```bash
chmod +t carpeta/
```
- Solo el creador puede borrar archivos en el directorio, útil en `/tmp`.

### SUID
```bash
chmod u+s programa
```
- El programa se ejecuta con los privilegios del propietario (ej: `passwd`).

---

## 🧪 Ejercicios Sugeridos

1. Crea un archivo con permisos `rw-r--r--`.
2. Usa `find` para listar archivos modificados hoy.
3. Comprime y descomprime un conjunto de archivos.
4. Aplica un Sticky Bit a una carpeta de pruebas.
5. Crea un script que capture errores en un `.log`.

---

Dominar estos conceptos te permitirá trabajar con seguridad, mantener buenas prácticas de administración y automatizar tareas del día a día.

