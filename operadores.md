# Operadores

## Qué son los operadores

Los operadores son símbolos especiales que nos permiten realizar operaciones con valores y variables. Piensa en ellos como herramientas que transforman, comparan o combinan datos.

Ya has visto algunos operadores en lecciones anteriores:

```js
const suma = 5 + 3; // El operador +
const edad = 25; // El operador =
```

En esta lección aprenderemos todos los operadores importantes que necesitas conocer en JavaScript.

---

## Operadores aritméticos

Los operadores aritméticos nos permiten hacer matemáticas básicas.

### Suma (+)

Suma dos números:

```js
const resultado = 5 + 3;
// resultado es 8

const precio = 100;
const impuesto = 16;
const total = precio + impuesto;
// total es 116
```

### Resta (-)

Resta el segundo número del primero:

```js
const resultado = 10 - 4;
// resultado es 6

const precioOriginal = 100;
const descuento = 20;
const precioFinal = precioOriginal - descuento;
// precioFinal es 80
```

### Multiplicación (*)

Multiplica dos números:

```js
const resultado = 6 * 7;
// resultado es 42

const precio = 25;
const cantidad = 4;
const total = precio * cantidad;
// total es 100
```

### División (/)

Divide el primer número entre el segundo:

```js
const resultado = 20 / 4;
// resultado es 5

const total = 100;
const personas = 4;
const porPersona = total / personas;
// porPersona es 25
```

### Módulo (%)

Devuelve el resto de una división:

```js
const resultado = 10 % 3;
// resultado es 1 (porque 10 ÷ 3 = 3 y sobra 1)

const numero = 17;
const resto = numero % 5;
// resto es 2 (porque 17 ÷ 5 = 3 y sobra 2)
```

> ¿Para qué sirve el módulo?
>
> Es muy útil para saber si un número es par o impar: si `numero % 2` es 0, el número es par.

### Exponenciación (**)

Eleva un número a una potencia:

```js
const resultado = 2 ** 3;
// resultado es 8 (2 × 2 × 2)

const base = 5;
const exponente = 2;
const potencia = base ** exponente;
// potencia es 25 (5 × 5)
```

---

## Operador de asignación (=)

El operador `=` asigna un valor a una variable:

```js
const nombre = "Ana";
let edad = 25;
let puntos = 0;
```

> ¿Recuerdas esto?
>
> Ya lo has usado en la lección de variables. El `=` NO significa "igual a", significa "asignar".

---

## Operadores de asignación combinados

Estos operadores combinan una operación aritmética con la asignación.

### Suma y asigna (+=)

```js
let puntos = 10;
puntos += 5; // Es lo mismo que: puntos = puntos + 5
// puntos ahora es 15

puntos += 3;
// puntos ahora es 18
```

### Resta y asigna (-=)

```js
let vidas = 3;
vidas -= 1; // Es lo mismo que: vidas = vidas - 1
// vidas ahora es 2
```

### Multiplica y asigna (*=)

```js
let cantidad = 5;
cantidad *= 2; // Es lo mismo que: cantidad = cantidad * 2
// cantidad ahora es 10
```

### Divide y asigna (/=)

```js
let numero = 100;
numero /= 4; // Es lo mismo que: numero = numero / 4
// numero ahora es 25
```

> ¿Ves el patrón?
>
> Todos estos operadores hacen una operación y guardan el resultado en la misma variable.

---

## Operadores de incremento y decremento

Estos operadores aumentan o disminuyen un número en 1.

### Incremento (++)

Aumenta el valor en 1:

```js
let contador = 5;
contador++;
// contador ahora es 6

contador++;
// contador ahora es 7
```

Es equivalente a:

```js
contador = contador + 1;
// o
contador += 1;
```

### Decremento (--)

Disminuye el valor en 1:

```js
let vidas = 3;
vidas--;
// vidas ahora es 2

vidas--;
// vidas ahora es 1
```

> ¿Dónde se usan más estos operadores?
>
> En contadores, temporizadores, vidas en juegos, intentos restantes, etc.

---

## Operadores de comparación

Los operadores de comparación comparan dos valores y devuelven `true` o `false`.

### Igual a (===)

Verifica si dos valores son exactamente iguales:

```js
const resultado = 5 === 5;
// resultado es true

const edad = 18;
const esMayorDeEdad = edad === 18;
// esMayorDeEdad es true

const nombre = "Ana";
const esAna = nombre === "Pedro";
// esAna es false
```

### Diferente de (!==)

Verifica si dos valores son diferentes:

```js
const resultado = 5 !== 3;
// resultado es true

const password = "1234";
const esIncorrecto = password !== "1234";
// esIncorrecto es false
```

### Mayor que (>)

```js
const resultado = 10 > 5;
// resultado es true

const edad = 20;
const esMayor = edad > 18;
// esMayor es true
```

### Menor que (<)

```js
const resultado = 5 < 10;
// resultado es true

const temperatura = 15;
const esFrio = temperatura < 20;
// esFrio es true
```

### Mayor o igual que (>=)

```js
const resultado = 10 >= 10;
// resultado es true

const edad = 18;
const puedeVotar = edad >= 18;
// puedeVotar es true
```

### Menor o igual que (<=)

```js
const resultado = 5 <= 10;
// resultado es true

const puntos = 50;
const necesitaMas = puntos <= 100;
// necesitaMas es true
```

> ¿Cuál es la diferencia entre > y >=?
>
> El `>` es estrictamente mayor. El `>=` incluye también el caso de igualdad.

### Importante: == vs ===

Existe también `==` y `!=`, pero **siempre debes usar `===` y `!==`**.

```js
5 == "5"   // true (no es estricto, convierte tipos)
5 === "5"  // false (estricto, compara tipo y valor)
```

> ¿Por qué usar ===?
>
> Porque `===` compara tanto el valor como el tipo de dato, evitando errores inesperados.

---

## Operadores lógicos

Los operadores lógicos trabajan con valores booleanos (true/false).

### AND lógico (&&)

Devuelve `true` solo si **ambas** condiciones son verdaderas:

```js
const resultado = true && true;
// resultado es true

const resultado2 = true && false;
// resultado2 es false

const edad = 20;
const tieneLicencia = true;
const puedeConducir = edad >= 18 && tieneLicencia;
// puedeConducir es true (ambas condiciones son verdaderas)
```

Tabla de verdad del AND (&&):

```js
true && true    // true
true && false   // false
false && true   // false
false && false  // false
```

> ¿Cuándo es verdadero el AND?
>
> Solo cuando AMBOS lados son true.

### OR lógico (||)

Devuelve `true` si **al menos una** condición es verdadera:

```js
const resultado = true || false;
// resultado es true

const resultado2 = false || false;
// resultado2 es false

const esFinDeSemana = true;
const esFeriado = false;
const puedeDescansar = esFinDeSemana || esFeriado;
// puedeDescansar es true (al menos una condición es verdadera)
```

Tabla de verdad del OR (||):

```js
true || true    // true
true || false   // true
false || true   // true
false || false  // false
```

> ¿Cuándo es verdadero el OR?
>
> Cuando AL MENOS UNO de los lados es true.

### NOT lógico (!)

Invierte un valor booleano:

```js
const resultado = !true;
// resultado es false

const resultado2 = !false;
// resultado2 es true

const lloviendo = false;
const noLlueve = !lloviendo;
// noLlueve es true
```

Ejemplos prácticos:

```js
const edad = 15;
const esMayorDeEdad = edad >= 18;
// esMayorDeEdad es false

const esMenorDeEdad = !esMayorDeEdad;
// esMenorDeEdad es true
```

> ¿Qué hace el operador !?
>
> Convierte true en false, y false en true. Es como decir "lo contrario de".

---

## Operador de concatenación

El operador `+` también se usa para unir strings:

```js
const nombre = "Ana";
const apellido = "García";
const nombreCompleto = nombre + " " + apellido;
// nombreCompleto es "Ana García"

const saludo = "Hola, " + nombre + "!";
// saludo es "Hola, Ana!"
```

> ¿Por qué + sirve para números y texto?
>
> JavaScript es inteligente: si usas + con números, suma. Si lo usas con strings, concatena (une).

Ten cuidado con mezclar números y strings:

```js
const resultado1 = 5 + 3;
// resultado1 es 8 (suma de números)

const resultado2 = "5" + "3";
// resultado2 es "53" (concatenación de strings)

const resultado3 = 5 + "3";
// resultado3 es "53" (JavaScript convierte 5 a string)
```

---

## Orden de operaciones

JavaScript sigue el orden matemático tradicional:

1. Paréntesis `()`
2. Exponenciación `**`
3. Multiplicación, División, Módulo `* / %`
4. Suma y Resta `+ -`

Ejemplos:

```js
const resultado = 5 + 3 * 2;
// resultado es 11, no 16 (primero multiplica, luego suma)

const resultado2 = (5 + 3) * 2;
// resultado2 es 16 (primero los paréntesis)

const resultado3 = 10 + 5 * 2 - 3;
// resultado3 es 17 (10 + 10 - 3)
```

> ¿Cómo recordar el orden?
>
> Usa paréntesis cuando tengas duda. Hacen el código más claro.

---

## Combinando operadores

Puedes combinar diferentes operadores en una sola expresión:

```js
const precio = 100;
const descuento = 20;
const cantidad = 3;

const total = (precio - descuento) * cantidad;
// total es 240

const edad = 25;
const tieneLicencia = true;
const tieneAuto = false;

const puedeViajar = edad >= 18 && (tieneLicencia || tieneAuto);
// puedeViajar es true
```

---

## Resumen de operadores

### Aritméticos:
- `+` suma
- `-` resta
- `*` multiplicación
- `/` división
- `%` módulo
- `**` exponenciación

### Asignación:
- `=` asignar
- `+=` sumar y asignar
- `-=` restar y asignar
- `*=` multiplicar y asignar
- `/=` dividir y asignar
- `++` incrementar en 1
- `--` decrementar en 1

### Comparación:
- `===` igual a
- `!==` diferente de
- `>` mayor que
- `<` menor que
- `>=` mayor o igual
- `<=` menor o igual

### Lógicos:
- `&&` AND (y)
- `||` OR (o)
- `!` NOT (no)

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
let x = 10;
x += 5;
x *= 2;
// valor de x
```

#### b)

```js
const a = 15;
const b = 4;
const resultado = a % b;
// valor de resultado
```

#### c)

```js
let contador = 0;
contador++;
contador++;
contador++;
// valor de contador
```

#### d)

```js
const precio = 100;
const descuento = 25;
const cantidad = 2;
const total = (precio - descuento) * cantidad;
// valor de total
```

#### e)

```js
const edad = 20;
const tieneLicencia = false;
const resultado = edad >= 18 && tieneLicencia;
// valor de resultado
```

#### f)

```js
const a = true;
const b = false;
const c = a || b && !b;
// valor de c
```

### 2. Operaciones básicas

Escribe expresiones para resolver estos problemas:

#### a)

Tienes 100 puntos y ganas 50 más. Luego pierdes 30. ¿Cuántos puntos tienes?

#### b)

Un producto cuesta 250 pesos. Tiene un descuento del 20%. ¿Cuál es el precio final?
(Pista: 20% de 250 es 250 * 0.20)

#### c)

Tienes 17 caramelos y quieres repartirlos entre 5 niños. ¿Cuántos le tocan a cada uno y cuántos sobran?
(Pista: usa división y módulo)

### 3. Comparaciones

Determina si cada expresión es `true` o `false`:

#### a)

```js
10 > 5
```

#### b)

```js
15 === "15"
```

#### c)

```js
20 >= 20
```

#### d)

```js
"Ana" !== "Pedro"
```

#### e)

```js
5 < 3
```

### 4. Operadores lógicos

Determina si cada expresión es `true` o `false`:

#### a)

```js
true && true
```

#### b)

```js
true && false
```

#### c)

```js
true || false
```

#### d)

```js
false || false
```

#### e)

```js
!true
```

#### f)

```js
!(5 > 3)
```

#### g)

```js
(10 > 5) && (3 < 7)
```

#### h)

```js
(10 < 5) || (3 < 7)
```

### 5. Encuentra los errores

Identifica y corrige los errores en estos ejemplos:

#### a)

```js
const resultado = 5 = 3 + 2;
```

#### b)

```js
let x = 10;
x ++ 5;
```

#### c)

```js
const esMayor = edad => 18;
```

### 6. Ejercicios prácticos

Para estos ejercicios, usa tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea variables para representar el precio de un producto (100), la cantidad a comprar (3), y el descuento en porcentaje (15). Calcula el total a pagar.

#### b)

Crea una variable `edad` con tu edad. Luego crea variables booleanas que verifiquen si:
- Eres mayor de edad (>= 18)
- Eres menor de 30
- Estás entre 18 y 30 (usa operadores lógicos)

#### c)

Crea un contador que empiece en 0. Increméntalo 5 veces usando `++`. Luego multiplícalo por 2 usando `*=`.

#### d)

Crea dos variables: `nombre` y `apellido`. Úsalas para crear una tercera variable `nombreCompleto` que los combine con un espacio en medio. Luego crea `saludo` que diga "Hola, [nombreCompleto]!".

#### e)

Experimenta con el operador módulo. Crea una variable con diferentes números y verifica cuáles son pares (número % 2 === 0) y cuáles son impares.

