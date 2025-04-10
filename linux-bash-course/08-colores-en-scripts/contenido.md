
# 🎨 Colores en Scripts Bash

Agregar colores a la salida de tus scripts no solo los hace más visuales, sino que también permite destacar errores, advertencias o mensajes importantes.

---

## 🖍️ Añadimos colores a nuestro script

Puedes usar secuencias ANSI para aplicar colores en la terminal.

```bash
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
NC='\033[0m' # No Color

echo -e "${GREEN}¡Todo ha salido correctamente!${NC}"
echo -e "${RED}Ha ocurrido un error.${NC}"
```

`echo -e` permite que se interpreten los caracteres especiales (`\033`).

---

## 📋 Listado de colores ANSI más comunes

| Color       | Código         |
|-------------|----------------|
| Negro       | `\033[0;30m`   |
| Rojo        | `\033[0;31m`   |
| Verde       | `\033[0;32m`   |
| Amarillo    | `\033[1;33m`   |
| Azul        | `\033[0;34m`   |
| Magenta     | `\033[0;35m`   |
| Cian        | `\033[0;36m`   |
| Blanco      | `\033[1;37m`   |
| Reset (NC)  | `\033[0m`      |

---

## 🧪 Ejercicio práctico

Crea un script que muestre los siguientes mensajes usando colores:

1. ✅ "Proceso finalizado correctamente" (Verde)
2. ⚠️ "Advertencia: espacio en disco bajo" (Amarillo)
3. ❌ "Error: archivo no encontrado" (Rojo)

---

## 💡 Consejo

Usa variables de color al inicio de tus scripts y aplica `${NC}` al final de cada línea coloreada para restablecer el color por defecto del terminal.

---

Colorear tus scripts hace que sean más amigables y fáciles de interpretar, especialmente cuando los compartes con otros usuarios o equipos.
