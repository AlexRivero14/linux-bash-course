
# 🔧 Funciones en Bash

Las funciones en Bash permiten **reutilizar bloques de código**, organizar scripts de forma más limpia y mantener un control sobre el flujo de ejecución. En esta sección aprenderás a declararlas, usarlas, y a distinguir entre variables locales y globales.

---

## 🧱 Declarar Funciones en Bash

Sintaxis general:
```bash
mi_funcion() {
  echo "Hola desde la función"
}
```

Llamada a la función:
```bash
mi_funcion
```

También puede declararse así (forma equivalente):
```bash
function mi_funcion {
  echo "Otra forma de declarar"
}
```

---

## 📥 Funciones con Parámetros

```bash
saludar() {
  echo "Hola, $1!"
}

saludar "Alex"
```

Puedes acceder a múltiples parámetros con `$1`, `$2`, `$@`, etc.

---

## 🧠 Variables Locales y Globales en Funciones

Por defecto, las variables son globales:

```bash
ejemplo() {
  nombre="Alex"
}
ejemplo
echo $nombre  # Se imprime Alex (global)
```

Para declarar variables **locales**, usa la palabra clave `local`:

```bash
ejemplo() {
  local nombre="Alex"
  echo "Dentro: $nombre"
}
ejemplo
echo "Fuera: $nombre"  # No existe fuera de la función
```

---

## ⚙️ Ejemplo completo

```bash
calcular_area() {
  local base=$1
  local altura=$2
  echo "Área: $((base * altura))"
}

calcular_area 5 3
```

---

## 🧪 Ejercicios prácticos

1. Crea una función que reciba un nombre y salude.
2. Crea una función que reciba dos números y devuelva su suma.
3. Usa variables locales y demuestra que no afectan al exterior.
4. Escribe un script con funciones para crear y borrar archivos.
5. Crea un menú donde cada opción llame a una función distinta.

---

Con funciones, tus scripts serán más profesionales, organizados y fáciles de mantener. ¡Practícalas y empieza a modular tu código!
