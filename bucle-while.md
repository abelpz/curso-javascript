# Bucle while

## El problema: hacer lo mismo muchas veces

Tienes una lista de precios y necesitas saber el total. Sin bucles, tendrías que escribir:

```js
const precios = [15, 23, 8, 45, 12];

let total = 0;
total = total + precios[0];  // 15
total = total + precios[1];  // 23
total = total + precios[2];  // 8
total = total + precios[3];  // 45
total = total + precios[4];  // 12

// total es 103
```

> ¿Te das cuenta del problema?
>
> Escribimos casi lo mismo 5 veces. Solo cambia el número entre corchetes.

¿Y si tuvieras 100 precios? ¿O 1000? Sería imposible escribir todo eso.

**La solución:** Un bucle hace esto por ti automáticamente.

---

## Qué es un bucle while

Un bucle **while** significa "mientras" en inglés. Es como decirle a JavaScript:

**"Mientras esto sea verdad, sigue haciendo esto"**

Es como cuando lavas platos: "Mientras haya platos sucios, sigue lavando". Te detienes cuando no quedan platos.

---

Ahora podemos resolver el problema anterior. En lugar de sumar cada precio a mano, le pedimos a JavaScript que lo haga:

```js
const precios = [15, 23, 8, 45, 12];

let total = 0;
let i = 0;

while (i < precios.length) {
  total = total + precios[i];
  i++;
}

// total es 103
```

> ¿Ves la diferencia?
>
> Con el bucle escribimos menos líneas, pero JavaScript suma los 5 precios (o los que sean) automáticamente.

Este código le dice a JavaScript: "Mientras haya precios en la lista, sigue sumándolos".

---

## Cómo se escribe un bucle while

Un bucle while tiene tres partes, como una receta:

```js
while (condición) {
  // código que quieres repetir
}
```

Las partes son:

1. **while** - La palabra que le dice a JavaScript "vamos a repetir algo"
2. **La condición entre paréntesis ( )** - Es la pregunta que JavaScript hace cada vez: ¿sigo o paro?
3. **El código entre llaves { }** - Es lo que quieres que se repita

> Es como los condicionales if:
>
> `if` pregunta una vez y decide. `while` pregunta muchas veces y repite.

---

## Tu primer bucle while

Vamos a hacer algo muy simple: contar del 1 al 3.

```js
let contador = 1;

while (contador <= 3) {
  contador = contador + 1;
}

// contador es 4
```

> Espera, ¿por qué contador termina en 4 si solo queríamos contar hasta 3?
>
> Vamos a verlo paso a paso para entenderlo.

---

### Cómo funciona paso a paso

Imagina que eres JavaScript leyendo este código línea por línea:

**Paso 1 - Empezamos:**
- Línea 1: `let contador = 1;`
- Creamos la variable contador con el valor 1

**Paso 2 - Primera pregunta:**
- Línea 3: `while (contador <= 3)`
- JavaScript pregunta: "¿contador es menor o igual a 3?"
- ¿1 es menor o igual a 3? ✓ Sí
- Como la respuesta es sí, entra a hacer lo que está entre las llaves

**Paso 3 - Primer trabajo:**
- Línea 4: `contador = contador + 1;`
- Cambiamos contador: 1 + 1 = 2
- Ahora contador vale 2
- Terminamos las llaves, volvemos arriba a preguntar otra vez

**Paso 4 - Segunda pregunta:**
- Línea 3: `while (contador <= 3)`
- JavaScript pregunta otra vez: "¿contador es menor o igual a 3?"
- ¿2 es menor o igual a 3? ✓ Sí
- Entramos otra vez

**Paso 5 - Segundo trabajo:**
- Línea 4: Cambiamos contador: 2 + 1 = 3
- Ahora contador vale 3
- Volvemos arriba a preguntar

**Paso 6 - Tercera pregunta:**
- Línea 3: "¿contador es menor o igual a 3?"
- ¿3 es menor o igual a 3? ✓ Sí (3 es igual a 3)
- Entramos otra vez

**Paso 7 - Tercer trabajo:**
- Línea 4: Cambiamos contador: 3 + 1 = 4
- Ahora contador vale 4
- Volvemos arriba a preguntar

**Paso 8 - Cuarta pregunta:**
- Línea 3: "¿contador es menor o igual a 3?"
- ¿4 es menor o igual a 3? ✗ No
- Como la respuesta es no, NO entramos
- El bucle termina

**Resultado final:** contador es 4

> **Resumen:** El bucle preguntó 4 veces, pero solo entró 3 veces. La última vez dijo "no" y se detuvo. Por eso contador termina en 4.

---

## El contador en bucles

El **contador** es como un reloj que cuenta cuántas veces has hecho algo. Para que funcione bien necesitas tres cosas:

1. **Crear el contador** - Antes del bucle, con un número inicial
2. **Cambiar el contador** - Dentro del bucle, cada vez que se repite
3. **Que se acerque al final** - El contador debe moverse hacia donde el bucle debe parar

```js
let i = 0;

while (i < 5) {
  i = i + 1;
}

// i es 5
```

> ¿Qué pasa si olvidas cambiar el contador?
>
> ¡El bucle nunca termina! Es como correr en círculos para siempre. Esto se llama **bucle infinito**.

Ejemplo de bucle infinito (NO hagas esto):

```js
let numero = 1;

while (numero < 10) {
  // Ups, olvidamos cambiar numero
  // El bucle pregunta "¿1 < 10?" y la respuesta siempre es sí
  // ¡Nunca termina!
}
```

---

## Contando con while

Puedes contar hacia arriba (1, 2, 3, 4, 5...):

```js
let cuenta = 1;

while (cuenta <= 5) {
  cuenta = cuenta + 1;
}

// cuenta es 6
```

O contar hacia abajo (5, 4, 3, 2, 1...):

```js
let cuenta = 5;

while (cuenta > 0) {
  cuenta = cuenta - 1;
}

// cuenta es 0
```

> Es como subir o bajar escaleras. Puedes ir hacia arriba o hacia abajo, solo cambia la dirección.

---

## Forma más corta de contar

¿Recuerdas los operadores `++` y `+=` de la lección de operadores? Puedes usarlos en los bucles:

```js
let i = 0;

while (i < 3) {
  i++;  // Esto es igual a i = i + 1
}

// i es 3
```

`i++` es una forma más corta de escribir `i = i + 1`.

También puedes contar de 2 en 2, de 3 en 3, o de lo que quieras:

```js
let numero = 0;

while (numero < 10) {
  numero += 2;  // Sube de 2 en 2
}

// numero es 10
// El bucle contó: 0, 2, 4, 6, 8, 10
```

> Es como saltar. En vez de dar un paso (sumar 1), das un salto más grande (sumar 2, 3, 5...).

---

## Haciendo operaciones en el bucle

Puedes realizar operaciones dentro del bucle en cada iteración:

```js
let contador = 1;
let suma = 0;

while (contador <= 5) {
  suma = suma + contador;
  contador++;
}

// contador es 6
// suma es 15 (1 + 2 + 3 + 4 + 5)
```

> Analiza el código:
> ¿Puedes seguir los valores de suma en cada iteración?

**Iteración 1:** suma = 0 + 1 = 1, contador = 2  
**Iteración 2:** suma = 1 + 2 = 3, contador = 3  
**Iteración 3:** suma = 3 + 3 = 6, contador = 4  
**Iteración 4:** suma = 6 + 4 = 10, contador = 5  
**Iteración 5:** suma = 10 + 5 = 15, contador = 6  

---

## Trabajando con strings en bucles

Puedes construir strings usando bucles:

```js
let contador = 1;
let texto = "";

while (contador <= 3) {
  texto = texto + "Hola ";
  contador++;
}

// texto es "Hola Hola Hola "
```

O crear números como texto:

```js
let i = 1;
let numeros = "";

while (i <= 5) {
  numeros = numeros + i + " ";
  i++;
}

// numeros es "1 2 3 4 5 "
```

---

## Bucles con arrays

Los bucles son muy útiles para recorrer arrays:

```js
const frutas = ["manzana", "pera", "naranja"];
let i = 0;

while (i < frutas.length) {
  const fruta = frutas[i];
  i++;
}

// Se accedió a cada fruta del array
```

Construir un nuevo array basado en otro:

```js
const numeros = [1, 2, 3, 4, 5];
const dobles = [];
let i = 0;

while (i < numeros.length) {
  const doble = numeros[i] * 2;
  dobles[i] = doble;
  i++;
}

// dobles es [2, 4, 6, 8, 10]
```

> ¿Ves cómo funciona?
>
> Usamos `i` para acceder a cada posición del array, desde 0 hasta length - 1.

---

## Condiciones más complejas

Puedes usar cualquier condición en un while, no solo comparaciones simples:

```js
let saldo = 100;
let compras = 0;
const precioProducto = 15;

while (saldo >= precioProducto) {
  saldo = saldo - precioProducto;
  compras++;
}

// saldo es 10
// compras es 6
// (Se compraron 6 productos de $15, gastando $90)
```

Con operadores lógicos:

```js
let intentos = 0;
let encontrado = false;
const numeros = [5, 8, 12, 15, 20];
let i = 0;

while (i < numeros.length && !encontrado) {
  if (numeros[i] === 12) {
    encontrado = true;
  }
  intentos++;
  i++;
}

// intentos es 3
// encontrado es true
```

---

## Bucles while con objetos

Puedes usar bucles para trabajar con arrays de objetos:

```js
const productos = [
  { nombre: "Laptop", precio: 1000 },
  { nombre: "Mouse", precio: 25 },
  { nombre: "Teclado", precio: 50 }
];

let i = 0;
let total = 0;

while (i < productos.length) {
  total = total + productos[i].precio;
  i++;
}

// total es 1075
```

---

## Ejemplos prácticos

### Ejemplo 1: Contar hasta un número

```js
let numero = 1;
const limite = 10;

while (numero <= limite) {
  numero++;
}

// numero es 11
```

### Ejemplo 2: Sumar números pares

```js
let i = 2;
let suma = 0;

while (i <= 10) {
  suma = suma + i;
  i = i + 2;
}

// suma es 30 (2 + 4 + 6 + 8 + 10)
```

### Ejemplo 3: Calcular factorial

```js
const numero = 5;
let factorial = 1;
let i = 1;

while (i <= numero) {
  factorial = factorial * i;
  i++;
}

// factorial es 120 (5! = 5 * 4 * 3 * 2 * 1)
```

### Ejemplo 4: Encontrar el mayor número en un array

```js
const numeros = [3, 7, 2, 9, 1, 5];
let mayor = numeros[0];
let i = 1;

while (i < numeros.length) {
  if (numeros[i] > mayor) {
    mayor = numeros[i];
  }
  i++;
}

// mayor es 9
```

### Ejemplo 5: Contar elementos que cumplen una condición

```js
const edades = [15, 22, 17, 30, 12, 25];
let mayoresDeEdad = 0;
let i = 0;

while (i < edades.length) {
  if (edades[i] >= 18) {
    mayoresDeEdad++;
  }
  i++;
}

// mayoresDeEdad es 3
```

### Ejemplo 6: Construir un string con template literals

```js
const nombres = ["Ana", "Carlos", "María"];
let lista = "";
let i = 0;

while (i < nombres.length) {
  lista = lista + `${i + 1}. ${nombres[i]} `;
  i++;
}

// lista es "1. Ana 2. Carlos 3. María "
```

---

## Consejos importantes

### 1. Siempre modifica el contador

```js
// ✓ BIEN
let i = 0;
while (i < 5) {
  i++;
}

// ✗ MAL - bucle infinito
let i = 0;
while (i < 5) {
  // i nunca cambia
}
```

### 2. Asegúrate de que la condición pueda ser falsa

```js
// ✓ BIEN - la condición eventualmente será falsa
let i = 0;
while (i < 10) {
  i++;
}

// ✗ MAL - la condición siempre es verdadera
while (true) {
  // esto nunca termina
}
```

### 3. Inicializa el contador antes del bucle

```js
// ✓ BIEN
let i = 0;
while (i < 5) {
  i++;
}

// ✗ MAL - i no está definido
while (i < 5) {
  i++;
}
```

---

## Resumen

- El bucle `while` repite código mientras una condición sea verdadera
- Necesitas un contador que se inicializa antes del bucle
- El contador debe modificarse dentro del bucle
- La condición debe poder volverse falsa para evitar bucles infinitos
- Los bucles son perfectos para recorrer arrays
- Puedes usar operadores de incremento (`++`, `--`, `+=`, `-=`)

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
let x = 0;
while (x < 4) {
  x++;
}
// valor de x
```

#### b)

```js
let suma = 0;
let i = 1;
while (i <= 4) {
  suma = suma + i;
  i++;
}
// valor de suma
```

#### c)

```js
let contador = 10;
while (contador > 5) {
  contador--;
}
// valor de contador
```

#### d)

```js
let resultado = 1;
let n = 3;
while (n > 0) {
  resultado = resultado * 2;
  n--;
}
// valor de resultado
```

#### e)

```js
const numeros = [2, 4, 6, 8];
let suma = 0;
let i = 0;
while (i < numeros.length) {
  suma = suma + numeros[i];
  i++;
}
// valor de suma
```

### 2. Encuentra los errores

Identifica y corrige los errores en estos bucles:

#### a)

```js
let i = 0;
while (i < 5) {
  // falta algo aquí
}
```

#### b)

```js
while (i < 10) {
  i++;
}
```

#### c)

```js
let x = 5;
while (x > 0) {
  x++;
}
```

#### d)

```js
let contador = 0;
while (contador < 3)
  contador++;
}
```

### 3. Escribe bucles while

Para estos ejercicios, utiliza tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Escribe un bucle while que cuente del 1 al 10 y guarde el resultado final en una variable.

#### b)

Escribe un bucle while que sume todos los números del 1 al 20 y guarde el total en una variable.

#### c)

Escribe un bucle while que multiplique los números del 1 al 5 (factorial de 5) y guarde el resultado.

#### d)

Dado el array `[10, 20, 30, 40, 50]`, usa un bucle while para sumar todos sus elementos.

#### e)

Dado el array `["JavaScript", "Python", "Java", "C++"]`, usa un bucle while para construir un string que contenga todos los lenguajes separados por comas.

### 4. Problemas con arrays

#### a)

Dado el array `[5, 12, 8, 130, 44]`, usa un bucle while para encontrar el número menor.

#### b)

Dado el array `[3, 7, 2, 9, 1, 5, 8]`, usa un bucle while para contar cuántos números son mayores que 5.

#### c)

Dado el array `[1, 2, 3, 4, 5]`, usa un bucle while para crear un nuevo array que contenga cada número multiplicado por 3.

#### d)

Dado el array de objetos:

```js
const productos = [
  { nombre: "Laptop", precio: 800, cantidad: 2 },
  { nombre: "Mouse", precio: 20, cantidad: 5 },
  { nombre: "Teclado", precio: 50, cantidad: 3 }
];
```

Usa un bucle while para calcular el valor total del inventario (precio × cantidad para cada producto, sumados).

#### e)

Dado el array `[15, 22, 8, 42, 17, 30]`, usa un bucle while para crear dos nuevos arrays: uno con los números pares y otro con los impares.

### 5. Desafíos

#### a)

Escribe un bucle while que invierta un array. Por ejemplo, si tienes `[1, 2, 3, 4, 5]`, debe crear un nuevo array `[5, 4, 3, 2, 1]`.

#### b)

Dado un array de strings `["hola", "mundo", "JavaScript"]`, usa un bucle while para contar el total de caracteres en todos los strings combinados.

#### c)

Crea un bucle while que genere los primeros 10 números de la secuencia de Fibonacci y los guarde en un array. La secuencia empieza con 0 y 1, y cada número siguiente es la suma de los dos anteriores: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...

#### d)

Dado un número como 12345, usa un bucle while para sumar todos sus dígitos (1 + 2 + 3 + 4 + 5 = 15). Pista: puedes usar `numero % 10` para obtener el último dígito y `Math.floor(numero / 10)` para eliminar el último dígito.


