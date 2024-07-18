# Manual de Ayuda - Funciones de la Librería JavaScript

## Índice

1. [Función `dameMesLetra`](#función-damemesletra)
2. [Función `dameConApostrofe`](#función-dameconapostrofe)
3. [Función `utf8Encode`](#función-utf8encode)
4. [Función `utf8Decode`](#función-utf8decode)
5. [Función `convertirDataTable`](#función-convertirdatatable)
6. [Función `validarHora`](#función-validarhora)
7. [Función `dameMinutos`](#función-dameminutos)
8. [Función `decodificaHora`](#función-decodificahora)
9. [Función `obtenerHorarios`](#función-obtenerhorarios)
10. [Función `validarCruce`](#función-validarcruce)
11. [Función `getEspacio`](#función-getespacio)
12. [Función `validaCruceHorario`](#función-validacrucehorario)
13. [Función `Burbuja`](#función-burbuja)
14. [Función `BurbujaCadena`](#función-burbujacadena)
15. [Función `dameVentana`](#función-dameventana)
16. [Función `escribeMoneda`](#función-escribemoneda)
17. [Función `escribeEnteros`](#función-escribeenteros)
18. [Función `dameVentanaTabla`](#función-dameventanatabla)
19. [Función `cargaRegistrosGen`](#función-cargaregistrosgen)
20. [Función `eliminaRegistroGen`](#función-eliminaregistrogen)


## Función `dameMesLetra`

### Descripción
Retorna el nombre del mes en letras mayúsculas según el número del mes proporcionado.

### Parámetros
- `nummes` (número): El número del mes (1 para enero, 2 para febrero, etc.).

### Retorno
- `string`: El nombre del mes en letras mayúsculas.

### Ejemplo de Uso
```javascript
var mes = dameMesLetra(5);
console.log(mes);  // Salida: "MAYO"
```

## Función `dameConApostrofe`

### Descripción
Envuelve cada elemento de una cadena separada por comas con comillas simples.

### Parámetros
- `cadena` (string): La cadena con elementos separados por comas.

### Retorno
- `string`: La cadena con cada elemento envuelto en comillas simples.

### Ejemplo de Uso
```javascript
var resultado = dameConApostrofe("manzana,pera,platano");
console.log(resultado);  // Salida: "'manzana','pera','platano'"
```

## Función `utf8Encode`

### Descripción
Codifica una cadena Unicode en UTF-8.

### Parámetros
- `unicodeString` (string): La cadena Unicode a codificar.

### Retorno
- `string`: La cadena codificada en UTF-8.

### Ejemplo de Uso
```javascript
var utf8String = utf8Encode("Hola, ¿cómo estás?");
console.log(utf8String);  // Salida: cadena UTF-8
```

## Función `utf8Decode`

### Descripción
Decodifica una cadena UTF-8 a Unicode.

### Parámetros
- `utf8String` (string): La cadena UTF-8 a decodificar.

### Retorno
- `string`: La cadena decodificada en Unicode.

### Ejemplo de Uso
```javascript
var unicodeString = utf8Decode(utf8String);
console.log(unicodeString);  // Salida: "Hola, ¿cómo estás?"
```

## Función `convertirDataTable`

### Descripción
Convierte una tabla HTML en un DataTable de jQuery y añade funcionalidades adicionales como búsqueda y exportación.

### Parámetros
- `latabla` (string): El ID de la tabla HTML a convertir.

### Ejemplo de Uso
```javascript
// Supongamos que tienes una tabla con el ID "miTabla"
convertirDataTable("miTabla");
```

## Función `validarHora`

### Descripción
Valida si una hora dada en formato HH:MM es correcta.

### Parámetros
- `hora` (string): La hora en formato HH:MM.

### Retorno
- `string`: Mensaje de error si la hora es incorrecta, vacío si es correcta.

### Ejemplo de Uso
```javascript
var mensaje = validarHora("25:30");
console.log(mensaje);  // Salida: "La hora debe estar entre 01 y 23\nLos minutos deben estar entre 01 y 59\n"
```

## Función `dameMinutos`

### Descripción
Convierte una hora en formato HH:MM a minutos.

### Parámetros
- `hora` (string): La hora en formato HH:MM.

### Retorno
- `number`: El total de minutos.

### Ejemplo de Uso
```javascript
var minutos = dameMinutos("02:30");
console.log(minutos);  // Salida: 150
```

## Función `decodificaHora`

### Descripción
Decodifica una cadena de horario en formato HH:MM-HH:MM y retorna los componentes de la hora inicial y final.

### Parámetros
- `horario` (string): La cadena de horario en formato HH:MM-HH:MM.

### Retorno
- `array`: Un arreglo con los componentes de la hora inicial y final.

### Ejemplo de Uso
```javascript
var datos = decodificaHora("08:00-12:00");
console.log(datos);  // Salida: ["08", "00", "12", "00", 480, 720]
```

## Función `obtenerHorarios`

### Descripción
Obtiene los horarios y valida posibles conflictos en la base de datos.

### Parámetros
- `id` (number): El ID del detalle.
- `elciclo` (string): El ciclo académico.
- `linea` (string): La línea de datos.

### Retorno
- `boolean`: Retorna `false` si hay conflictos, de lo contrario `true`.

### Ejemplo de Uso
```javascript
var resultado = obtenerHorarios(1, "2023A", "linea1");
console.log(resultado);  // Salida: true o false dependiendo de los conflictos
```

## Función `validarCruce`

### Descripción
Valida si un horario específico se cruza con otros horarios en un arreglo dado.

### Parámetros
- `arreglo` (array): Arreglo de horarios en formato "HHMM|HHMM".
- `horariodia` (string): Horario en formato HH:MM-HH:MM a validar.

### Retorno
- `boolean`: Retorna `true` si no hay cruce, `false` si hay cruce.

### Ejemplo de Uso
```javascript
var horarios = ["0800|1000", "1100|1300"];
var resultado = validarCruce(horarios, "0900-1100");
console.log(resultado);  // Salida: false
```

## Función `getEspacio`

### Descripción
Obtiene el espacio disponible entre los horarios en un arreglo dado.

### Parámetros
- `arreglo` (array): Arreglo de horarios en formato "HHMM|HHMM".
- `horariodia` (string): Horario en formato HH:MM-HH:MM para buscar el espacio.

### Retorno
- `string`: El espacio disponible.

### Ejemplo de Uso
```javascript
var horarios = ["0800|1000|Espacio1", "1100|1300|Espacio2"];
var espacio = getEspacio(horarios, "0900-1100");
console.log(espacio);  // Salida: "Espacio1"
```

## Función `validaCruceHorario`

### Descripción
Valida si hay un cruce de horarios específico en un conjunto de horarios.

### Parámetros
- `tipo` (string): Tipo de elemento a validar (ej. "PROFESOR", "AULA").
- `indiceComparar` (number): Índice del arreglo de horarios a comparar.
- `valorComparar` (string): Valor a comparar en los horarios.
- `valorComparard` (string): Descripción del valor a comparar.
- `loshorarios` (array): Arreglo de horarios.
- `indiceDia` (number): Índice del día en los horarios.
- `horariodia` (string): Horario en formato HH:MM-HH:MM a validar.
- `linea` (string): Línea de datos.

### Retorno
- `string`: Mensaje de error si hay un cruce, vacío si no hay cruce.

### Ejemplo de Uso
```javascript
var horarios = [{"PROFESOR": "123", "LUNES_1": "0800-1000"}, {"PROFESOR": "123", "LUNES_1": "1100-1300"}];
var mensaje = validaCruce

Horario("PROFESOR", 0, "123", "Profesor 123", horarios, 1, "0900-1100", "linea1");
console.log(mensaje);  // Salida: "Error: PROFESOR Profesor 123 No disponible en el horario 0900-1100"
```

## Función `Burbuja`

### Descripción
Ordena un arreglo de horarios en formato "HHMM|HHMM" utilizando el algoritmo de burbuja.

### Parámetros
- `lista` (array): Arreglo de horarios a ordenar.

### Retorno
- `array`: Arreglo ordenado.

### Ejemplo de Uso
```javascript
var horarios = ["1100|1300", "0800|1000"];
var ordenados = Burbuja(horarios);
console.log(ordenados);  // Salida: ["0800|1000", "1100|1300"]
```

## Función `BurbujaCadena`

### Descripción
Ordena un arreglo de cadenas en formato "HHMM|HHMM" utilizando el algoritmo de burbuja.

### Parámetros
- `lista` (array): Arreglo de cadenas a ordenar.

### Retorno
- `array`: Arreglo ordenado.

### Ejemplo de Uso
```javascript
var cadenas = ["b|2", "a|1"];
var ordenadas = BurbujaCadena(cadenas);
console.log(ordenadas);  // Salida: ["a|1", "b|2"]
```

## Función `dameVentana`

### Descripción
Crea una ventana modal de Bootstrap con los parámetros especificados.

### Parámetros
- `nombre` (string): Nombre de la ventana.
- `contenedor` (string): ID del contenedor donde se añadirá la ventana.
- `titulo` (string): Título de la ventana.
- `tam` (string): Tamaño de la ventana (ej. "lg" para large).
- `colorfondohead` (string): Clase CSS para el color de fondo del encabezado.
- `imaico` (string): Clase CSS para el ícono del encabezado.
- `alto` (number): Altura de la ventana en píxeles.

### Ejemplo de Uso
```javascript
dameVentana("miVentana", "contenedorPrincipal", "Título de la Ventana", "lg", "bg-primary", "fa fa-info-circle", 500);
```

## Función `escribeMoneda`

### Descripción
Formatea el valor de un campo de entrada para que tenga separadores de miles.

### Parámetros
- `input` (object): Objeto del campo de entrada.

### Ejemplo de Uso
```javascript
// Supongamos que tienes un campo de entrada con el ID "monto"
document.getElementById("monto").addEventListener("input", function() {
    escribeMoneda(this);
});
```

## Función `escribeEnteros`

### Descripción
Permite solo la entrada de números enteros en un campo de entrada.

### Parámetros
- `event` (object): Objeto del evento de entrada.

### Ejemplo de Uso
```javascript
// Supongamos que tienes un campo de entrada con el ID "numeroEntero"
document.getElementById("numeroEntero").addEventListener("keypress", function(event) {
    escribeEnteros(event);
});
```

## Función `dameVentanaTabla`

### Descripción
Crea una ventana modal de Bootstrap con una tabla generada dinámicamente a partir de una consulta SQL.

### Parámetros
- `nombre` (string): Nombre de la ventana.
- `contenedor` (string): ID del contenedor donde se añadirá la ventana.
- `titulo` (string): Título de la ventana.
- `tam` (string): Tamaño de la ventana (ej. "lg" para large).
- `colorfondohead` (string): Clase CSS para el color de fondo del encabezado.
- `imaico` (string): Clase CSS para el ícono del encabezado.
- `alto` (number): Altura de la ventana en píxeles.
- `columnas` (array): Arreglo de nombres de las columnas.
- `sqlOrigen` (string): Cadena SQL para obtener los datos.
- `valorpadre` (string): Valor del campo padre.
- `condicion` (string): Condición para la consulta SQL.

### Ejemplo de Uso
```javascript
var columnas = ["ID", "Nombre", "Edad"];
dameVentanaTabla("miTabla", "contenedorPrincipal", "Título de la Tabla", "lg", "bg-primary", "fa fa-table", 500, columnas, "SELECT * FROM usuarios", "", "");
```

## Función `cargaRegistrosGen`

### Descripción
Carga registros en una tabla dinámica dentro de una ventana modal de Bootstrap.

### Parámetros
- `nombre` (string): Nombre de la ventana.
- `sqlOrigen` (string): Cadena SQL para obtener los datos.
- `valorpadre` (string): Valor del campo padre.
- `contenedor` (string): ID del contenedor donde se añadirá la tabla.
- `condicion` (string): Condición para la consulta SQL.

### Ejemplo de Uso
```javascript
cargaRegistrosGen("miTabla", "SELECT * FROM usuarios", "", "contenedorPrincipal", "");
```

## Función `eliminaRegistroGen`

### Descripción
Elimina un registro de una tabla dinámica y actualiza la tabla.

### Parámetros
- `nombre` (string): Nombre de la ventana.
- `sqlOrigen` (string): Cadena SQL para obtener los datos.
- `elid` (string): ID del registro a eliminar.
- `valorpadre` (string): Valor del campo padre.
- `contenedor` (string): ID del contenedor donde se añadirá la tabla.
- `condicion` (string): Condición para la consulta SQL.

### Ejemplo de Uso
```javascript
eliminaRegistroGen("miTabla", "SELECT * FROM usuarios", "1", "", "contenedorPrincipal", "");
```
```

