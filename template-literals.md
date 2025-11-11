# Template Literals

## Qué son los template literals

Los template literals (también llamados template strings) son una forma moderna y más cómoda de trabajar con strings en JavaScript. Nos permiten crear strings de una manera más clara y legible.

En la lección de operadores viste cómo concatenar strings:

```js
const nombre = "Ana";
const edad = 25;
const mensaje = "Hola, me llamo " + nombre + " y tengo " + edad + " años.";
```

Con template literals, esto se vuelve mucho más simple y fácil de leer.

---

## Sintaxis básica

Los template literals usan **comillas invertidas** (backticks) `` ` `` en lugar de comillas simples `'` o dobles `"`.

```js
const mensaje = `Hola mundo`;
```

> ¿Dónde está la tecla de comillas invertidas?
>
> En la mayoría de teclados está a la izquierda del número 1, junto a la tecla Esc. En algunos teclados en español, necesitas presionar Alt Gr + la tecla junto al número 1.

Puedes usar template literals como cualquier string normal:

```js
const saludo = `Hola`;
const despedida = `Adiós`;
const vacio = ``;
```

---

## Interpolación de variables

La característica más útil de los template literals es la **interpolación**: insertar variables directamente dentro del string usando `${nombreVariable}`.

Compara estas dos formas:

### Con concatenación (forma antigua):

```js
const nombre = "Carlos";
const edad = 30;
const mensaje = "Hola, me llamo " + nombre + " y tengo " + edad + " años.";
```

### Con template literals (forma moderna):

```js
const nombre = "Carlos";
const edad = 30;
const mensaje = `Hola, me llamo ${nombre} y tengo ${edad} años.`;
```

> ¿Ves la diferencia?
>
> No necesitas cerrar y abrir strings con el operador +. Simplemente escribes `${variable}` donde quieres que aparezca el valor.

Más ejemplos:

```js
const producto = "Laptop";
const precio = 15000;
const stock = 5;

const info = `El producto ${producto} cuesta $${precio} y hay ${stock} unidades disponibles.`;
// info es: "El producto Laptop cuesta $15000 y hay 5 unidades disponibles."
```

```js
const ciudad = "Madrid";
const temperatura = 22;

const clima = `Hoy en ${ciudad} hace ${temperatura} grados.`;
// clima es: "Hoy en Madrid hace 22 grados."
```

---

## Expresiones dentro de template literals

Puedes poner cualquier expresión de JavaScript dentro de `${}`, no solo variables.

### Operaciones matemáticas:

```js
const precio = 100;
const descuento = 20;

const mensaje = `El precio final es $${precio - descuento}`;
// mensaje es: "El precio final es $80"
```

```js
const cantidad = 5;
const precioUnitario = 25;

const total = `Total: $${cantidad * precioUnitario}`;
// total es: "Total: $125"
```

### Llamadas a métodos:

```js
const nombre = "ana garcía";

const saludo = `Hola ${nombre.toUpperCase()}!`;
// saludo es: "Hola ANA GARCÍA!"
```

### Comparaciones:

```js
const edad = 20;

const mensaje = `¿Es mayor de edad? ${edad >= 18}`;
// mensaje es: "¿Es mayor de edad? true"
```

### Operador ternario (lo veremos más adelante):

```js
const edad = 15;

const mensaje = `Eres ${edad >= 18 ? "mayor" : "menor"} de edad`;
// mensaje es: "Eres menor de edad"
```

> ¿Entiendes el poder de ${}?
>
> Puedes ejecutar cualquier código JavaScript válido dentro de las llaves.

---

## Strings multilínea

Una ventaja enorme de los template literals es que puedes crear strings de varias líneas sin necesidad de concatenar o usar caracteres especiales.

### Con strings tradicionales (complicado):

```js
const poema = "Roses are red,\n" +
              "Violets are blue,\n" +
              "JavaScript is awesome,\n" +
              "And so are you!";
```

> ¿Qué es \n?
>
> Es un carácter especial que representa un salto de línea.

### Con template literals (simple):

```js
const poema = `Roses are red,
Violets are blue,
JavaScript is awesome,
And so are you!`;
```

> ¿Ves qué fácil?
>
> Simplemente presionas Enter donde quieres un salto de línea.

Más ejemplos:

```js
const lista = `Lista de compras:
- Manzanas
- Pan
- Leche
- Huevos`;
```

```js
const carta = `Estimado cliente,

Gracias por su compra.

Atentamente,
El equipo`;
```

---

## Combinando interpolación y multilínea

Puedes usar ambas características juntas:

```js
const nombre = "Ana";
const producto = "Laptop";
const precio = 15000;

const mensaje = `Hola ${nombre},

Tu pedido de ${producto} ha sido confirmado.
Total a pagar: $${precio}

Gracias por tu compra!`;
```

```js
const usuario = "Carlos";
const puntos = 150;
const nivel = 5;

const estadisticas = `=== Perfil de Usuario ===
Nombre: ${usuario}
Puntos: ${puntos}
Nivel: ${nivel}
Siguiente nivel: ${puntos + 50} puntos`;
```

---

## Template literals vs concatenación

Veamos una comparación lado a lado:

### Ejemplo 1: Mensaje simple

```js
// Concatenación
const nombre = "María";
const saludo = "Hola, " + nombre + "!";

// Template literal
const saludo = `Hola, ${nombre}!`;
```

### Ejemplo 2: Múltiples variables

```js
// Concatenación
const nombre = "Pedro";
const edad = 28;
const ciudad = "Barcelona";
const mensaje = nombre + " tiene " + edad + " años y vive en " + ciudad + ".";

// Template literal
const mensaje = `${nombre} tiene ${edad} años y vive en ${ciudad}.`;
```

### Ejemplo 3: Con operaciones

```js
// Concatenación
const precio = 100;
const cantidad = 3;
const mensaje = "Total: $" + (precio * cantidad);

// Template literal
const mensaje = `Total: $${precio * cantidad}`;
```

> ¿Cuál prefieres usar?
>
> Los template literals son más limpios, legibles y menos propensos a errores.

---

## Cuándo usar template literals

**Usa template literals cuando:**
- Necesites insertar variables en un string
- Trabajes con strings de varias líneas
- Necesites hacer operaciones dentro del string
- Quieras código más limpio y legible

**Usa strings tradicionales cuando:**
- Sea un string simple sin variables: `"Hola"`
- Por consistencia en código antiguo que usa comillas simples o dobles

En general, muchos desarrolladores usan template literals por defecto en código moderno.

---

## Escapando caracteres

Si necesitas mostrar `${` literalmente en un template literal, usa `\`:

```js
const mensaje = `El precio es \${100}`;
// mensaje es: "El precio es ${100}"
```

Si necesitas mostrar una comilla invertida:

```js
const mensaje = `Este es un backtick: \``;
// mensaje es: "Este es un backtick: `"
```

---

## Errores comunes

### Error 1: Olvidar las llaves

```js
// ✗ Incorrecto
const nombre = "Ana";
const mensaje = `Hola $nombre`;
// mensaje es: "Hola $nombre" (no interpola)

// ✓ Correcto
const mensaje = `Hola ${nombre}`;
```

### Error 2: Usar comillas normales

```js
// ✗ Incorrecto
const nombre = "Ana";
const mensaje = "Hola ${nombre}";
// mensaje es: "Hola ${nombre}" (no interpola)

// ✓ Correcto
const mensaje = `Hola ${nombre}`;
```

### Error 3: Olvidar cerrar las llaves

```js
// ✗ Incorrecto
const edad = 25;
const mensaje = `Tengo ${edad años`;
// Error de sintaxis

// ✓ Correcto
const mensaje = `Tengo ${edad} años`;
```

---

## Resumen

| Característica | String tradicional | Template literal |
|----------------|-------------------|------------------|
| Comillas | `"` o `'` | `` ` `` |
| Interpolar variables | `"Hola " + nombre` | `` `Hola ${nombre}` `` |
| Múltiples líneas | `"línea 1\n" + "línea 2"` | `` `línea 1\nlínea 2` `` |
| Expresiones | `"Total: " + (a + b)` | `` `Total: ${a + b}` `` |

---

## Ejercicios

### 1. Convierte a template literals

Convierte estos strings con concatenación a template literals:

#### a)

```js
const nombre = "Juan";
const apellido = "Pérez";
const nombreCompleto = nombre + " " + apellido;
```

#### b)

```js
const producto = "Mouse";
const precio = 250;
const mensaje = "El " + producto + " cuesta $" + precio;
```

#### c)

```js
const ciudad = "Madrid";
const pais = "España";
const ubicacion = ciudad + ", " + pais;
```

### 2. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
const x = 10;
const y = 5;
const resultado = `${x} + ${y} = ${x + y}`;
// valor de resultado
```

#### b)

```js
const nombre = "ana";
const mensaje = `Hola ${nombre.toUpperCase()}`;
// valor de mensaje
```

#### c)

```js
const precio = 100;
const descuento = 0.20;
const total = `Precio final: $${precio - (precio * descuento)}`;
// valor de total
```

#### d)

```js
const edad = 25;
const mensaje = `Edad: ${edad}, el doble es: ${edad * 2}`;
// valor de mensaje
```

### 3. Encuentra los errores

Identifica y corrige los errores:

#### a)

```js
const nombre = "María";
const saludo = "Hola ${nombre}";
```

#### b)

```js
const edad = 30;
const mensaje = `Tengo ${edad años`;
```

#### c)

```js
const precio = 50;
const mensaje = `Total: $precio`;
```

### 4. Crea template literals

Para estos ejercicios, usa tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea variables para tu nombre, edad y ciudad. Luego crea un mensaje usando template literals que diga:
"Me llamo [nombre], tengo [edad] años y vivo en [ciudad]."

#### b)

Crea variables para un producto, precio y cantidad. Usa template literals para crear un mensaje que muestre:
- El nombre del producto
- El precio unitario
- La cantidad
- El total (precio × cantidad)

Todo en un string multilínea con el formato que prefieras.

#### c)

Crea una "tarjeta de presentación" usando template literals multilínea que incluya:
- Tu nombre
- Tu profesión u ocupación
- Tu email
- Tu teléfono
- Tu ciudad

Dale un formato bonito con líneas en blanco y símbolos si quieres.

#### d)

Crea variables para 3 productos con sus precios. Usa template literals para crear una "factura" que muestre:
- Cada producto con su precio
- El subtotal (suma de los 3)
- El IVA (16% del subtotal)
- El total final

#### e)

Experimenta creando mensajes dinámicos. Crea variables para diferentes escenarios y usa template literals para generar mensajes personalizados. Por ejemplo: nombre de usuario, puntos ganados, nivel alcanzado, recompensa obtenida, etc.

