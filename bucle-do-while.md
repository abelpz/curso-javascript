# Bucle do...while

## Qué es un bucle do...while

El bucle **do...while** es una variación del bucle while. La diferencia principal es que **siempre se ejecuta al menos una vez**, incluso si la condición es falsa desde el principio.

Ya conoces el bucle while y el bucle for. El bucle do...while es como el while, pero verifica la condición **después** de ejecutar el código, no antes.

> ¿Recuerdas el bucle while?
>
> Con while, si la condición es falsa desde el inicio, el código nunca se ejecuta.

Veamos la diferencia:

Con while (puede no ejecutarse nunca):

```js
let i = 5;

while (i < 3) {
  i++;
}

// El código nunca se ejecutó porque 5 no es menor que 3
// i sigue siendo 5
```

Con do...while (se ejecuta al menos una vez):

```js
let i = 5;

do {
  i++;
} while (i < 3);

// El código se ejecutó una vez aunque 5 no es menor que 3
// i es 6
```

---

## Sintaxis del bucle do...while

La estructura del bucle do...while es:

```js
do {
  // código que se ejecuta al menos una vez
} while (condición);
```

> Observa la estructura:
>
> - Primero viene `do` (hacer)
> - Luego el código entre llaves
> - Después viene `while` con la condición
> - Termina con punto y coma `;`

---

## Tu primer bucle do...while

Veamos un ejemplo simple:

```js
let contador = 1;

do {
  contador++;
} while (contador < 5);

// contador es 5
```

Analicemos qué pasa en cada iteración:

**Primera ejecución:**
- contador es 1
- Se ejecuta el código: contador++
- contador ahora es 2
- ¿2 < 5? Sí, entonces continúa

**Segunda ejecución:**
- contador es 2
- Se ejecuta el código: contador++
- contador ahora es 3
- ¿3 < 5? Sí, entonces continúa

**Tercera ejecución:**
- contador es 3
- Se ejecuta el código: contador++
- contador ahora es 4
- ¿4 < 5? Sí, entonces continúa

**Cuarta ejecución:**
- contador es 4
- Se ejecuta el código: contador++
- contador ahora es 5
- ¿5 < 5? No, entonces se detiene

---

## La diferencia clave: ejecución garantizada

La característica más importante del do...while es que **siempre se ejecuta al menos una vez**:

```js
let numero = 10;

do {
  numero = numero + 5;
} while (numero < 5);

// numero es 15
// El código se ejecutó una vez, aunque 10 no es menor que 5
```

Compáralo con while:

```js
let numero = 10;

while (numero < 5) {
  numero = numero + 5;
}

// numero es 10
// El código nunca se ejecutó porque 10 no es menor que 5
```

---

## Cuándo usar do...while

El bucle do...while es útil cuando necesitas que el código se ejecute **al menos una vez** antes de verificar la condición.

### Casos comunes:

1. **Validar entrada del usuario** (cuando sepas sobre input)
2. **Ejecutar un proceso al menos una vez**
3. **Menús que deben mostrarse al menos una vez**

Ejemplo conceptual (sin input real):

```js
let respuesta = "no";
let intentos = 0;

do {
  intentos++;
  // Aquí normalmente pedirías input al usuario
  // Por ahora, simulamos que después de 3 intentos responde "sí"
  if (intentos === 3) {
    respuesta = "sí";
  }
} while (respuesta !== "sí");

// intentos es 3
// respuesta es "sí"
```

---

## Contando con do...while

Puedes usar do...while para contar, igual que con while o for:

Contar hacia arriba:

```js
let i = 1;
let resultado = "";

do {
  resultado = resultado + i + " ";
  i++;
} while (i <= 5);

// resultado es "1 2 3 4 5 "
```

Contar hacia abajo:

```js
let cuenta = 5;
let texto = "";

do {
  texto = texto + cuenta + " ";
  cuenta--;
} while (cuenta > 0);

// texto es "5 4 3 2 1 "
```

---

## Recorriendo arrays con do...while

Puedes usar do...while para recorrer arrays, aunque es menos común que usar for o while:

```js
const frutas = ["manzana", "pera", "naranja"];
let i = 0;
let lista = "";

do {
  lista = lista + frutas[i] + " ";
  i++;
} while (i < frutas.length);

// lista es "manzana pera naranja "
```

> ¿Cuándo usar do...while con arrays?
>
> Normalmente es mejor usar for o while para arrays. Usa do...while cuando necesites que se ejecute al menos una vez, incluso si el array está vacío (aunque esto puede causar errores).

Ten cuidado con arrays vacíos:

```js
const vacio = [];
let i = 0;
let resultado = "inicio";

do {
  // Esto causará un error si el array está vacío
  // porque vacio[0] es undefined
  resultado = resultado + vacio[i];
  i++;
} while (i < vacio.length);

// resultado es "inicioundefined"
```

Por eso, para arrays es mejor verificar primero:

```js
const numeros = [5, 10, 15];
let suma = 0;

if (numeros.length > 0) {
  let i = 0;
  do {
    suma = suma + numeros[i];
    i++;
  } while (i < numeros.length);
}

// suma es 30
```

---

## Operaciones con do...while

Puedes hacer operaciones matemáticas:

```js
let i = 1;
let suma = 0;

do {
  suma = suma + i;
  i++;
} while (i <= 10);

// suma es 55 (1+2+3+4+5+6+7+8+9+10)
```

Multiplicar números:

```js
let i = 1;
let producto = 1;

do {
  producto = producto * i;
  i++;
} while (i <= 5);

// producto es 120 (5! = 5*4*3*2*1)
```

---

## do...while con condicionales

Puedes combinar do...while con if:

```js
let contador = 0;
let pares = 0;
let impares = 0;

do {
  if (contador % 2 === 0) {
    pares++;
  } else {
    impares++;
  }
  contador++;
} while (contador < 10);

// contador es 10
// pares es 5 (0, 2, 4, 6, 8)
// impares es 5 (1, 3, 5, 7, 9)
```

---

## do...while con objetos

Trabajando con arrays de objetos:

```js
const productos = [
  { nombre: "Laptop", precio: 1000, stock: 5 },
  { nombre: "Mouse", precio: 25, stock: 0 },
  { nombre: "Teclado", precio: 50, stock: 3 }
];

let i = 0;
let disponibles = 0;

if (productos.length > 0) {
  do {
    if (productos[i].stock > 0) {
      disponibles++;
    }
    i++;
  } while (i < productos.length);
}

// disponibles es 2
```

---

## Usando break con do...while

Puedes usar `break` para salir del bucle antes de tiempo:

```js
let contador = 0;
let encontrado = false;

do {
  contador++;
  if (contador === 5) {
    encontrado = true;
    break;
  }
} while (contador < 10);

// contador es 5
// encontrado es true
```

Con arrays:

```js
const numeros = [3, 7, 12, 15, 20];
let i = 0;
let resultado = -1;

if (numeros.length > 0) {
  do {
    if (numeros[i] > 10) {
      resultado = numeros[i];
      break;
    }
    i++;
  } while (i < numeros.length);
}

// resultado es 12 (el primer número mayor que 10)
```

---

## Usando continue con do...while

El `continue` salta a la siguiente iteración:

```js
let i = 0;
let suma = 0;

do {
  i++;
  if (i === 5) {
    continue;
  }
  suma = suma + i;
} while (i < 10);

// suma es 50 (1+2+3+4+6+7+8+9+10, sin el 5)
// i es 10
```

---

## Ejemplos prácticos

### Ejemplo 1: Simulación de reintentos

```js
let intentos = 0;
const maximoIntentos = 5;
let exito = false;

do {
  intentos++;
  // Simulamos que en el intento 3 tiene éxito
  if (intentos === 3) {
    exito = true;
  }
} while (!exito && intentos < maximoIntentos);

// intentos es 3
// exito es true
```

### Ejemplo 2: Procesar hasta condición

```js
let numero = 1;
let suma = 0;

do {
  suma = suma + numero;
  numero++;
} while (suma < 100);

// suma es 105 (1+2+3+...+14)
// numero es 15
```

### Ejemplo 3: Acumular hasta límite

```js
let saldo = 1000;
const precioProducto = 150;
let compras = 0;

do {
  saldo = saldo - precioProducto;
  compras++;
} while (saldo >= precioProducto);

// saldo es 100
// compras es 6
```

### Ejemplo 4: Generar números hasta condición

```js
let numero = 1;
const numeros = [];

do {
  numeros[numeros.length] = numero;
  numero = numero * 2;
} while (numero <= 100);

// numeros es [1, 2, 4, 8, 16, 32, 64]
```

### Ejemplo 5: Sumar dígitos de un número

```js
let numero = 12345;
let suma = 0;

do {
  suma = suma + (numero % 10);
  numero = Math.floor(numero / 10);
} while (numero > 0);

// suma es 15 (1+2+3+4+5)
```

---

## Comparación: while vs do...while

### while:
```js
let i = 5;

while (i < 3) {
  i++;
}

// i es 5 (nunca se ejecutó)
```

### do...while:
```js
let i = 5;

do {
  i++;
} while (i < 3);

// i es 6 (se ejecutó una vez)
```

---

## ¿Cuándo usar cada bucle?

### Usa for cuando:
- Sabes cuántas veces repetir
- Recorres un array
- Quieres todo organizado (inicio, condición, incremento)

### Usa while cuando:
- No sabes cuántas veces repetir
- La condición debe verificarse ANTES de ejecutar
- Puede que nunca se ejecute

### Usa do...while cuando:
- No sabes cuántas veces repetir
- El código DEBE ejecutarse AL MENOS UNA VEZ
- La condición debe verificarse DESPUÉS de ejecutar

---

## Consejos importantes

### 1. Recuerda el punto y coma final

```js
// ✓ BIEN
do {
  // código
} while (condición);

// ✗ MAL
do {
  // código
} while (condición)
```

### 2. Verifica arrays vacíos

```js
// ✓ BIEN
const array = [1, 2, 3];
if (array.length > 0) {
  let i = 0;
  do {
    // código
    i++;
  } while (i < array.length);
}

// ✗ RIESGOSO
const array = [];
let i = 0;
do {
  const valor = array[i]; // Error si array está vacío
  i++;
} while (i < array.length);
```

### 3. Asegura que el bucle pueda terminar

```js
// ✓ BIEN
let i = 0;
do {
  i++;
} while (i < 10);

// ✗ MAL - bucle infinito
let i = 0;
do {
  // i nunca cambia
} while (i < 10);
```

---

## Resumen

- `do...while` ejecuta el código al menos una vez antes de verificar la condición
- La condición se verifica **después** de cada ejecución
- Es útil cuando necesitas garantizar al menos una ejecución
- La sintaxis termina con punto y coma `;`
- Puedes usar `break` y `continue`
- Es el menos usado de los tres bucles (for, while, do...while)
- Ten cuidado con arrays vacíos

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
let x = 0;
do {
  x++;
} while (x < 5);
// valor de x
```

#### b)

```js
let x = 10;
do {
  x++;
} while (x < 5);
// valor de x
```

#### c)

```js
let suma = 0;
let i = 1;
do {
  suma = suma + i;
  i++;
} while (i <= 5);
// valor de suma
```

#### d)

```js
let contador = 5;
do {
  contador--;
} while (contador > 0);
// valor de contador
```

#### e)

```js
let resultado = "";
let i = 1;
do {
  resultado = resultado + i;
  i++;
} while (i <= 3);
// valor de resultado
```

### 2. Encuentra los errores

Identifica y corrige los errores:

#### a)

```js
let i = 0;
do {
  i++;
} while (i < 5)
```

#### b)

```js
do {
  i++;
} while (i < 5);
```

#### c)

```js
let x = 0;
do
  x++;
while (x < 3);
```

#### d)

```js
let x = 0;
while (x < 5) do {
  x++;
}
```

### 3. Compara bucles

Para cada bucle while, escribe su equivalente en do...while:

#### a)

```js
let i = 0;
while (i < 10) {
  i++;
}
```

#### b)

```js
let suma = 0;
let i = 1;
while (i <= 5) {
  suma = suma + i;
  i++;
}
```

#### c)

```js
const numeros = [5, 10, 15, 20];
let i = 0;
let total = 0;
while (i < numeros.length) {
  total = total + numeros[i];
  i++;
}
```

### 4. Escribe bucles do...while

Para estos ejercicios, utiliza tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Escribe un bucle do...while que cuente del 1 al 10.

#### b)

Escribe un bucle do...while que sume los números del 1 al 20.

#### c)

Usa do...while para multiplicar los números del 1 al 5 (factorial de 5).

#### d)

Dado el array `[10, 20, 30, 40, 50]`, usa do...while para sumar todos sus elementos (incluye validación para array vacío).

#### e)

Escribe un bucle do...while que genere los múltiplos de 7 menores que 100 y los guarde en un array.

### 5. Problemas prácticos

#### a)

Usa do...while para encontrar el primer número divisible por 7 entre 50 y 100.

#### b)

Dado un número como 9876, usa do...while para invertir sus dígitos (resultado: 6789). Pista: usa `numero % 10` para obtener el último dígito y `Math.floor(numero / 10)` para eliminar el último dígito.

#### c)

Crea un bucle do...while que simule un proceso de "reintentos". Empieza con `intentos = 0` y `exito = false`. Incrementa intentos en cada iteración. Simula que el éxito ocurre cuando intentos sea igual a un número aleatorio entre 1 y 10 (usa `Math.floor(Math.random() * 10) + 1` para el número objetivo, pero defínelo antes del bucle).

#### d)

Dado el array de objetos:

```js
const tareas = [
  { nombre: "Estudiar", completada: false },
  { nombre: "Ejercicio", completada: true },
  { nombre: "Compras", completada: false },
  { nombre: "Leer", completada: true }
];
```

Usa do...while para contar cuántas tareas están completadas (con validación de array vacío).

#### e)

Escribe un bucle do...while que genere potencias de 2 (2, 4, 8, 16, 32, ...) hasta que el valor supere 1000. Guarda todos los valores en un array.

### 6. Desafíos

#### a)

Compara el comportamiento: crea tres versiones del mismo código (una con for, una con while, y una con do...while) que sumen los números del 1 al 100. ¿Cuál prefieres y por qué?

#### b)

Usa do...while para verificar si un número es primo. Por ejemplo, dado el número 17, verifica si es divisible por algún número entre 2 y 16.

#### c)

Dado el array `[5, 3, 8, 1, 9, 2, 7, 4, 6]`, usa do...while para ordenarlo de menor a mayor (bubble sort). Este es un desafío avanzado que requiere bucles anidados.



