# Variables

## Qué son las variables

Las variables son como cajas o contenedores donde podemos guardar información. Cada variable tiene un nombre y puede almacenar cualquier tipo de dato que ya conoces: strings, números, booleanos, arrays, objetos, etc.

Imagina que tienes una caja y le pones una etiqueta con un nombre. Dentro de esa caja puedes guardar algo: un número, un texto, una lista, etc. Cada vez que necesites ese valor, simplemente buscas la caja por su nombre.

En la lección anterior trabajamos directamente con los valores:

```js
"Hola mundo"
42
true
```

Pero en programas reales, necesitamos guardar estos valores en variables para poder usarlos después.

---

## Cómo crear variables

En JavaScript existen tres formas de crear variables: `const`, `let` y `var`. Nos enfocaremos en `const` y `let`, que son las formas modernas.

### Usando const

La palabra `const` se usa para crear variables cuyo valor **no va a cambiar**. Una vez que le asignas un valor, ese valor permanece constante.

```js
const nombre = "Ana";
const edad = 25;
const esEstudiante = true;
```

> ¿Ves cómo se escribe?
>
> Primero va la palabra `const`, luego el nombre de la variable, después el símbolo `=`, y finalmente el valor.

La estructura es siempre:

```
const nombreDeVariable = valor;
```

Más ejemplos:

```js
const ciudad = "Madrid";
const temperatura = 22;
const disponible = false;
const puntos = 100;
```

### Usando let

La palabra `let` se usa para crear variables cuyo valor **puede cambiar** durante la ejecución del programa.

```js
let contador = 0;
let nombre = "Carlos";
let activo = true;
```

La estructura es igual que `const`:

```
let nombreDeVariable = valor;
```

La diferencia está en que con `let` puedes cambiar el valor después:

```js
let puntos = 10;
puntos = 20;
puntos = 30;
```

> ¿Notaste algo importante?
>
> Cuando cambias el valor, ya no usas `let` de nuevo, solo escribes el nombre de la variable y el nuevo valor.

Con `const` esto no es posible:

```js
const puntos = 10;
puntos = 20; // ¡Error! No puedes cambiar una const
```

---

## Cuándo usar const y cuándo usar let

Esta es una regla simple que te ayudará mucho:

**Usa `const` por defecto**. Solo usa `let` cuando sepas que el valor va a cambiar.

Ejemplos de cuándo usar `const`:

```js
const nombre = "María";
const PI = 3.14159;
const diasEnSemana = 7;
const colores = ["rojo", "azul", "verde"];
```

> ¿Por qué estos deberían ser const?
>
> Porque son valores que no necesitan cambiar durante el programa.

Ejemplos de cuándo usar `let`:

```js
let contador = 0;
let intentos = 3;
let mensaje = "Bienvenido";
```

> ¿Por qué estos deberían ser let?
>
> Porque probablemente necesitarás cambiar estos valores: el contador aumentará, los intentos disminuirán, el mensaje cambiará.

---

## Usando variables

Una vez que creas una variable, puedes usarla en cualquier parte de tu código simplemente escribiendo su nombre.

```js
const nombre = "Pedro";
const edad = 30;

typeof nombre; // "string"
typeof edad; // "number"
```

Puedes usar variables en operaciones:

```js
const precio = 100;
const descuento = 20;
const precioFinal = precio - descuento;
```

> ¿Cuál es el valor de precioFinal?
>
> Es 80, porque 100 - 20 = 80.

Puedes combinar variables con otros valores:

```js
const nombre = "Ana";
const saludo = "Hola, " + nombre;
```

> ¿Cuál es el valor de saludo?
>
> Es "Hola, Ana", porque combinamos el string "Hola, " con el valor de la variable nombre.

---

## Nombres de variables

Los nombres de variables en JavaScript deben seguir ciertas reglas:

### Reglas obligatorias:

1. Pueden contener letras, números, `$` y `_`
2. NO pueden empezar con un número
3. NO pueden contener espacios
4. NO pueden usar palabras reservadas de JavaScript (como `const`, `let`, `if`, `for`, etc.)

Nombres válidos:

```js
const nombre = "Ana";
const edad2 = 25;
const precio_total = 100;
const $elemento = "div";
const _privado = true;
const nombreCompleto = "Ana García";
```

Nombres NO válidos:

```js
const 2edad = 25; // ¡Error! Empieza con número
const precio total = 100; // ¡Error! Tiene espacio
const const = "valor"; // ¡Error! 'const' es palabra reservada
```

### Convención camelCase:

En JavaScript usamos una convención llamada **camelCase** para nombres de variables con varias palabras.

La primera palabra va en minúscula, y las siguientes palabras empiezan con mayúscula:

```js
const nombreCompleto = "Ana García";
const edadDelUsuario = 25;
const precioConDescuento = 80;
const esMayorDeEdad = true;
```

> ¿Ves cómo se forma el nombre?
>
> Es como una joroba de camello: nombreCompleto, edadDelUsuario.

---

## Variables con diferentes tipos de datos

Las variables pueden almacenar cualquier tipo de dato.

### Variables con strings:

```js
const nombre = "Carlos";
const apellido = "Rodríguez";
const ciudad = "Barcelona";
const mensaje = "¡Bienvenido!";
```

### Variables con números:

```js
const edad = 28;
const precio = 99.99;
const cantidad = 5;
const temperatura = -3;
```

### Variables con booleanos:

```js
const activo = true;
const disponible = false;
const esMayorDeEdad = true;
const tieneDescuento = false;
```

### Variables con arrays:

```js
const colores = ["rojo", "verde", "azul"];
const numeros = [1, 2, 3, 4, 5];
const mixto = [10, "texto", true, 3.14];
const vacio = [];
```

### Variables con objetos:

```js
const persona = {
  nombre: "Ana",
  edad: 25,
  ciudad: "Madrid"
};

const libro = {
  titulo: "JavaScript para todos",
  autor: "María López",
  paginas: 300
};
```

---

## Cambiar el valor de las variables let

Como vimos antes, las variables creadas con `let` pueden cambiar su valor.

```js
let contador = 0;
contador = 1;
contador = 2;
contador = 3;
```

Puedes cambiar el valor usando el valor anterior:

```js
let puntos = 10;
puntos = puntos + 5; // ahora puntos es 15
puntos = puntos * 2; // ahora puntos es 30
```

> ¿Entiendes qué pasa aquí?
>
> En la segunda línea, tomamos el valor actual de puntos (10), le sumamos 5, y guardamos el resultado (15) de vuelta en puntos.

También puedes cambiar el tipo de dato completamente:

```js
let dato = 42;
dato = "texto";
dato = true;
```

Aunque esto es técnicamente posible, no es una buena práctica. Generalmente queremos que una variable mantenga el mismo tipo de dato.

---

## Variables sin valor inicial

Puedes crear una variable con `let` sin darle un valor inicial:

```js
let nombre;
let edad;
let activo;
```

> ¿Qué valor tienen estas variables?
>
> Tienen el valor `undefined`, porque no les hemos asignado nada todavía.

Luego puedes asignarles un valor:

```js
let nombre;
nombre = "Pedro";

let edad;
edad = 30;
```

Con `const` esto NO es posible. Debes asignar el valor inmediatamente:

```js
const nombre = "Pedro"; // ✓ Correcto
const edad; // ✗ Error: const debe tener valor inicial
```

---

## Sobre var (no lo uses)

Existe una tercera forma de crear variables llamada `var`, pero es antigua y tiene problemas. Siempre usa `const` o `let`.

```js
var nombre = "Juan"; // ✗ No hagas esto
const nombre = "Juan"; // ✓ Haz esto
```

Solo necesitas saber que `var` existe porque lo verás en código antiguo, pero tú debes usar `const` y `let`.

---

## Resumen

| Palabra clave | ¿Puede cambiar? | ¿Necesita valor inicial? | ¿Cuándo usarla? |
|---------------|-----------------|---------------------------|-----------------|
| `const` | No | Sí | Por defecto, para valores constantes |
| `let` | Sí | No | Cuando el valor cambiará |
| `var` | Sí | No | No la uses (antigua) |

---

## Ejercicios

### 1. Encuentra los errores

Identifica qué está mal en cada ejemplo:

#### a)

```js
const nombre = "Ana";
nombre = "María";
```

#### b)

```js
let edad;
const ciudad;
```

#### c)

```js
const 1numero = 10;
```

#### d)

```js
const precio total = 100;
```

#### e)

```js
let mensaje = "Hola";
let mensaje = "Adiós";
```

### 2. ¿const o let?

Decide si cada variable debería ser `const` o `let`:

#### a)

El nombre de un usuario en un sistema (no cambia después del login).

#### b)

Un contador que aumenta cada vez que alguien hace clic.

#### c)

El valor de PI (3.14159).

#### d)

La edad actual de una persona en un programa que simula el paso del tiempo.

#### e)

El título de una página web.

### 3. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
let x = 10;
x = x + 5;
x = x * 2;
// valor de x
```

#### b)

```js
const nombre = "Juan";
const apellido = "Pérez";
const nombreCompleto = nombre + " " + apellido;
// valor de nombreCompleto
```

#### c)

```js
let contador = 0;
contador = contador + 1;
contador = contador + 1;
contador = contador + 1;
// valor de contador
```

#### d)

```js
const precio = 100;
const descuento = 25;
const total = precio - descuento;
// valor de total
```

### 4. Crea variables

Para estos ejercicios, utiliza tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea 5 variables usando `const`: tu nombre, edad, ciudad, si eres estudiante, y tu comida favorita.

#### b)

Crea 3 variables usando `let`: un contador que empiece en 0, una temperatura que empiece en 20, y un mensaje que diga "Inicio". Luego cambia el valor de cada una al menos una vez.

#### c)

Crea una variable con un array que contenga los días de la semana. Luego crea otra variable con un objeto que describa tu película favorita (título, director, año, duración).

#### d)

Crea 5 pares de variables donde combines valores. Por ejemplo: `nombre` y `apellido` que se combinen en `nombreCompleto`, o `precio` y `cantidad` que se multipliquen en `total`.

#### e)

Intenta crear una variable `const`, y luego intenta cambiarle el valor. ¿Qué error te muestra JavaScript? Escribe el mensaje de error que ves.

