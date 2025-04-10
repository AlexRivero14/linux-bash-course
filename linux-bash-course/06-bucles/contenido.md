
# 🔁 Bucles en Bash

Los bucles son fundamentales para automatizar tareas repetitivas en Bash. En esta sección exploramos los bucles `for` y `while`, sus variantes y ejemplos prácticos que puedes aplicar de inmediato.

---

## 🔄 Bucle FOR – Parte 1

El bucle `for` recorre una lista de elementos o un rango.

```bash
for i in 1 2 3 4 5; do
  echo "Número: $i"
done
```

---

## 🔁 Bucle FOR – Parte 2 (con secuencia)

```bash
for i in $(seq 1 5); do
  echo "Iteración $i"
done
```

---

## 🧪 Ejercicio práctico FOR – Medidor de archivos

Script para contar el número de archivos en varias carpetas:

```bash
#!/bin/bash
for dir in /etc /usr /var; do
  echo "$dir contiene $(ls $dir | wc -l) archivos"
done
```

---

## 🗃️ Ejercicio práctico FOR – Ordenar archivos automáticamente

```bash
#!/bin/bash
mkdir -p imagenes documentos scripts

for archivo in *; do
  if [[ $archivo == *.jpg || $archivo == *.png ]]; then
    mv "$archivo" imagenes/
  elif [[ $archivo == *.pdf || $archivo == *.docx ]]; then
    mv "$archivo" documentos/
  elif [[ $archivo == *.sh ]]; then
    mv "$archivo" scripts/
  fi
done
```

---

## 🔁 Bucle WHILE – Parte 1

Ejecuta mientras la condición sea verdadera:

```bash
contador=1
while [ $contador -le 5 ]; do
  echo "Contador: $contador"
  ((contador++))
done
```

---

## 🔄 Bucle WHILE – Parte 2

Combinado con lectura de entrada:

```bash
echo "Presiona ENTER para continuar (Ctrl+C para salir)"
while read; do
  echo "Continuando..."
done
```

---

## 📄 Bucle WHILE – Iterar por líneas

```bash
while read linea; do
  echo "Línea: $linea"
done < archivo.txt
```

---

## 🧠 Ejercicios sugeridos

1. Crea un bucle `for` que muestre los días de la semana.
2. Usa `while` para leer números hasta que se ingrese el 0.
3. Automatiza la organización de archivos por extensión.
4. Itera sobre una lista de usuarios y muestra su UID.
5. Crea un menú con `select` y combínalo con bucles.

---

Dominar los bucles en Bash te permitirá automatizar procesos de forma eficiente y manejar grandes volúmenes de tareas repetitivas. ¡Pruébalos y adáptalos a tus necesidades!
