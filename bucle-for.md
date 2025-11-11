# Bucle for

## Qué es un bucle for

El bucle **for** es una forma más compacta de escribir bucles cuando sabes exactamente cuántas veces quieres repetir algo. Es especialmente útil para recorrer arrays.

Ya aprendiste sobre el bucle `while`. El bucle `for` hace lo mismo, pero organiza la inicialización, la condición y el incremento en un solo lugar.

> ¿Recuerdas el bucle while?
>
> Con while necesitabas tres cosas separadas: inicializar el contador antes, la condición en el while, y el incremento dentro del bucle.

Compara estos dos bucles que hacen exactamente lo mismo:

Con while:

```js
let i = 0;
while (i < 5) {
  i++;
}
// i es 5
```

Con for:

```js
for (let i = 0; i < 5; i++) {
  // código aquí
}
// i es 5 dentro del bucle, pero no existe fuera
```

---

## Sintaxis del bucle for

La estructura del bucle for tiene tres partes separadas por punto y coma:

```js
for (inicialización; condición; incremento) {
  // código que se repite
}
```

> Las tres partes son:
>
> 1. **Inicialización**: Se ejecuta una sola vez al inicio (creas el contador)
> 2. **Condición**: Se verifica antes de cada iteración (igual que en while)
> 3. **Incremento**: Se ejecuta después de cada iteración (actualizas el contador)

Ejemplo básico:

```js
for (let i = 0; i < 3; i++) {
  // Este código se ejecuta 3 veces
}
```

Analicemos qué pasa:

**Inicio:**
- Se ejecuta `let i = 0` (solo una vez)

**Primera iteración:**
- ¿i < 3? (¿0 < 3?) Sí → ejecuta el código
- Después del código, ejecuta `i++` (i ahora es 1)

**Segunda iteración:**
- ¿i < 3? (¿1 < 3?) Sí → ejecuta el código
- Después del código, ejecuta `i++` (i ahora es 2)

**Tercera iteración:**
- ¿i < 3? (¿2 < 3?) Sí → ejecuta el código
- Después del código, ejecuta `i++` (i ahora es 3)

**Fin:**
- ¿i < 3? (¿3 < 3?) No → el bucle termina

---

## Tu primer bucle for

Veamos un ejemplo simple que cuenta del 1 al 5:

```js
let resultado = "";

for (let i = 1; i <= 5; i++) {
  resultado = resultado + i + " ";
}

// resultado es "1 2 3 4 5 "
```

> Observa el código:
> - Empezamos en 1 (`let i = 1`)
> - Continuamos mientras i sea menor o igual a 5 (`i <= 5`)
> - Aumentamos i en 1 cada vez (`i++`)

---

## Recorriendo arrays con for

El bucle for es perfecto para recorrer arrays. La estructura típica es:

```js
const frutas = ["manzana", "pera", "naranja"];

for (let i = 0; i < frutas.length; i++) {
  const fruta = frutas[i];
}

// Se accedió a cada fruta: "manzana", "pera", "naranja"
```

> ¿Por qué empezamos en 0?
>
> Porque los índices de los arrays empiezan en 0.

> ¿Por qué usamos `i < frutas.length`?
>
> Porque si el array tiene 3 elementos, los índices son 0, 1, 2. El length es 3, así que i < 3 nos da exactamente esos índices.

---

## Operaciones dentro del bucle for

Puedes hacer cualquier operación dentro del bucle:

### Sumar números:

```js
let suma = 0;

for (let i = 1; i <= 10; i++) {
  suma = suma + i;
}

// suma es 55 (1+2+3+4+5+6+7+8+9+10)
```

### Sumar elementos de un array:

```js
const numeros = [5, 10, 15, 20];
let total = 0;

for (let i = 0; i < numeros.length; i++) {
  total = total + numeros[i];
}

// total es 50
```

### Construir strings:

```js
const nombres = ["Ana", "Carlos", "María"];
let saludo = "";

for (let i = 0; i < nombres.length; i++) {
  saludo = saludo + "Hola " + nombres[i] + ". ";
}

// saludo es "Hola Ana. Hola Carlos. Hola María. "
```

---

## Incrementos personalizados

No siempre tienes que incrementar de 1 en 1. Puedes usar cualquier incremento:

### Contar de 2 en 2:

```js
let pares = "";

for (let i = 0; i <= 10; i += 2) {
  pares = pares + i + " ";
}

// pares es "0 2 4 6 8 10 "
```

### Contar de 5 en 5:

```js
let multiplos = "";

for (let i = 5; i <= 25; i += 5) {
  multiplos = multiplos + i + " ";
}

// multiplos es "5 10 15 20 25 "
```

### Contar hacia atrás:

```js
let cuenta = "";

for (let i = 5; i > 0; i--) {
  cuenta = cuenta + i + " ";
}

// cuenta es "5 4 3 2 1 "
```

---

## Creando nuevos arrays

Puedes usar for para crear un nuevo array basado en otro:

### Duplicar valores:

```js
const numeros = [1, 2, 3, 4, 5];
const dobles = [];

for (let i = 0; i < numeros.length; i++) {
  dobles[i] = numeros[i] * 2;
}

// dobles es [2, 4, 6, 8, 10]
```

### Filtrar elementos:

```js
const edades = [15, 22, 17, 30, 12, 25];
const mayores = [];

for (let i = 0; i < edades.length; i++) {
  if (edades[i] >= 18) {
    mayores[mayores.length] = edades[i];
  }
}

// mayores es [22, 30, 25]
```

> ¿Por qué usamos `mayores[mayores.length]`?
>
> Porque `mayores.length` nos da la siguiente posición vacía en el array. Si mayores tiene 0 elementos, agregamos en la posición 0. Si tiene 1 elemento, agregamos en la posición 1, etc.

---

## Bucles for con condicionales

Puedes combinar for con if para procesar elementos selectivamente:

```js
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let sumaPares = 0;
let sumaImpares = 0;

for (let i = 0; i < numeros.length; i++) {
  if (numeros[i] % 2 === 0) {
    sumaPares = sumaPares + numeros[i];
  } else {
    sumaImpares = sumaImpares + numeros[i];
  }
}

// sumaPares es 30 (2+4+6+8+10)
// sumaImpares es 25 (1+3+5+7+9)
```

Contar elementos que cumplen una condición:

```js
const calificaciones = [85, 92, 78, 95, 88, 72, 90];
let aprobados = 0;

for (let i = 0; i < calificaciones.length; i++) {
  if (calificaciones[i] >= 80) {
    aprobados++;
  }
}

// aprobados es 5
```

---

## Trabajando con arrays de objetos

El bucle for es muy útil para recorrer arrays de objetos:

```js
const productos = [
  { nombre: "Laptop", precio: 1000 },
  { nombre: "Mouse", precio: 25 },
  { nombre: "Teclado", precio: 50 }
];

let total = 0;

for (let i = 0; i < productos.length; i++) {
  total = total + productos[i].precio;
}

// total es 1075
```

Encontrar un objeto específico:

```js
const personas = [
  { nombre: "Ana", edad: 25 },
  { nombre: "Carlos", edad: 30 },
  { nombre: "María", edad: 28 }
];

let nombreBuscado = "";

for (let i = 0; i < personas.length; i++) {
  if (personas[i].edad > 28) {
    nombreBuscado = personas[i].nombre;
  }
}

// nombreBuscado es "Carlos"
```

---

## Bucles for anidados

Puedes poner un bucle for dentro de otro. Esto es útil para trabajar con arrays multidimensionales:

```js
const matriz = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

let suma = 0;

for (let i = 0; i < matriz.length; i++) {
  for (let j = 0; j < matriz[i].length; j++) {
    suma = suma + matriz[i][j];
  }
}

// suma es 45 (suma de todos los números)
```

> ¿Cómo funciona?
>
> El bucle externo recorre las filas (cada array dentro del array principal).
> El bucle interno recorre los elementos de cada fila.

Otro ejemplo con patrones:

```js
let patron = "";

for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 3; j++) {
    patron = patron + `(${i},${j}) `;
  }
  patron = patron + "\n";
}

// patron es:
// "(1,1) (1,2) (1,3) 
//  (2,1) (2,2) (2,3) 
//  (3,1) (3,2) (3,3) "
```

---

## Rompiendo bucles con break

A veces quieres detener un bucle antes de que termine naturalmente. Para eso usas `break`:

```js
const numeros = [5, 12, 8, 15, 3, 20];
let encontrado = false;
let posicion = -1;

for (let i = 0; i < numeros.length; i++) {
  if (numeros[i] === 15) {
    encontrado = true;
    posicion = i;
    break;
  }
}

// encontrado es true
// posicion es 3
```

> ¿Qué hace break?
>
> Detiene el bucle inmediatamente, sin verificar más elementos.

---

## Saltando iteraciones con continue

`continue` salta a la siguiente iteración sin ejecutar el resto del código:

```js
let suma = 0;

for (let i = 1; i <= 10; i++) {
  if (i === 5) {
    continue;
  }
  suma = suma + i;
}

// suma es 50 (1+2+3+4+6+7+8+9+10, saltándose el 5)
```

Otro ejemplo:

```js
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let sumaPares = 0;

for (let i = 0; i < numeros.length; i++) {
  if (numeros[i] % 2 !== 0) {
    continue;
  }
  sumaPares = sumaPares + numeros[i];
}

// sumaPares es 30 (2+4+6+8+10)
```

---

## Ejemplos prácticos

### Ejemplo 1: Encontrar el máximo

```js
const numeros = [45, 23, 67, 12, 89, 34];
let maximo = numeros[0];

for (let i = 1; i < numeros.length; i++) {
  if (numeros[i] > maximo) {
    maximo = numeros[i];
  }
}

// maximo es 89
```

### Ejemplo 2: Calcular promedio

```js
const calificaciones = [85, 90, 78, 92, 88];
let suma = 0;

for (let i = 0; i < calificaciones.length; i++) {
  suma = suma + calificaciones[i];
}

const promedio = suma / calificaciones.length;

// promedio es 86.6
```

### Ejemplo 3: Invertir un array

```js
const original = [1, 2, 3, 4, 5];
const invertido = [];

for (let i = original.length - 1; i >= 0; i--) {
  invertido[invertido.length] = original[i];
}

// invertido es [5, 4, 3, 2, 1]
```

### Ejemplo 4: Contar vocales en un string

```js
const texto = "JavaScript es genial";
const vocales = ["a", "e", "i", "o", "u", "A", "E", "I", "O", "U"];
let contador = 0;

for (let i = 0; i < texto.length; i++) {
  for (let j = 0; j < vocales.length; j++) {
    if (texto[i] === vocales[j]) {
      contador++;
    }
  }
}

// contador es 7
```

### Ejemplo 5: Tabla de multiplicar

```js
const numero = 5;
let tabla = "";

for (let i = 1; i <= 10; i++) {
  const resultado = numero * i;
  tabla = tabla + `${numero} x ${i} = ${resultado}\n`;
}

// tabla contiene la tabla del 5
```

### Ejemplo 6: Calcular total de compra con descuento

```js
const carrito = [
  { producto: "Laptop", precio: 1000, cantidad: 1 },
  { producto: "Mouse", precio: 25, cantidad: 2 },
  { producto: "Teclado", precio: 50, cantidad: 1 }
];

let subtotal = 0;

for (let i = 0; i < carrito.length; i++) {
  subtotal = subtotal + (carrito[i].precio * carrito[i].cantidad);
}

const descuento = subtotal * 0.1;
const total = subtotal - descuento;

// subtotal es 1100
// descuento es 110
// total es 990
```

---

## For vs While: ¿Cuándo usar cada uno?

### Usa for cuando:
- Sabes cuántas veces quieres repetir algo
- Estás recorriendo un array
- Quieres mantener la inicialización, condición e incremento juntos

### Usa while cuando:
- No sabes cuántas veces se repetirá el bucle
- La condición es más compleja
- El incremento no es regular

---

## Resumen

- El bucle `for` organiza inicialización, condición e incremento en una línea
- Es perfecto para recorrer arrays: `for (let i = 0; i < array.length; i++)`
- Puedes incrementar o decrementar con cualquier valor
- `break` detiene el bucle completamente
- `continue` salta a la siguiente iteración
- Puedes anidar bucles for (for dentro de for)
- Es más compacto que while cuando sabes el número de iteraciones

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
let suma = 0;
for (let i = 0; i < 5; i++) {
  suma = suma + i;
}
// valor de suma
```

#### b)

```js
let resultado = "";
for (let i = 1; i <= 3; i++) {
  resultado = resultado + i;
}
// valor de resultado
```

#### c)

```js
const numeros = [10, 20, 30];
let total = 0;
for (let i = 0; i < numeros.length; i++) {
  total = total + numeros[i];
}
// valor de total
```

#### d)

```js
let contador = 0;
for (let i = 0; i < 10; i++) {
  if (i % 2 === 0) {
    contador++;
  }
}
// valor de contador
```

#### e)

```js
const nombres = ["Ana", "Luis", "María"];
let primeras = "";
for (let i = 0; i < nombres.length; i++) {
  primeras = primeras + nombres[i][0];
}
// valor de primeras
```

### 2. Encuentra los errores

Identifica y corrige los errores:

#### a)

```js
for (let i = 0 i < 5 i++) {
  // código
}
```

#### b)

```js
for (i = 0; i < 5; i++) {
  // código
}
```

#### c)

```js
const array = [1, 2, 3];
for (let i = 1; i <= array.length; i++) {
  const valor = array[i];
}
```

#### d)

```js
for (let i = 0; i < 5; i--) {
  // código
}
```

### 3. Convierte while a for

Reescribe estos bucles while como bucles for:

#### a)

```js
let i = 0;
while (i < 10) {
  i++;
}
```

#### b)

```js
const frutas = ["manzana", "pera", "uva"];
let i = 0;
while (i < frutas.length) {
  const fruta = frutas[i];
  i++;
}
```

#### c)

```js
let suma = 0;
let i = 1;
while (i <= 100) {
  suma = suma + i;
  i++;
}
```

### 4. Escribe bucles for

Para estos ejercicios, utiliza tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea un bucle for que sume todos los números del 1 al 50.

#### b)

Dado el array `[2, 4, 6, 8, 10]`, usa un bucle for para multiplicar todos los elementos y guardar el resultado.

#### c)

Dado el array `["JavaScript", "Python", "Java"]`, usa un bucle for para construir un string que los una con " - " entre cada uno.

#### d)

Usa un bucle for para crear un array con los primeros 15 múltiplos de 3.

#### e)

Dado el array `[5, 12, 8, 130, 44, 3]`, usa un bucle for para encontrar tanto el número mayor como el menor.

### 5. Problemas con arrays

#### a)

Dado el array `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`, crea dos nuevos arrays: uno con los números pares y otro con los impares.

#### b)

Dado el array de objetos:

```js
const estudiantes = [
  { nombre: "Ana", nota: 85 },
  { nombre: "Carlos", nota: 92 },
  { nombre: "María", nota: 78 },
  { nombre: "Pedro", nota: 95 }
];
```

Usa un bucle for para:
- Calcular el promedio de las notas
- Encontrar el nombre del estudiante con la nota más alta

#### c)

Crea un array con los números del 1 al 20. Luego usa un bucle for para crear un nuevo array donde cada número esté elevado al cuadrado.

#### d)

Dado el array `["hola", "mundo", "JavaScript", "es", "genial"]`, usa un bucle for para encontrar la palabra más larga.

#### e)

Crea dos arrays: `nombres = ["Ana", "Carlos", "María"]` y `edades = [25, 30, 28]`. Usa un bucle for para crear un array de objetos donde cada objeto tenga las propiedades nombre y edad.

### 6. Desafíos

#### a)

Usa bucles for anidados para crear una matriz (array de arrays) de 4x4 donde cada elemento sea la suma de sus índices. Ejemplo: posición [2][3] debe contener 5.

#### b)

Dado un array de números, usa un bucle for para crear un nuevo array que contenga solo los números que son mayores que el promedio del array original.

#### c)

Crea un bucle for que genere los primeros 15 números de la secuencia de Fibonacci en un array.

#### d)

Dado el array `[3, 1, 4, 1, 5, 9, 2, 6, 5, 3]`, usa un bucle for para encontrar cuántas veces aparece cada número. Guarda los resultados en variables separadas o en un objeto.



