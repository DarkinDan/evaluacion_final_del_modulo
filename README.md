# Sistema de Gestión de una Tienda de Videojuegos

Este proyecto corresponde al ejercicio integrador del Módulo 3 de Python. El programa permite administrar el inventario y las ventas de una tienda de videojuegos desde la consola.

## Objetivo

Crear un sistema sencillo en Python que use:

- Variables.
- Condicionales `if`, `elif`, `else`.
- Ciclos `while` y `for`.
- Funciones.
- Diccionarios y listas.
- Validación de datos.
- Cálculos estadísticos básicos.

## Estructura de los datos

La información de los videojuegos se guarda en un diccionario llamado `videojuegos`.

Cada código de videojuego funciona como clave principal del diccionario. El valor asociado a cada código es otro diccionario con la información del juego.

Ejemplo:

```python
videojuegos = {
    "VG001": {
        "nombre": "FIFA 26",
        "plataforma": "PlayStation 5",
        "precio": 250000,
        "cantidad": 10
    }
}
```

## Datos iniciales

El programa inicia con tres videojuegos de prueba:

| Código | Nombre | Plataforma | Precio | Cantidad |
|---|---|---|---:|---:|
| VG001 | FIFA 26 | PlayStation 5 | 250000 | 10 |
| VG002 | Zelda: Breath of the Wild | Nintendo Switch | 220000 | 5 |
| VG003 | Forza Horizon 5 | Xbox Series X | 210000 | 8 |

## Menú principal

Al ejecutar el programa se muestra el siguiente menú:

```text
===== TIENDA DE VIDEOJUEGOS =====
1. Agregar videojuego
2. Mostrar inventario
3. Buscar videojuego por codigo
4. Actualizar precio
5. Registrar venta
6. Mostrar estadisticas
7. Eliminar videojuego
8. Salir
```

El menú se repite hasta que el usuario seleccione la opción `8`.

## Funciones implementadas

### `agregar_videojuego(videojuegos)`

Solicita los datos de un nuevo videojuego y lo agrega al diccionario.

Validaciones:

- El código no puede estar repetido.
- El nombre no puede estar vacío.
- La plataforma debe seleccionarse desde una lista de opciones válidas.
- El precio debe ser mayor que cero.
- La cantidad debe ser mayor que cero.

### `mostrar_inventario(videojuegos)`

Recorre el diccionario e imprime todos los videojuegos registrados con su código, nombre, plataforma, precio y cantidad disponible.

Si no hay videojuegos registrados, muestra un mensaje informativo.

### `buscar_videojuego(videojuegos)`

Solicita el código de un videojuego y muestra su información si existe.

Si el código no existe, muestra un mensaje de error.

### `actualizar_precio(videojuegos)`

Solicita el código del videojuego y permite cambiar su precio.

Validaciones:

- El videojuego debe existir.
- El nuevo precio debe ser mayor que cero.

### `registrar_venta(videojuegos)`

Permite registrar la venta de un videojuego.

Solicita:

- Código del videojuego.
- Cantidad a vender.

Validaciones:

- El videojuego debe existir.
- La cantidad a vender debe ser mayor que cero.
- Debe existir suficiente inventario.

Acciones:

- Resta la cantidad vendida del inventario.
- Calcula el total de la venta.
- Imprime una factura sencilla.

Ejemplo de factura:

```text
Factura:
Juego: FIFA 26
Precio unitario: $250.000
Cantidad: 2
Total: $500.000
```

### `mostrar_estadisticas(videojuegos)`

Muestra estadísticas generales del inventario:

- Total de videojuegos registrados.
- Valor total del inventario.
- Videojuego más costoso.
- Videojuego con mayor cantidad disponible.
- Promedio de precios.

### `eliminar_videojuego(videojuegos)`

Solicita el código de un videojuego y lo elimina del inventario si existe.

### `menu()`

Controla la ejecución principal del programa. Muestra el menú, recibe la opción del usuario y llama a la función correspondiente.

## Funciones auxiliares

El programa también incluye algunas funciones auxiliares para evitar repetir código:

### `formatear_precio(valor)`

Convierte un número en formato de precio con el símbolo `$`.

Ejemplo:

```text
250000 -> $250.000
```

### `pedir_texto(mensaje)`

Solicita texto al usuario y valida que no esté vacío.

### `pedir_numero_entero(mensaje)`

Solicita un número entero y valida que sea mayor que cero.

### `pedir_plataforma()`

Muestra una lista de plataformas válidas y retorna la opción seleccionada por el usuario.

## Cómo ejecutar el programa

1. Guarda el archivo `TALLER_MODULO3.PY` en una carpeta de tu computador.
2. Abre una terminal en esa carpeta.
3. Ejecuta el programa con:

```bash
python TALLER_MODULO3.PY
```

También puedes usar:

```bash
py TALLER_MODULO3.PY
```

si estás trabajando en Windows.

## Ejemplo de uso

### Registrar una venta

Entrada del usuario:

```text
Ingrese codigo del videojuego: VG001
Ingrese cantidad a vender: 2
```

Salida del programa:

```text
Factura:
Juego: FIFA 26
Precio unitario: $250.000
Cantidad: 2
Total: $500.000
Venta registrada correctamente.
```

Después de esta venta, la cantidad disponible de `VG001` pasa de `10` a `8`.

## Notas importantes

- El programa no guarda la información en archivos externos ni en base de datos.
- Los cambios realizados durante la ejecución solo existen mientras el programa está abierto.
- Al cerrar y volver a ejecutar el programa, el inventario vuelve a los datos iniciales.
- El código fue mantenido simple para practicar fundamentos de Python sin agregar complejidad innecesaria.

## Conceptos practicados

- Diccionarios anidados.
- Listas.
- Funciones con parámetros.
- Validaciones con ciclos `while`.
- Recorridos con ciclos `for`.
- Condicionales.
- Cálculos con inventario y precios.
