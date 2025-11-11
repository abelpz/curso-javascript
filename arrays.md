# Arrays

## Qué son los arrays

Los arrays son listas ordenadas que nos permiten almacenar múltiples valores en una sola variable. Piensa en un array como una caja dividida en compartimentos numerados, donde cada compartimento puede guardar un valor.

Ya viste arrays brevemente en la lección de tipos de datos. Ahora aprenderás cómo trabajar con ellos en profundidad.

Mira estos ejemplos de arrays:

```js
const numeros = [1, 2, 3, 4, 5];
const frutas = ["manzana", "pera", "naranja"];
const valores = [10, "texto", true, 3.14];
```

> ¿Qué tienen en común estos tres arrays?
>
> Todos usan corchetes `[]` y separan sus elementos con comas.

---

## Creando arrays

Para crear un array, usas corchetes `[]` y separas los elementos con comas:

```js
const colores = ["rojo", "verde", "azul"];
```

Puedes crear arrays vacíos:

```js
const vacio = [];
```

Puedes crear arrays con diferentes tipos de datos:

```js
const mixto = [42, "JavaScript", true, 3.14];
```

> ¿Recuerdas esto?
>
> En la lección de tipos de datos aprendiste que los arrays pueden contener cualquier tipo de dato, incluso mezclados.

---

## Índices en arrays

Cada elemento en un array tiene una **posición** llamada **índice**. Los índices comienzan en **0**, no en 1.

```js
const dias = ["lunes", "martes", "miércoles", "jueves", "viernes"];
```

En este array:
- `"lunes"` está en el índice 0
- `"martes"` está en el índice 1
- `"miércoles"` está en el índice 2
- `"jueves"` está en el índice 3
- `"viernes"` está en el índice 4

> ¿Por qué empiezan en 0?
>
> Es una convención en programación. El primer elemento siempre está en la posición 0.

---

## Accediendo a elementos

**Acceder** significa obtener o buscar el valor que está guardado en una posición específica del array para poder usarlo en nuestro programa.

Para acceder a un elemento del array, usas el nombre del array seguido de corchetes con el índice:

```js
const frutas = ["manzana", "pera", "naranja", "plátano"];

const primera = frutas[0];
// primera es "manzana"

const segunda = frutas[1];
// segunda es "pera"

const tercera = frutas[2];
// tercera es "naranja"
```

> ¿Qué valor tiene frutas[3]?
>
> Es "plátano", porque es el cuarto elemento (índice 3).

Puedes usar variables como índices:

```js
const numeros = [10, 20, 30, 40, 50];
const indice = 2;

const valor = numeros[indice];
// valor es 30
```

Si intentas acceder a un índice que no existe:

```js
const colores = ["rojo", "verde"];

const tercero = colores[2];
// tercero es undefined
```

---

## La propiedad length

Todo array tiene una propiedad `length` que te dice cuántos elementos contiene:

```js
const frutas = ["manzana", "pera", "naranja"];
const cantidad = frutas.length;
// cantidad es 3
```

```js
const numeros = [5, 10, 15, 20, 25, 30];
const total = numeros.length;
// total es 6
```

```js
const vacio = [];
const cuantos = vacio.length;
// cuantos es 0
```

> ¿Para qué sirve length?
>
> Es muy útil para saber cuántos elementos hay, para recorrer el array, o para acceder al último elemento.

### Accediendo al último elemento

Puedes usar `length` para obtener el último elemento:

```js
const dias = ["lunes", "martes", "miércoles", "jueves", "viernes"];
const ultimo = dias[dias.length - 1];
// ultimo es "viernes"
```

> ¿Por qué restamos 1?
>
> Porque si el array tiene 5 elementos, el último está en el índice 4 (length - 1).

---

## Modificando elementos

Puedes cambiar el valor de un elemento accediendo a su índice:

```js
const colores = ["rojo", "verde", "azul"];

colores[1] = "amarillo";
// Ahora colores es ["rojo", "amarillo", "azul"]
```

```js
const numeros = [10, 20, 30];

numeros[0] = 100;
numeros[2] = 300;
// Ahora numeros es [100, 20, 300]
```

> ¿Puedes modificar un array const?
>
> Sí, puedes modificar los elementos dentro del array. Lo que no puedes es reasignar el array completo.

```js
const frutas = ["manzana", "pera"];

frutas[0] = "naranja"; // ✓ Esto funciona
// frutas es ["naranja", "pera"]

frutas = ["uva", "kiwi"]; // ✗ Esto da error
```

---

## Arrays con diferentes tipos de datos

Los arrays pueden contener cualquier tipo de dato: strings, números, booleanos, otros arrays, objetos, etc.

### Arrays de strings:

```js
const nombres = ["Ana", "Carlos", "María", "Pedro"];
const ciudades = ["Madrid", "Barcelona", "Valencia"];
```

### Arrays de números:

```js
const edades = [25, 30, 18, 42];
const precios = [19.99, 29.99, 9.99];
```

### Arrays de booleanos:

```js
const respuestas = [true, false, true, true, false];
const activos = [true, true, false];
```

### Arrays mixtos:

```js
const datos = ["Ana", 25, true, 3.14];
const info = [42, "JavaScript", false, "desarrollo"];
```

> ¿Es buena práctica mezclar tipos?
>
> Técnicamente es posible, pero generalmente es mejor que un array contenga elementos del mismo tipo para mayor claridad.

---

## Arrays dentro de arrays

Puedes tener arrays dentro de otros arrays. Esto se llama **array multidimensional** o **array anidado**.

```js
const matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
```

> Vuelve a ver el codigo de arriba.
> ¿Cuántos elementos tiene el array asignado a la variable matriz?
> R: 3 elementos. Cada elemento es un array.

Para acceder a elementos en arrays anidados, usas múltiples corchetes:

```js
const numeros = [
  [10, 20],
  [30, 40],
  [50, 60]
];

const primero = numeros[0];
// primero es [10, 20]

const elemento = numeros[0][1];
// elemento es 20

const otro = numeros[2][0];
// otro es 50

const anidado = primero[0];
// anidado es 10
```

> ¿Entiendes cómo funciona?
>
> `numeros[0]` accede al primer array `[10, 20]`, y luego `[1]` accede al segundo elemento de ese array.
>
> primero es [10, 20] y anidado es 10.

Otro ejemplo:

```js
const datos = [
  ["Ana", "María", "Carlos"],
  [25, 30, 28],
  [true, true, false]
];

const nombre = datos[0][1];
// nombre es "María"

const edad = datos[1][2];
// edad es 28

const activo = datos[2][0];
// activo es true
```

---

## Arrays y objetos

Puedes combinar arrays y objetos de diferentes formas.

### Array de objetos:

```js
const personas = [
  { nombre: "Ana", edad: 25 },
  { nombre: "Carlos", edad: 30 },
  { nombre: "María", edad: 28 }
];

const primerPersona = personas[0];
// primerPersona es { nombre: "Ana", edad: 25 }

const nombre = personas[1].nombre;
// nombre es "Carlos"

const edad = personas[2].edad;
// edad es 28
```

> ¿Ves cómo se combinan?
>
> Primero usas corchetes para acceder al array, luego punto para acceder a las propiedades del objeto.

### Objeto con arrays:

```js
const estudiante = {
  nombre: "Pedro",
  calificaciones: [8, 9, 7, 10],
  materias: ["Matemáticas", "Historia", "Ciencias"]
};

const primeraCalificacion = estudiante.calificaciones[0];
// primeraCalificacion es 8

const segundaMateria = estudiante.materias[1];
// segundaMateria es "Historia"
```

---

## Copiando arrays

Si intentas copiar un array con el operador `=`, no obtienes una copia independiente:

```js
const original = [1, 2, 3];
const copia = original;

copia[0] = 100;

// Ahora original también cambió
// original es [100, 2, 3]
// copia es [100, 2, 3]
```

> ¿Por qué pasa esto?
>
> Porque `copia` y `original` son como dos nombres diferentes para el mismo array. Es como si dos personas tuvieran la llave de la misma caja: cuando una persona cambia algo dentro de la caja, la otra persona también verá ese cambio porque es la misma caja.

Para crear una copia independiente, puedes usar diferentes técnicas (que veremos más adelante con métodos de arrays). Por ahora, solo necesitas saber que esto puede pasar.

---

## Comparando arrays

Dos arrays no son iguales aunque tengan los mismos elementos:

```js
const array1 = [1, 2, 3];
const array2 = [1, 2, 3];

const sonIguales = array1 === array2;
// sonIguales es false
```

> ¿Por qué son diferentes?
>
> Porque aunque los dos arrays contengan los mismos valores, son dos arrays separados. Es como tener dos cajas diferentes que contienen las mismas cosas: las cajas siguen siendo diferentes aunque tengan el mismo contenido dentro.

---

## Trabajando con índices en condicionales

Puedes usar arrays dentro de condicionales:

```js
const calificaciones = [7, 8, 9, 6];
const primera = calificaciones[0];
let mensaje;

if (primera >= 8) {
  mensaje = "Excelente primera calificación";
} else if (primera >= 6) {
  mensaje = "Buena primera calificación";
} else {
  mensaje = "Necesitas mejorar";
}
// mensaje es "Buena primera calificación"
```

Verificando el tamaño del array:

```js
const frutas = ["manzana", "pera"];
let mensaje;

if (frutas.length === 0) {
  mensaje = "El array está vacío";
} else if (frutas.length < 3) {
  mensaje = "Pocas frutas";
} else {
  mensaje = "Muchas frutas";
}
// mensaje es "Pocas frutas"
```

---

## Ejemplos prácticos

### Ejemplo 1: Lista de tareas

```js
const tareas = [
  "Estudiar JavaScript",
  "Hacer ejercicios",
  "Leer documentación"
];

const totalTareas = tareas.length;
// totalTareas es 3

const primeraTarea = tareas[0];
// primeraTarea es "Estudiar JavaScript"

const ultimaTarea = tareas[tareas.length - 1];
// ultimaTarea es "Leer documentación"
```

### Ejemplo 2: Registro de temperaturas

```js
const temperaturas = [22, 25, 23, 24, 26, 21, 23];

const lunes = temperaturas[0];
// lunes es 22

const viernes = temperaturas[4];
// viernes es 26

const diasRegistrados = temperaturas.length;
// diasRegistrados es 7
```

### Ejemplo 3: Productos en una tienda

```js
const productos = [
  { nombre: "Laptop", precio: 1000 },
  { nombre: "Mouse", precio: 25 },
  { nombre: "Teclado", precio: 50 }
];

const primerProducto = productos[0].nombre;
// primerProducto es "Laptop"

const precioSegundo = productos[1].precio;
// precioSegundo es 25

const cantidadProductos = productos.length;
// cantidadProductos es 3
```

### Ejemplo 4: Matriz de calificaciones

```js
const calificaciones = [
  [8, 9, 7],   // Estudiante 1
  [6, 8, 9],   // Estudiante 2
  [10, 9, 8]   // Estudiante 3
];

const primeraCalifEstudiante1 = calificaciones[0][0];
// primeraCalifEstudiante1 es 8

const terceraCalifEstudiante2 = calificaciones[1][2];
// terceraCalifEstudiante2 es 9

const cantidadEstudiantes = calificaciones.length;
// cantidadEstudiantes es 3
```

---

## Resumen

- Los arrays son listas ordenadas de valores
- Se crean con corchetes `[]`
- Los índices empiezan en 0
- Usas `array[indice]` para acceder a elementos
- `array.length` te dice cuántos elementos hay
- Puedes modificar elementos: `array[indice] = nuevoValor`
- Los arrays pueden contener cualquier tipo de dato
- Puedes tener arrays dentro de arrays (multidimensionales)

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
const numeros = [5, 10, 15, 20, 25];
const tercero = numeros[2];
// valor de tercero
```

#### b)

```js
const frutas = ["manzana", "pera", "naranja"];
const cuantas = frutas.length;
// valor de cuantas
```

#### c)

```js
const valores = [100, 200, 300, 400];
const ultimo = valores[valores.length - 1];
// valor de ultimo
```

#### d)

```js
const datos = [
  [1, 2],
  [3, 4],
  [5, 6]
];
const elemento = datos[1][1];
// valor de elemento
```

#### e)

```js
const colores = ["rojo", "verde", "azul"];
colores[1] = "amarillo";
const segundo = colores[1];
// valor de segundo
```

### 2. Encuentra los errores

Identifica y corrige los errores en estos ejemplos:

#### a)

```js
const numeros = [1, 2, 3, 4, 5;
const primero = numeros[0];
```

#### b)

```js
const frutas = ["manzana", "pera", "naranja"];
const segunda = frutas.1;
```

#### c)

```js
const = [10, 20, 30];
const valor = datos[0];
```

#### d)

```js
const colores = ["rojo", "verde", "azul"];
const primero = colores(0);
```

### 3. Accede a los elementos

Para estos arrays, obtén los valores indicados:

#### a)

```js
const dias = ["lunes", "martes", "miércoles", "jueves", "viernes", "sábado", "domingo"];
// Obtén el primer día de la semana
// Obtén el último día de la semana
// Obtén "miércoles"
```

#### b)

```js
const edades = [18, 25, 30, 22, 35, 28];
// Obtén la primera edad
// Obtén la cuarta edad
// Obtén cuántas edades hay en total
```

#### c)

```js
const matriz = [
  [10, 20, 30],
  [40, 50, 60],
  [70, 80, 90]
];
// Obtén el número 50
// Obtén el número 90
// Obtén el número 10
```

### 4. Modifica arrays

#### a)

Crea un array con 5 números. Luego cambia el primero y el último elemento por otros valores.

#### b)

Crea un array con los nombres de 4 colores. Cambia el segundo color por uno diferente.

#### c)

Crea un array con 3 booleanos. Invierte el valor del segundo elemento (si era true, ponlo false, y viceversa).

### 5. Crea estructuras

Para estos ejercicios, utiliza tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea un array llamado `mesesDelAño` que contenga los nombres de los 12 meses. Luego crea variables que obtengan:
- El primer mes del año
- Tu mes favorito (usando su índice)
- El último mes del año
- La cantidad total de meses

#### b)

Crea un array de objetos llamado `libros` que contenga 3 libros. Cada libro debe tener las propiedades: título, autor y páginas. Luego obtén:
- El título del primer libro
- El autor del segundo libro
- La cantidad de páginas del tercer libro

#### c)

Crea un array bidimensional llamado `tablero` que represente un tablero de 3x3 (como el tres en raya). Puede contener números, strings o lo que prefieras. Luego accede a diferentes posiciones del tablero.

#### d)

Crea un objeto llamado `estudiante` que tenga las propiedades:
- nombre (string)
- edad (número)
- calificaciones (array de números)
- materias (array de strings)

Luego accede a elementos específicos de los arrays dentro del objeto.

#### e)

Crea un array llamado `inventario` que contenga 5 productos. Cada producto debe ser un objeto con: nombre, precio, y cantidad. Usa condicionales para:
- Verificar si el primer producto tiene stock (cantidad > 0)
- Verificar si el precio del tercer producto es mayor a 100
- Determinar cuántos productos hay en el inventario

