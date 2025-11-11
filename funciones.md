# Funciones

## El problema: repetir el mismo código

Imagina que necesitas calcular la edad de varias personas. Sabes en qué año nacieron y que el año actual es 2025. Para calcular la edad solo debes restar el año de nacimiento del año actual.

```js
const nacimientoJuan = 2010;
const edadJuan = 2025 - nacimientoJuan;
// edadJuan es 15

const nacimientoMaria = 2008;
const edadMaria = 2025 - nacimientoMaria;
// edadMaria es 17

const nacimientoPedro = 2012;
const edadPedro = 2025 - nacimientoPedro;
// edadPedro es 13
```

> ¿Ves el problema?
>
> Estamos escribiendo el mismo cálculo una y otra vez. Solo cambia el año de nacimiento.

Si tienes 100 personas, ¿escribirías esto 100 veces? ¡Eso sí que sería aburrido!

**La solución:** Las funciones te permiten escribir el código una vez y usarlo todas las veces que quieras.

---

## Qué es una función

Una **función** es como una receta de cocina. Escribes las instrucciones una vez, y luego puedes usar esa receta cuantas veces quieras.

O piensa en una función como una máquina:
- Le das algo (entrada)
- Hace su trabajo
- Te devuelve un resultado (salida)

Ahora podemos resolver el problema anterior con una función:

```js
function calcularEdad(anioNacimiento) {
  const edad = 2025 - anioNacimiento;
  return edad;
}

const edadJuan = calcularEdad(2010);   // 15
const edadMaria = calcularEdad(2008);  // 17
const edadPedro = calcularEdad(2012);  // 13
```

> ¿Ves la diferencia?
>
> Escribimos el cálculo una sola vez, y lo usamos tres veces. ¡Mucho mejor!

---

## Cómo crear una función

Hay dos cosas diferentes con las funciones:
1. **Definir/crear** la función (escribir la receta)
2. **Llamar/usar** la función (usar la receta)

Primero veamos cómo **definir** una función:

```js
function nombreDeLaFuncion(parametros) {
  // código que hace algo
  return resultado;
}
```

Las partes de la definición son:

1. **function** - La palabra que dice "voy a crear una función" (igual que `const` o `let` dicen "voy a crear una variable", o `while` dice "voy a crear un bucle")
2. **nombreDeLaFuncion** - El nombre que le das (debe ser descriptivo, como `calcularEdad` o `sumarNumeros`)
3. **parametros** - Funciona como una variable que puede recibir diferentes valores cada vez que usas la función (va entre paréntesis, por ejemplo: `anioNacimiento`)
4. **{ }** - Las llaves que encierran el cuerpo de la función
5. **código** - Las instrucciones que va a ejecutar la función (va dentro de las llaves)
6. **return** - Lo que la función devuelve como resultado

> Es como darle un nombre a una receta de cocina y escribir qué ingredientes necesita.

---

## Tu primera función

Vamos a crear una función simple que suma dos números:

```js
function sumar(a, b) {
  const resultado = a + b;
  return resultado;
}
```

Ahora podemos usar esta función:

```js
const suma1 = sumar(5, 3);
// suma1 es 8

const suma2 = sumar(10, 20);
// suma2 es 30

const suma3 = sumar(100, 50);
// suma3 es 150
```

> ¿Ves cómo funciona?
>
> Creamos la función una vez, y la usamos tres veces con números diferentes.

---

## Llamar una función

**Llamar** una función significa usarla. Para llamar una función, escribes su nombre seguido de paréntesis con los valores que necesita:

```js
sumar(5, 3)
```

Aquí:
- `sumar` es el nombre de la función
- `5` y `3` son los valores que le pasas
- La función hace su trabajo y devuelve `8`

Es como pedirle a alguien que haga algo: "Oye sumar, suma 5 y 3 por favor".

---

## Parámetros y argumentos

Es importante entender la diferencia:

**Parámetros** = Los usas cuando **defines** la función (son como variables que esperan un valor)

```js
function saludar(nombre) {  // "nombre" es un parámetro
  const mensaje = "Hola " + nombre;
  return mensaje;
}
```

Aquí `nombre` es un parámetro. Es como un espacio vacío que se llenará después.

**Argumentos** = Los usas cuando **llamas** la función (son los valores reales que le pasas)

```js
const saludo1 = saludar("Ana");     // "Ana" es un argumento
// saludo1 es "Hola Ana"

const saludo2 = saludar("Carlos");  // "Carlos" es un argumento
// saludo2 es "Hola Carlos"
```

Aquí `"Ana"` y `"Carlos"` son argumentos.

> **Resumen:**
>
> - **Parámetros** = las variables en la definición de la función que permiten usar un valor diferente cada vez que la llamas
> - **Argumentos** = los valores concretos que le pasas cuando llamas la función

---

## Funciones con un parámetro

Ejemplo simple:

```js
function duplicar(numero) {
  return numero * 2;
}

const doble1 = duplicar(5);   // 10
const doble2 = duplicar(15);  // 30
const doble3 = duplicar(7);   // 14
```

Otro ejemplo:

```js
function hacerMayuscula(texto) {
  return texto.toUpperCase();
}

const grito1 = hacerMayuscula("hola");  // "HOLA"
const grito2 = hacerMayuscula("adiós"); // "ADIÓS"
```

---

## Funciones con dos parámetros

Puedes tener más de un parámetro, separados por comas:

```js
function multiplicar(a, b) {
  return a * b;
}

const producto1 = multiplicar(5, 3);   // 15
const producto2 = multiplicar(10, 4);  // 40
const producto3 = multiplicar(7, 6);   // 42
```

Otro ejemplo:

```js
function crearNombreCompleto(nombre, apellido) {
  return nombre + " " + apellido;
}

const persona1 = crearNombreCompleto("Ana", "García");      // "Ana García"
const persona2 = crearNombreCompleto("Carlos", "Martínez"); // "Carlos Martínez"
```

---

## Funciones con tres o más parámetros

Puedes tener todos los parámetros que necesites:

```js
function calcularPromedio(nota1, nota2, nota3) {
  const suma = nota1 + nota2 + nota3;
  const promedio = suma / 3;
  return promedio;
}

const promedio1 = calcularPromedio(8, 9, 7);    // 8
const promedio2 = calcularPromedio(10, 9, 10);  // 9.666...
```

Con cuatro parámetros:

```js
function crearDireccion(calle, numero, ciudad, pais) {
  return calle + " " + numero + ", " + ciudad + ", " + pais;
}

const direccion = crearDireccion("Main St", "123", "Madrid", "España");
// "Main St 123, Madrid, España"
```

---

## La palabra return

`return` es como la salida de la máquina. Es lo que la función te devuelve.

```js
function restar(a, b) {
  const resultado = a - b;
  return resultado;  // Esto es lo que sale de la función
}

const diferencia = restar(10, 3);
// diferencia es 7
```

> Importante: Cuando la función llega a `return`, se detiene inmediatamente.

```js
function ejemplo() {
  return 5;
  // Todo lo que esté después de return NO se ejecuta
  const x = 10;  // Esta línea nunca se ejecuta
}
```

---

## Return directo

Puedes hacer return directamente sin guardar en una variable:

```js
// Forma larga:
function sumar(a, b) {
  const resultado = a + b;
  return resultado;
}

// Forma corta (hace lo mismo):
function sumar(a, b) {
  return a + b;
}
```

Ambas formas funcionan igual. La segunda es más corta.

---

## Funciones sin parámetros

Algunas funciones no necesitan parámetros:

```js
function saludar() {
  return "Hola, ¿cómo estás?";
}

const mensaje1 = saludar();  // "Hola, ¿cómo estás?"
const mensaje2 = saludar();  // "Hola, ¿cómo estás?"
```

Otro ejemplo:

```js
function obtenerFechaActual() {
  return "2025-11-09";
}

const hoy = obtenerFechaActual();
```

> Aún necesitas los paréntesis `()` aunque no haya parámetros.

---

## Funciones sin return

Algunas funciones no devuelven nada, solo hacen algo:

```js
function mostrarMensaje(texto) {
  // Esta función no devuelve nada
  // Solo podría hacer algo como mostrar en pantalla
}
```

Si una función no tiene `return`, devuelve `undefined`:

```js
function sinReturn() {
  const x = 5;
  // no hay return
}

const resultado = sinReturn();
// resultado es undefined
```

> En este curso nos enfocaremos en funciones que devuelven valores con `return`.

---

## Usar funciones dentro de otras operaciones

Puedes usar el resultado de una función directamente:

```js
function multiplicar(a, b) {
  return a * b;
}

const resultado = multiplicar(5, 3) + 10;
// Primero multiplica 5 * 3 = 15
// Luego suma 15 + 10 = 25
// resultado es 25
```

En condiciones:

```js
function esMayorDeEdad(edad) {
  return edad >= 18;
}

if (esMayorDeEdad(20)) {
  // Esto se ejecuta porque 20 >= 18 es true
}
```

En template literals:

```js
function obtenerNombre() {
  return "Ana";
}

const mensaje = `Hola ${obtenerNombre()}, ¿cómo estás?`;
// mensaje es "Hola Ana, ¿cómo estás?"
```

---

## Funciones que llaman a otras funciones

Una función puede usar otras funciones:

```js
function sumar(a, b) {
  return a + b;
}

function multiplicar(a, b) {
  return a * b;
}

function calcularTotal(precio, cantidad) {
  const subtotal = multiplicar(precio, cantidad);
  const impuesto = multiplicar(subtotal, 0.16);
  const total = sumar(subtotal, impuesto);
  return total;
}

const total = calcularTotal(100, 3);
// total es 348
```

---

## Funciones con arrays

Las funciones son muy útiles con arrays:

```js
function sumarArray(numeros) {
  let suma = 0;
  let i = 0;
  
  while (i < numeros.length) {
    suma = suma + numeros[i];
    i++;
  }
  
  return suma;
}

const total1 = sumarArray([5, 10, 15]);        // 30
const total2 = sumarArray([1, 2, 3, 4, 5]);    // 15
```

Encontrar el mayor:

```js
function encontrarMayor(numeros) {
  let mayor = numeros[0];
  let i = 1;
  
  while (i < numeros.length) {
    if (numeros[i] > mayor) {
      mayor = numeros[i];
    }
    i++;
  }
  
  return mayor;
}

const max1 = encontrarMayor([5, 12, 8, 20, 3]);  // 20
const max2 = encontrarMayor([45, 23, 67, 12]);   // 67
```

---

## Funciones con objetos

Puedes recibir objetos como parámetros:

```js
function calcularAreaRectangulo(rectangulo) {
  return rectangulo.ancho * rectangulo.alto;
}

const rect1 = { ancho: 5, alto: 10 };
const area1 = calcularAreaRectangulo(rect1);  // 50

const rect2 = { ancho: 8, alto: 3 };
const area2 = calcularAreaRectangulo(rect2);  // 24
```

O crear objetos:

```js
function crearPersona(nombre, edad) {
  return {
    nombre: nombre,
    edad: edad
  };
}

const persona1 = crearPersona("Ana", 25);
// persona1 es { nombre: "Ana", edad: 25 }

const persona2 = crearPersona("Carlos", 30);
// persona2 es { nombre: "Carlos", edad: 30 }
```

---

## Ámbito de variables (scope)

Las variables creadas dentro de una función solo existen dentro de esa función:

```js
function ejemplo() {
  const x = 10;  // x solo existe aquí dentro
  return x;
}

const resultado = ejemplo();  // 10
// x NO existe aquí fuera
```

Esto está bien:

```js
function sumar(a, b) {
  const resultado = a + b;
  return resultado;
}

const total = sumar(5, 3);  // 8
// resultado solo existe dentro de la función
```

Pero esto NO funciona:

```js
function ejemplo() {
  const mensaje = "Hola";
}

const texto = mensaje;  // ❌ Error: mensaje no está definido
// mensaje solo existe dentro de la función
```

> Piensa en las funciones como cajas: lo que está dentro de la caja, se queda dentro de la caja.

---

## Variables de fuera de las funciones

Las funciones pueden usar variables que están fuera:

```js
const impuesto = 0.16;

function calcularTotal(precio) {
  const total = precio + (precio * impuesto);
  return total;
}

const total1 = calcularTotal(100);  // 116
const total2 = calcularTotal(200);  // 232
```

Pero es mejor pasar todo como parámetros:

```js
function calcularTotal(precio, impuesto) {
  const total = precio + (precio * impuesto);
  return total;
}

const total1 = calcularTotal(100, 0.16);  // 116
const total2 = calcularTotal(200, 0.16);  // 232
```

---

## Ejemplos prácticos

### Ejemplo 1: Convertir temperatura

```js
function celsiusAFahrenheit(celsius) {
  return (celsius * 9/5) + 32;
}

const temp1 = celsiusAFahrenheit(0);    // 32
const temp2 = celsiusAFahrenheit(100);  // 212
const temp3 = celsiusAFahrenheit(25);   // 77
```

### Ejemplo 2: Validar edad

```js
function puedeVotar(edad) {
  return edad >= 18;
}

const persona1 = puedeVotar(20);  // true
const persona2 = puedeVotar(15);  // false
```

### Ejemplo 3: Calcular descuento

```js
function aplicarDescuento(precio, porcentaje) {
  const descuento = precio * (porcentaje / 100);
  const precioFinal = precio - descuento;
  return precioFinal;
}

const precio1 = aplicarDescuento(100, 10);  // 90
const precio2 = aplicarDescuento(50, 20);   // 40
```

### Ejemplo 4: Obtener iniciales

```js
function obtenerIniciales(nombre, apellido) {
  const inicial1 = nombre[0];
  const inicial2 = apellido[0];
  return inicial1 + inicial2;
}

const iniciales1 = obtenerIniciales("Ana", "García");      // "AG"
const iniciales2 = obtenerIniciales("Carlos", "Martínez"); // "CM"
```

### Ejemplo 5: Contar palabras

```js
function contarPalabras(texto) {
  let contador = 0;
  let i = 0;
  
  while (i < texto.length) {
    if (texto[i] === " ") {
      contador++;
    }
    i++;
  }
  
  return contador + 1;
}

const cantidad1 = contarPalabras("Hola mundo");           // 2
const cantidad2 = contarPalabras("JavaScript es genial"); // 3
```

### Ejemplo 6: Calcular precio con múltiples productos

```js
function calcularCarrito(productos) {
  let total = 0;
  let i = 0;
  
  while (i < productos.length) {
    total = total + productos[i].precio;
    i++;
  }
  
  return total;
}

const carrito1 = [
  { nombre: "Laptop", precio: 1000 },
  { nombre: "Mouse", precio: 25 }
];

const total1 = calcularCarrito(carrito1);  // 1025
```

---

## Por qué usar funciones

Las funciones te ayudan a:

1. **No repetir código** - Escribes una vez, usas muchas veces
2. **Organizar tu código** - Cada función hace una cosa específica
3. **Encontrar errores más fácil** - Si algo falla, sabes dónde buscar
4. **Reutilizar código** - Puedes usar la misma función en diferentes proyectos

> Las funciones son como herramientas en una caja de herramientas. Cada una tiene un propósito específico.

---

## Resumen

- Las funciones son bloques de código reutilizables
- Se crean con `function nombreFuncion(parametros) { ... }`
- Se llaman escribiendo `nombreFuncion(argumentos)`
- `return` devuelve el resultado de la función
- Los parámetros son variables que la función necesita
- Los argumentos son los valores reales que le pasas
- Las variables dentro de funciones solo existen ahí dentro
- Las funciones te ayudan a no repetir código

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
function multiplicarPor3(numero) {
  return numero * 3;
}

const resultado = multiplicarPor3(5);
// valor de resultado
```

#### b)

```js
function sumar(a, b) {
  return a + b;
}

const total = sumar(10, 20) + 5;
// valor de total
```

#### c)

```js
function obtenerPrimero(array) {
  return array[0];
}

const numeros = [7, 2, 9, 4];
const primero = obtenerPrimero(numeros);
// valor de primero
```

#### d)

```js
function combinar(texto1, texto2) {
  return texto1 + " " + texto2;
}

const frase = combinar("Hola", "mundo");
// valor de frase
```

#### e)

```js
function esPositivo(numero) {
  return numero > 0;
}

const resultado = esPositivo(-5);
// valor de resultado
```

### 2. Encuentra los errores

Identifica y corrige los errores:

#### a)

```js
function sumar(a, b) {
  resultado = a + b;
}

const total = sumar(5, 3);
```

#### b)

```js
function multiplicar(a, b) {
  return a * b
}

const producto multiplicar(4, 5);
```

#### c)

```js
function saludar(nombre) {
  return "Hola " + nombre;

const mensaje = saludar("Ana");
```

#### d)

```js
function dividir(a, b)
  return a / b;
}

const resultado = dividir(10, 2);
```

### 3. Crea funciones

Para estos ejercicios, utiliza tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea una función llamada `restar` que reciba dos números y devuelva su resta.

#### b)

Crea una función llamada `obtenerUltimo` que reciba un array y devuelva el último elemento.

#### c)

Crea una función llamada `crearSaludo` que reciba un nombre y devuelva "Hola [nombre], bienvenido".

#### d)

Crea una función llamada `calcularIVA` que reciba un precio y devuelva el IVA (16% del precio).

#### e)

Crea una función llamada `esParOImpar` que reciba un número y devuelva "par" si es par o "impar" si es impar.

### 4. Funciones con arrays

#### a)

Crea una función que reciba un array de números y devuelva la suma de todos.

#### b)

Crea una función que reciba un array de números y devuelva el menor.

#### c)

Crea una función que reciba un array de strings y devuelva la cantidad de elementos.

#### d)

Crea una función que reciba un array de números y devuelva un nuevo array con cada número multiplicado por 2.

#### e)

Crea una función que reciba un array de números y devuelva cuántos son mayores que 10.

### 5. Funciones con objetos

#### a)

Crea una función que reciba un objeto persona con nombre y edad, y devuelva "Mayor de edad" o "Menor de edad".

#### b)

Crea una función que reciba un objeto producto con precio y cantidad, y devuelva el total (precio * cantidad).

#### c)

Crea una función que reciba dos parámetros (nombre y edad) y devuelva un objeto con esas propiedades.

#### d)

Crea una función que reciba un array de objetos (productos con precio) y devuelva el total de todos los precios.

#### e)

Crea una función que reciba un objeto rectangulo con ancho y alto, y devuelva el perímetro (2 * ancho + 2 * alto).

### 6. Desafíos

#### a)

Crea una función que reciba un string y devuelva el string al revés. Por ejemplo, "hola" → "aloh".

#### b)

Crea una función que reciba un número y devuelva true si es primo, false si no lo es.

#### c)

Crea una función que reciba dos arrays de números y devuelva un nuevo array con los elementos de ambos arrays combinados.

#### d)

Crea una función que reciba un array de números y devuelva un objeto con dos propiedades: pares (array con números pares) e impares (array con números impares).


