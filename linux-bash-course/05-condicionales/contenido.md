
# 🔁 Condicionales en Bash

En esta sección aprenderás a controlar el flujo de tus scripts usando condicionales: `if`, `else`, `elif` y estructuras como `case`. También verás operadores lógicos y cómo tomar decisiones dinámicas en Bash.

---

## 🧠 Sentencias Condicionales - IF, ELIF y ELSE

Estructura básica de una condición:
```bash
if [ condición ]; then
   # código si se cumple
elif [ otra_condición ]; then
   # otro bloque
else
   # si no se cumple ninguna
fi
```

Ejemplo:
```bash
numero=5

if [ $numero -gt 10 ]; then
    echo "Es mayor que 10"
elif [ $numero -eq 10 ]; then
    echo "Es igual a 10"
else
    echo "Es menor que 10"
fi
```

---

## 🔗 Operadores Lógicos

| Operador | Significado       |
|----------|-------------------|
| `-eq`    | Igual             |
| `-ne`    | Distinto          |
| `-gt`    | Mayor que         |
| `-lt`    | Menor que         |
| `-ge`    | Mayor o igual     |
| `-le`    | Menor o igual     |
| `&&`     | Y lógico (AND)    |
| `||`     | O lógico (OR)     |

---

## 🛠️ Script de ejemplo: Automatizar actualizaciones

```bash
#!/bin/bash

echo "¿Deseas actualizar el sistema? (s/n)"
read respuesta

if [[ "$respuesta" == "s" ]]; then
    sudo apt update && sudo apt upgrade -y
    echo "Sistema actualizado correctamente."
else
    echo "Actualización cancelada."
fi
```

---

## 🔄 Control del Flujo - CASE

Alternativa a `if` cuando se evalúan múltiples opciones.

```bash
read -p "Elige una opción (a/b/c): " opcion

case $opcion in
    a) echo "Elegiste A";;
    b) echo "Elegiste B";;
    c) echo "Elegiste C";;
    *) echo "Opción inválida";;
esac
```

---

## 🧪 Ejercicios prácticos

1. Escribe un script que determine si un número es par o impar.
2. Crea un menú con opciones usando `case`.
3. Crea un script que reciba un parámetro y valide si existe un archivo.
4. Automatiza tareas diarias con confirmación (`if`).
5. Compara dos strings y muestra si son iguales.

---

El uso de condicionales en Bash permite crear scripts inteligentes y dinámicos. Practica estos ejemplos y empieza a tomar decisiones en tus automatizaciones.
