# Funciones flecha

## Qué son las funciones flecha

Las funciones flecha (también conocidas como arrow functions) son una forma más corta de escribir funciones anónimas en JavaScript.

Mira la diferencia entre una función anónima tradicional y una función flecha:

Una función anónima tradicional:

```js
const suma = function(a, b) {
  return a + b;
};
```

Una función flecha:

```js
const suma = (a, b) => {
  return a + b;
};
```

> Vuelve a ver ambas funciones detenidamente.
>
> ¿Cuál es la diferencia entre las dos?

Fíjate que la función flecha utiliza el símbolo `=>` (que parece una flecha) en lugar de la palabra `function`. Esta es la característica principal que distingue a las funciones flecha de las funciones tradicionales.

Para llamar a la función, simplemente usas el nombre de la variable:

```js
suma(2, 3); // 5
```

## Sintaxis de las funciones flecha

Las funciones flecha tienen varias formas de escribirse dependiendo de la cantidad de parámetros y líneas de código que tengan.

### Con múltiples parámetros

Cuando la función tiene dos o más parámetros, se escriben entre paréntesis:

```js
const multiplicar = (a, b) => {
  return a * b;
};

multiplicar(4, 5); // 20
```

### Con un solo parámetro

Cuando la función tiene un solo parámetro, puedes omitir los paréntesis:

```js
const cuadrado = x => {
  return x * x;
};

cuadrado(5); // 25
```

> ¿Notaste que no usamos paréntesis alrededor de x?
>
> Esto es completamente válido cuando solo hay un parámetro.

### Sin parámetros

Cuando la función no tiene parámetros, debes usar paréntesis vacíos:

```js
const saludar = () => {
  return "¡Hola!";
};

saludar(); // "¡Hola!"
```

## Return implícito

Una de las características más útiles de las funciones flecha es el **return implícito**. Cuando la función tiene una sola línea que devuelve un valor, puedes omitir las llaves `{}` y la palabra `return`.

Mira estos ejemplos:

Función flecha con return explícito:

```js
const suma = (a, b) => {
  return a + b;
};
```

La misma función con return implícito:

```js
const suma = (a, b) => a + b;
```

> ¿Ves la diferencia?
>
> Hemos eliminado las llaves y la palabra return. La función ahora es mucho más corta.

Ambas funciones hacen exactamente lo mismo, pero la segunda es más concisa. El valor de `a + b` se devuelve automáticamente.

Veamos más ejemplos:

```js
const cuadrado = x => x * x;
const triple = n => n * 3;
const saludar = nombre => "Hola, " + nombre;

cuadrado(4); // 16
triple(5); // 15
saludar("Ana"); // "Hola, Ana"
```

> ¿Puedes identificar cuántos parámetros tiene cada función?
>
> ¿Todas usan return implícito?

---

## Funciones flecha en objetos

Al igual que las funciones anónimas, las funciones flecha se pueden usar como propiedades de objetos:

```js
const calculadora = {
  suma: (a, b) => a + b,
  resta: (a, b) => a - b,
  multiplicar: (a, b) => a * b,
  dividir: (a, b) => a / b
};

calculadora.suma(10, 5); // 15
calculadora.resta(10, 5); // 5
calculadora.multiplicar(10, 5); // 50
calculadora.dividir(10, 5); // 2
```

> ¿Cuántas propiedades tiene el objeto calculadora?
>
> ¿Todas las funciones usan return implícito?

En este ejemplo, cada propiedad del objeto calculadora contiene una función flecha con return implícito.

---

## Funciones flecha en arrays

También puedes almacenar funciones flecha dentro de un array:

```js
const operaciones = [
  (a, b) => a + b,
  (a, b) => a - b,
  (a, b) => a * b
];

operaciones[0](10, 5); // 15
operaciones[1](10, 5); // 5
operaciones[2](10, 5); // 50
```

> ¿Cuántas funciones hay en el array?
>
> ¿Cómo llamarías a la función que multiplica?

Cada elemento del array es una función flecha que podemos ejecutar usando su índice.

---

## Funciones flecha con múltiples líneas

Cuando tu función necesita más de una línea de código, debes usar llaves `{}` y el `return` explícito:

```js
const calcularPrecio = (precio, descuento) => {
  const precioConDescuento = precio - (precio * descuento / 100);
  const precioFinal = precioConDescuento * 1.16; // agregando IVA
  return precioFinal;
};

calcularPrecio(100, 20); // 92.8
```

> ¿Por qué esta función necesita llaves y return?
>
> ¿Cuántas líneas de código tiene dentro de la función?

Cuando la función tiene más de una línea, es necesario usar las llaves para delimitar el bloque de código y usar `return` para devolver el valor.

---

## Cuándo usar funciones flecha

Las funciones flecha son especialmente útiles en estos casos:

1. **Como callbacks**: cuando se pasan como argumentos a otras funciones (lo veremos en futuras lecciones)
2. **Operaciones simples**: cuando necesitas hacer operaciones rápidas y concisas
3. **Métodos de arrays**: como `map`, `filter`, `reduce` (lo veremos más adelante)

Ejemplo simple:

```js
const numeros = [1, 2, 3, 4, 5];
const dobles = numeros.map(n => n * 2);

console.log(dobles); // [2, 4, 6, 8, 10]
```

> No te preocupes si no entiendes completamente este ejemplo todavía.
>
> Lo importante es que veas cómo una función flecha puede hacer el código más limpio y fácil de leer.

---

## Ejercicios

### 1. Encuentra los errores

#### a)

```js
const multiplicar = a, b => a * b;

const resultado = multiplicar(3, 4);
```

#### b)

```js
const saludar = (nombre) => 
  const mensaje = "Hola " + nombre;
  return mensaje;
};
```

#### c)

```js
const dividir => (a, b) => a / b;

const resultado = dividir(10, 2);
```

### 2. Resuelve

#### a)

```js
const calcular = (x, y) => x * 2 + y;

const resultado = calcular(5, 3);
// valor de resultado
```

#### b)

```js
const operaciones = {
  sumar: (a, b) => a + b,
  restar: (a, b) => a - b
};

const x = operaciones.sumar(10, 5);
const y = operaciones.restar(10, 5);
const z = x * y;
// valor de x, y, z
```

#### c)

```js
const funciones = [
  x => x + 10,
  x => x * 2,
  x => x - 5
];

const resultado = funciones[2](funciones[0](funciones[1](3)));
// valor de resultado
```

### 3. Convierte a funciones flecha

Convierte las siguientes funciones a funciones flecha con return implícito cuando sea posible.

#### a)

```js
const restar = function(a, b) {
  return a - b;
};
```

#### b)

```js
const obtenerNombre = function() {
  return "María";
};
```

#### c)

```js
const calcularArea = function(ancho, alto) {
  const area = ancho * alto;
  return area;
};
```

### 4. Crea funciones flecha

Para estos ejercicios, utiliza vs-code o tu editor de código favorito. Toma una captura de pantalla de cada uno y compártela con tu instructor.

#### a)

Crea una función flecha llamada `esMayorDeEdad` que reciba una edad y devuelva `true` si es mayor o igual a 18, y `false` en caso contrario. Usa return implícito.

#### b)

Crea un objeto llamado `conversiones` que tenga las siguientes propiedades con funciones flecha:
- `celsiusAFahrenheit`: convierte grados Celsius a Fahrenheit (fórmula: `C * 9/5 + 32`)
- `fahrenheitACelsius`: convierte grados Fahrenheit a Celsius (fórmula: `(F - 32) * 5/9`)
- `metrosAPies`: convierte metros a pies (fórmula: `m * 3.28084`)

#### c)

Crea un array llamado `validaciones` que contenga tres funciones flecha:
- La primera debe verificar si un número es positivo
- La segunda debe verificar si un número es par
- La tercera debe verificar si un número es mayor que 100

Todas deben devolver `true` o `false`.

