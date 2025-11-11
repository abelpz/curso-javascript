# Tipos de datos

## Qué son los tipos de datos

En JavaScript, toda la información con la que trabajamos tiene un tipo. Los tipos de datos son las diferentes categorías de información que podemos usar en nuestro código.

Imagina que los tipos de datos son como diferentes tipos de objetos en la vida real: números, palabras, respuestas de verdadero o falso, listas de cosas, etc. Cada tipo tiene sus propias características y se usa para diferentes propósitos.

JavaScript tiene varios tipos de datos básicos que aprenderemos en esta lección.

---

## String (Texto)

El tipo de dato **string** se usa para representar texto. Pueden ser palabras, oraciones, párrafos o cualquier secuencia de caracteres.

Los strings siempre van entre comillas. Puedes usar comillas dobles `"`, comillas simples `'`, o comillas invertidas `` ` ``.

Mira estos ejemplos de strings:

```js
"Hola mundo"
'JavaScript'
"123"
'¡Bienvenido!'
"Me llamo Ana y tengo 25 años"
```

> ¿Notaste que "123" está entre comillas?
>
> Cuando un número está entre comillas, JavaScript lo trata como texto, no como número.

Todos estos son strings válidos:

```js
"a"
"JavaScript es divertido"
"12345"
"@#$%"
""
```

> ¿Puedes identificar cuál es un string vacío?

El último ejemplo `""` es un string vacío. No tiene ningún carácter dentro, pero sigue siendo un string.

### Verificando el tipo string

JavaScript tiene una herramienta llamada `typeof` que nos dice qué tipo de dato es algo. Observa:

```js
typeof "Hola"
// resultado: "string"

typeof 'JavaScript'
// resultado: "string"

typeof "123"
// resultado: "string"
```

> ¿Ves que todos devuelven "string"?
>
> Esto confirma que son datos de tipo texto.

---

## Number (Números)

El tipo de dato **number** se usa para representar números. Pueden ser números enteros o decimales, positivos o negativos.

Mira estos ejemplos de números:

```js
42
3.14
-10
0
1000000
-5.5
```

> ¿Cuál es la diferencia entre "42" y 42?

"42" (entre comillas) es un string, mientras que 42 (sin comillas) es un número. Aunque se vean parecidos, JavaScript los trata de forma completamente diferente.

Los números NO llevan comillas. Si les pones comillas, se convierten en strings.

### Operaciones con números

Los números se pueden usar en operaciones matemáticas:

```js
5 + 3
// resultado: 8

10 - 4
// resultado: 6

6 * 7
// resultado: 42

20 / 4
// resultado: 5

10 % 3
// resultado: 1
```

> ¿Sabes qué hace el operador %?
>
> Se llama módulo y devuelve el resto de una división. 10 dividido entre 3 es 3, y sobra 1.

### Verificando el tipo number

Usamos `typeof` para verificar que son números:

```js
typeof 42
// resultado: "number"

typeof 3.14
// resultado: "number"

typeof -10
// resultado: "number"
```

---

## Boolean (Verdadero o Falso)

El tipo de dato **boolean** solo tiene dos valores posibles: `true` (verdadero) o `false` (falso).

Los booleanos se usan para responder preguntas de sí o no, para verificar condiciones, o para tomar decisiones en el código.

```js
true
false
```

> ¿Eso es todo?
>
> Sí, los booleanos solo pueden ser true o false. Nada más.

Es importante escribirlos sin comillas. Si escribes `"true"` con comillas, eso es un string, no un booleano.

Compara:

```js
true      // boolean
"true"    // string

false     // boolean
"false"   // string
```

### Verificando el tipo boolean

```js
typeof true
// resultado: "boolean"

typeof false
// resultado: "boolean"

typeof "true"
// resultado: "string"
```

> ¿Ves la diferencia en el último ejemplo?
>
> "true" entre comillas es un string, no un boolean.

### Comparaciones que devuelven booleanos

Cuando comparamos cosas en JavaScript, el resultado es siempre un boolean:

```js
5 > 3
// resultado: true

10 < 8
// resultado: false

7 === 7
// resultado: true

4 !== 4
// resultado: false

10 >= 10
// resultado: true
```

> ¿Entiendes qué hace cada operador?
>
> `>` mayor que, `<` menor que, `===` igual a, `!==` diferente de, `>=` mayor o igual, `<=` menor o igual.

---

## Undefined (Indefinido)

El tipo **undefined** significa que algo no tiene valor asignado o no está definido todavía.

```js
undefined
```

Por ahora solo necesitas saber que existe. Lo usaremos más adelante.

```js
typeof undefined
// resultado: "undefined"
```

---

## Null (Nulo)

El tipo **null** representa la ausencia intencional de un valor. Es diferente de undefined.

```js
null
```

Mientras que `undefined` significa "no tiene valor", `null` significa "intencionalmente vacío o sin valor".

```js
typeof null
// resultado: "object"
```

> ¿Por qué typeof null devuelve "object"?
>
> Esto es un error histórico de JavaScript que se mantiene por compatibilidad. Solo recuerda que null es su propio tipo.

---

## Array (Lista)

Un **array** es una lista ordenada de valores. Los arrays se escriben entre corchetes `[]` y los valores se separan con comas.

```js
[1, 2, 3, 4, 5]
["manzana", "pera", "naranja"]
[true, false, true]
[10, "texto", true, 3.14]
[]
```

> ¿Notaste el último ejemplo?
>
> Los arrays pueden estar vacíos.

Los arrays pueden contener cualquier tipo de dato, incluso mezclados:

```js
[1, "dos", 3, "cuatro", true]
```

Cada elemento en un array tiene una posición que comienza desde 0:

```js
// En el array: ["lunes", "martes", "miércoles"]
// Posición 0: "lunes"
// Posición 1: "martes"  
// Posición 2: "miércoles"
```

> ¿Por qué empieza en 0 y no en 1?
>
> Es una convención en programación. La primera posición es 0, la segunda es 1, y así sucesivamente.

### Verificando el tipo array

```js
typeof [1, 2, 3]
// resultado: "object"
```

Los arrays técnicamente son objetos en JavaScript, por eso `typeof` devuelve "object".

---

## Object (Objeto)

Un **object** es una colección de datos relacionados que normalmente se usa para describir cosas. Los objetos se escriben entre llaves `{}` y contienen propiedades, que son pares de nombre y valor.

```js
{
  nombre: "Ana",
  edad: 25,
  estudiante: true
}
```

Cada par se escribe como `nombre: valor` y se separa con comas.

```js
{
  titulo: "JavaScript básico",
  paginas: 200,
  disponible: true
}
```

> ¿Ves cómo cada propiedad describe algo del objeto?
>
> Los objetos son perfectos para agrupar información relacionada.

Un objeto puede estar vacío:

```js
{}
```

### Verificando el tipo object

```js
typeof { nombre: "Ana", edad: 25 }
// resultado: "object"
```

---

## Resumen de tipos de datos

Aquí está un resumen rápido de todos los tipos:

| Tipo | Ejemplo | typeof devuelve |
|------|---------|-----------------|
| String | `"Hola"` | `"string"` |
| Number | `42` | `"number"` |
| Boolean | `true` | `"boolean"` |
| Undefined | `undefined` | `"undefined"` |
| Null | `null` | `"object"` |
| Array | `[1, 2, 3]` | `"object"` |
| Object | `{ nombre: "Ana" }` | `"object"` |

---

## Ejercicios

### 1. Identifica el tipo

¿Qué tipo de dato es cada uno de estos? Usa `typeof` si no estás seguro.

#### a)

```js
"JavaScript"
```

#### b)

```js
100
```

#### c)

```js
true
```

#### d)

```js
"true"
```

#### e)

```js
[1, 2, 3, 4]
```

#### f)

```js
3.14
```

#### g)

```js
"123"
```

#### h)

```js
false
```

### 2. ¿Verdadero o falso?

Determina si estas afirmaciones son verdaderas o falsas:

#### a)

"50" y 50 son el mismo tipo de dato.

#### b)

Los strings pueden estar vacíos (`""`).

#### c)

Los booleanos pueden ser `true`, `false`, o `maybe`.

#### d)

Un array puede contener diferentes tipos de datos al mismo tiempo.

#### e)

`typeof null` devuelve `"null"`.

### 3. Encuentra los errores

Identifica qué está mal en cada ejemplo:

#### a)

```js
typeof 42
// resultado esperado: "string"
```

#### b)

```js
typeof true
// resultado esperado: "boolean"
```

#### c)

```js
typeof "false"
// resultado esperado: "boolean"
```

### 4. Crea ejemplos

Para estos ejercicios, utiliza la consola de tu navegador o tu editor de código favorito.

#### a)

Escribe 5 ejemplos diferentes de strings. Incluye un string vacío, un string con números, y un string con símbolos especiales.

#### b)

Escribe 5 ejemplos diferentes de numbers. Incluye números enteros, decimales, positivos y negativos.

#### c)

Crea 3 arrays: uno que contenga solo números, otro que contenga solo strings, y otro que mezcle diferentes tipos de datos.

#### d)

Crea 2 objetos diferentes. El primero debe describir un libro (título, autor, páginas). El segundo debe describir una persona (nombre, edad, ciudad).

#### e)

Usa `typeof` para verificar el tipo de al menos 10 valores diferentes que tú elijas. Anota los resultados.

