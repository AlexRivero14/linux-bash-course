
# 馃敡 Variables y Procesamiento de la Informaci贸n en Bash

Esta secci贸n se centra en las **variables en Bash**, la **manipulaci贸n de texto**, y la **automatizaci贸n del tratamiento de la informaci贸n** usando herramientas poderosas como `awk`, `sed`, `cut`, y m谩s.

---

## 馃搶 Variables en Bash

### 馃搷 Declarar y usar variables
```bash
nombre="Alex"
echo $nombre
```

### 馃枿锔?Guardar output en variables
```bash
fecha=$(date)
echo "Hoy es: $fecha"
```

### 鈱笍 Entrada de datos con `read`
```bash
read -p "Introduce tu nombre: " nombre
echo "Hola, $nombre"
```

---

## 馃М Par谩metros y Variables especiales

| Variable | Descripci贸n |
|----------|-------------|
| `$0`     | Nombre del script |
| `$1`, `$2`, ... | Argumentos pasados |
| `$#`     | N煤mero de argumentos |
| `$@`     | Todos los argumentos como lista |
| `$?`     | C贸digo de salida del 煤ltimo comando |

```bash
echo "Se han pasado $# argumentos"
```

---

## 馃洜锔?Procesadores de informaci贸n

### 馃敜 `tr` 鈥?Sustituir caracteres
```bash
echo "linux" | tr a-z A-Z
```

### 馃М `awk` 鈥?Potente procesador de texto por columnas
```bash
awk '{print $1, $3}' archivo.txt
```

### 鉁傦笍 `cut` 鈥?Extraer columnas o campos
```bash
cut -d':' -f1 /etc/passwd
```

### 鉁傦笍 `sed` 鈥?Reemplazo de patrones y edici贸n
```bash
sed 's/rojo/azul/g' archivo.txt
```

---

## 鈿欙笍 Automatizaci贸n con scripts

### 馃攣 Script para tratamiento de la informaci贸n
```bash
#!/bin/bash
for archivo in *.log; do
  grep "ERROR" "$archivo" >> errores.txt
done
```

### 馃攳 Script para b煤squedas automatizadas
```bash
#!/bin/bash
read -p "Palabra a buscar: " palabra
grep -r "$palabra" /var/log
```

---

## 馃И Ejercicios sugeridos

1. Crea una variable con tu nombre y mu茅strala en pantalla.
2. Crea un script que reciba un argumento y lo use como nombre de archivo.
3. Usa `awk` para mostrar solo el usuario y el shell por defecto de `/etc/passwd`.
4. Usa `sed` para reemplazar palabras en m煤ltiples archivos.
5. Automatiza un script que busque errores y guarde los resultados.

---

El dominio de estas herramientas te permitir谩 escribir scripts potentes para procesar datos, auditar logs y automatizar tareas del sistema. 隆Practica y prueba sin miedo!
