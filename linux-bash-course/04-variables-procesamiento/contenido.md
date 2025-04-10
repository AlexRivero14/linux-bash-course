
# 🔧 Variables y Procesamiento de la Información en Bash

Esta sección se centra en las **variables en Bash**, la **manipulación de texto**, y la **automatización del tratamiento de la información** usando herramientas poderosas como `awk`, `sed`, `cut`, y más.

---

## 📌 Variables en Bash

### 📍 Declarar y usar variables
```bash
nombre="Alex"
echo $nombre
```

### 🖨️ Guardar output en variables
```bash
fecha=$(date)
echo "Hoy es: $fecha"
```

### ⌨️ Entrada de datos con `read`
```bash
read -p "Introduce tu nombre: " nombre
echo "Hola, $nombre"
```

---

## 🧮 Parámetros y Variables especiales

| Variable | Descripción |
|----------|-------------|
| `$0`     | Nombre del script |
| `$1`, `$2`, ... | Argumentos pasados |
| `$#`     | Número de argumentos |
| `$@`     | Todos los argumentos como lista |
| `$?`     | Código de salida del último comando |

```bash
echo "Se han pasado $# argumentos"
```

---

## 🛠️ Procesadores de información

### 🔤 `tr` – Sustituir caracteres
```bash
echo "linux" | tr a-z A-Z
```

### 🧮 `awk` – Potente procesador de texto por columnas
```bash
awk '{print $1, $3}' archivo.txt
```

### ✂️ `cut` – Extraer columnas o campos
```bash
cut -d':' -f1 /etc/passwd
```

### ✂️ `sed` – Reemplazo de patrones y edición
```bash
sed 's/rojo/azul/g' archivo.txt
```

---

## ⚙️ Automatización con scripts

### 🔁 Script para tratamiento de la información
```bash
#!/bin/bash
for archivo in *.log; do
  grep "ERROR" "$archivo" >> errores.txt
done
```

### 🔍 Script para búsquedas automatizadas
```bash
#!/bin/bash
read -p "Palabra a buscar: " palabra
grep -r "$palabra" /var/log
```

---

## 🧪 Ejercicios sugeridos

1. Crea una variable con tu nombre y muéstrala en pantalla.
2. Crea un script que reciba un argumento y lo use como nombre de archivo.
3. Usa `awk` para mostrar solo el usuario y el shell por defecto de `/etc/passwd`.
4. Usa `sed` para reemplazar palabras en múltiples archivos.
5. Automatiza un script que busque errores y guarde los resultados.

---

El dominio de estas herramientas te permitirá escribir scripts potentes para procesar datos, auditar logs y automatizar tareas del sistema. ¡Practica y prueba sin miedo!
