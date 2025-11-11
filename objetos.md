# Objetos

## Qué son los objetos

Los objetos son estructuras que nos permiten agrupar información relacionada usando pares de **propiedad: valor**. Son perfectos para describir cosas del mundo real.

Ya viste objetos brevemente en la lección de tipos de datos. Ahora aprenderás cómo trabajar con ellos en profundidad.

Mira este ejemplo de un objeto:

```js
const persona = {
  nombre: "Ana",
  edad: 25,
  ciudad: "Madrid"
};
```

> ¿Qué describe este objeto?
>
> Describe a una persona con su nombre, edad y ciudad.

Los objetos se escriben entre llaves `{}` y contienen propiedades. Cada propiedad tiene un **nombre** (clave) y un **valor**, separados por dos puntos `:`.

---

## Creando objetos

Para crear un objeto, usas llaves `{}` y defines pares de propiedad: valor, separados por comas:

```js
const libro = {
  titulo: "JavaScript para todos",
  autor: "María López",
  paginas: 300
};
```

Puedes crear objetos vacíos:

```js
const vacio = {};
```

Las propiedades pueden tener cualquier tipo de dato como valor:

```js
const producto = {
  nombre: "Laptop",
  precio: 1000,
  disponible: true,
  cantidad: 5
};
```

> ¿Cuántas propiedades tiene el objeto producto?
>
> Tiene 4 propiedades: nombre, precio, disponible y cantidad.

---

## Propiedades y valores

Cada propiedad en un objeto tiene:
1. Un **nombre** (también llamado clave o key)
2. Un **valor** (que puede ser de cualquier tipo)

```js
const auto = {
  marca: "Toyota",    // propiedad: marca, valor: "Toyota"
  modelo: "Corolla",  // propiedad: modelo, valor: "Corolla"
  año: 2023          // propiedad: año, valor: 2023
};
```

Los valores pueden ser strings, números, booleanos, arrays, otros objetos, etc:

```js
const estudiante = {
  nombre: "Carlos",              // string
  edad: 20,                      // número
  activo: true,                  // booleano
  calificaciones: [8, 9, 7],    // array
  direccion: {                   // objeto
    calle: "Main St",
    numero: 123
  }
};
```

---

## Accediendo a propiedades

**Acceder** a una propiedad significa obtener o leer el valor que está guardado en esa propiedad del objeto.

Hay dos formas de acceder a las propiedades de un objeto:

### 1. Notación de punto

La forma más común es usar el punto `.`:

```js
const persona = {
  nombre: "Ana",
  edad: 25,
  ciudad: "Madrid"
};

const nombrePersona = persona.nombre;
// nombrePersona es "Ana"

const edadPersona = persona.edad;
// edadPersona es 25

const ciudadPersona = persona.ciudad;
// ciudadPersona es "Madrid"
```

> ¿Ves el patrón?
>
> Escribes el nombre del objeto, luego un punto, y luego el nombre de la propiedad.

### 2. Notación de corchetes

También puedes usar corchetes `[]` con el nombre de la propiedad como string:

```js
const libro = {
  titulo: "JavaScript",
  autor: "Pedro",
  paginas: 200
};

const tituloLibro = libro["titulo"];
// tituloLibro es "JavaScript"

const autorLibro = libro["autor"];
// autorLibro es "Pedro"
```

> ¿Cuándo usar corchetes?
>
> Los corchetes son útiles cuando el nombre de la propiedad está en una variable o tiene caracteres especiales.

Ejemplo con variable:

```js
const auto = {
  marca: "Toyota",
  modelo: "Corolla",
  año: 2023
};

const propiedad = "marca";
const valor = auto[propiedad];
// valor es "Toyota"
```

---

## Modificando propiedades

Puedes cambiar el valor de una propiedad accediendo a ella y asignando un nuevo valor:

```js
const producto = {
  nombre: "Mouse",
  precio: 25,
  stock: 10
};

producto.precio = 20;
// Ahora producto.precio es 20

producto.stock = 15;
// Ahora producto.stock es 15
```

También puedes usar notación de corchetes:

```js
const persona = {
  nombre: "Carlos",
  edad: 30
};

persona["edad"] = 31;
// Ahora persona.edad es 31
```

> ¿Puedes modificar un objeto const?
>
> Sí, puedes modificar las propiedades. Lo que no puedes es reasignar el objeto completo.

```js
const libro = {
  titulo: "JavaScript",
  paginas: 200
};

libro.paginas = 250; // ✓ Esto funciona

libro = { titulo: "Python", paginas: 300 }; // ✗ Esto da error
```

---

## Agregando propiedades

Puedes agregar nuevas propiedades a un objeto en cualquier momento:

```js
const persona = {
  nombre: "Ana",
  edad: 25
};

persona.ciudad = "Barcelona";
// Ahora persona tiene la propiedad ciudad

persona.profesion = "Ingeniera";
// Ahora persona tiene la propiedad profesion
```

El objeto ahora es:

```js
{
  nombre: "Ana",
  edad: 25,
  ciudad: "Barcelona",
  profesion: "Ingeniera"
}
```

También puedes agregar con corchetes:

```js
const auto = {
  marca: "Toyota"
};

auto["modelo"] = "Corolla";
auto["año"] = 2023;
```

---

## Eliminando propiedades

Puedes eliminar una propiedad usando el operador `delete`:

```js
const producto = {
  nombre: "Laptop",
  precio: 1000,
  descuento: 100
};

delete producto.descuento;
// Ahora producto ya no tiene la propiedad descuento
```

El objeto queda:

```js
{
  nombre: "Laptop",
  precio: 1000
}
```

---

## Objetos anidados

Un objeto puede contener otros objetos como valores de sus propiedades:

```js
const persona = {
  nombre: "Carlos",
  edad: 30,
  direccion: {
    calle: "Main Street",
    numero: 123,
    ciudad: "Madrid"
  }
};
```

Para acceder a propiedades de objetos anidados, usas múltiples puntos:

```js
const calle = persona.direccion.calle;
// calle es "Main Street"

const ciudad = persona.direccion.ciudad;
// ciudad es "Madrid"

const numero = persona.direccion.numero;
// numero es 123
```

> ¿Entiendes cómo funciona?
>
> Primero accedes a `persona.direccion`, que es un objeto. Luego accedes a las propiedades de ese objeto.

Ejemplo más complejo:

```js
const empresa = {
  nombre: "Tech Corp",
  fundador: {
    nombre: "María",
    edad: 35,
    contacto: {
      email: "maria@example.com",
      telefono: "123456789"
    }
  }
};

const nombreFundador = empresa.fundador.nombre;
// nombreFundador es "María"

const emailFundador = empresa.fundador.contacto.email;
// emailFundador es "maria@example.com"
```

---

## Objetos con arrays

Los objetos pueden contener arrays como valores:

```js
const estudiante = {
  nombre: "Pedro",
  edad: 22,
  calificaciones: [8, 9, 7, 10],
  materias: ["Matemáticas", "Historia", "Ciencias"]
};

const primeraCalificacion = estudiante.calificaciones[0];
// primeraCalificacion es 8

const segundaMateria = estudiante.materias[1];
// segundaMateria es "Historia"

const cantidadMaterias = estudiante.materias.length;
// cantidadMaterias es 4
```

> ¿Ves cómo se combinan?
>
> Primero usas punto para acceder a la propiedad del objeto, luego corchetes para acceder al array.

---

## Arrays de objetos

Puedes tener un array donde cada elemento es un objeto:

```js
const productos = [
  { nombre: "Laptop", precio: 1000 },
  { nombre: "Mouse", precio: 25 },
  { nombre: "Teclado", precio: 50 }
];

const primerProducto = productos[0];
// primerProducto es { nombre: "Laptop", precio: 1000 }

const nombreSegundo = productos[1].nombre;
// nombreSegundo es "Mouse"

const precioTercero = productos[2].precio;
// precioTercero es 50
```

> ¿Cuál es el orden?
>
> Primero corchetes para acceder al array, luego punto para acceder a las propiedades del objeto.

---

## Verificando si una propiedad existe

Puedes verificar si un objeto tiene una propiedad usando `in`:

```js
const auto = {
  marca: "Toyota",
  modelo: "Corolla"
};

const tieneMarca = "marca" in auto;
// tieneMarca es true

const tieneColor = "color" in auto;
// tieneColor es false
```

O verificar si el valor es `undefined`:

```js
const persona = {
  nombre: "Ana",
  edad: 25
};

const ciudad = persona.ciudad;
// ciudad es undefined (la propiedad no existe)

let mensaje;

if (persona.ciudad === undefined) {
  mensaje = "No tiene ciudad definida";
} else {
  mensaje = `Vive en ${persona.ciudad}`;
}
// mensaje es "No tiene ciudad definida"
```

---

## Objetos y template literals

Los objetos funcionan muy bien con template literals:

```js
const persona = {
  nombre: "Carlos",
  edad: 30,
  profesion: "Desarrollador"
};

const presentacion = `Hola, soy ${persona.nombre}, tengo ${persona.edad} años y soy ${persona.profesion}.`;
// presentacion es "Hola, soy Carlos, tengo 30 años y soy Desarrollador."
```

```js
const producto = {
  nombre: "Laptop",
  precio: 1000,
  descuento: 0.15
};

const precioFinal = producto.precio * (1 - producto.descuento);
const mensaje = `El ${producto.nombre} cuesta $${precioFinal}`;
// mensaje es "El Laptop cuesta $850"
```

---

## Copiando objetos

Similar a los arrays, si intentas copiar un objeto con `=`, no obtienes una copia independiente:

```js
const original = {
  nombre: "Ana",
  edad: 25
};

const copia = original;
copia.edad = 30;

// Ahora original también cambió
// original.edad es 30
// copia.edad es 30
```

> ¿Por qué pasa esto?
>
> Porque `copia` y `original` son como dos nombres diferentes para el mismo objeto. Es como si dos personas tuvieran la llave de la misma caja: cuando una persona cambia algo dentro de la caja, la otra persona también verá ese cambio porque es la misma caja.

---

## Comparando objetos

Dos objetos no son iguales aunque tengan las mismas propiedades:

```js
const obj1 = { nombre: "Ana", edad: 25 };
const obj2 = { nombre: "Ana", edad: 25 };

const sonIguales = obj1 === obj2;
// sonIguales es false
```

> ¿Por qué son diferentes?
>
> Porque aunque los dos objetos tengan las mismas propiedades y valores, son dos objetos separados. Es como tener dos cajas diferentes que contienen las mismas cosas: las cajas siguen siendo diferentes aunque tengan el mismo contenido dentro.

---

## Trabajando con objetos en condicionales

Puedes usar propiedades de objetos en condicionales:

```js
const producto = {
  nombre: "Laptop",
  precio: 1200,
  stock: 5
};

let mensaje;

if (producto.stock > 0) {
  mensaje = `${producto.nombre} disponible`;
} else {
  mensaje = `${producto.nombre} agotado`;
}
// mensaje es "Laptop disponible"
```

```js
const estudiante = {
  nombre: "Pedro",
  calificacion: 85
};

let resultado;

if (estudiante.calificacion >= 90) {
  resultado = "Excelente";
} else if (estudiante.calificacion >= 70) {
  resultado = "Bien";
} else {
  resultado = "Regular";
}
// resultado es "Bien"
```

Verificando múltiples propiedades:

```js
const usuario = {
  nombre: "Carlos",
  edad: 25,
  suscrito: true,
  activo: true
};

let acceso;

if (usuario.edad >= 18 && usuario.suscrito && usuario.activo) {
  acceso = "Acceso completo";
} else {
  acceso = "Acceso limitado";
}
// acceso es "Acceso completo"
```

---

## Ejemplos prácticos

### Ejemplo 1: Perfil de usuario

```js
const usuario = {
  username: "ana_dev",
  nombre: "Ana García",
  edad: 28,
  email: "ana@example.com",
  premium: true
};

const presentacion = `Usuario: ${usuario.username}`;
// presentacion es "Usuario: ana_dev"

const esPremium = usuario.premium ? "Sí" : "No";
// esPremium es "Sí"
```

### Ejemplo 2: Producto de tienda

```js
const producto = {
  id: 101,
  nombre: "Teclado mecánico",
  precio: 150,
  stock: 25,
  categoria: "Accesorios"
};

const disponible = producto.stock > 0;
// disponible es true

producto.stock = producto.stock - 1;
// Vendimos uno, ahora stock es 24
```

### Ejemplo 3: Datos de contacto

```js
const contacto = {
  nombre: "María López",
  empresa: "Tech Solutions",
  telefono: "555-0123",
  direccion: {
    calle: "Av. Principal",
    numero: 456,
    ciudad: "Barcelona",
    codigoPostal: "08001"
  }
};

const direccionCompleta = `${contacto.direccion.calle} ${contacto.direccion.numero}, ${contacto.direccion.ciudad}`;
// direccionCompleta es "Av. Principal 456, Barcelona"
```

### Ejemplo 4: Lista de estudiantes

```js
const clase = {
  nombre: "JavaScript 101",
  profesor: "Carlos Ruiz",
  estudiantes: [
    { nombre: "Ana", nota: 85 },
    { nombre: "Pedro", nota: 92 },
    { nombre: "María", nota: 78 }
  ]
};

const cantidadEstudiantes = clase.estudiantes.length;
// cantidadEstudiantes es 3

const primerEstudiante = clase.estudiantes[0].nombre;
// primerEstudiante es "Ana"

const notaSegundo = clase.estudiantes[1].nota;
// notaSegundo es 92
```

### Ejemplo 5: Configuración de aplicación

```js
const config = {
  idioma: "es",
  tema: "oscuro",
  notificaciones: true,
  opciones: {
    sonido: true,
    vibracion: false,
    email: true
  }
};

// Modificando configuración
config.tema = "claro";
config.opciones.sonido = false;

const temaActual = config.tema;
// temaActual es "claro"
```

---

## Resumen

- Los objetos agrupan información relacionada en pares propiedad: valor
- Se crean con llaves `{}`
- Usas `objeto.propiedad` o `objeto["propiedad"]` para acceder a valores
- Puedes modificar: `objeto.propiedad = nuevoValor`
- Puedes agregar: `objeto.nuevaPropiedad = valor`
- Puedes eliminar: `delete objeto.propiedad`
- Los objetos pueden contener arrays y otros objetos
- Los arrays pueden contener objetos

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de cada variable?

#### a)

```js
const libro = {
  titulo: "JavaScript",
  autor: "María",
  paginas: 300
};

const autor = libro.autor;
// valor de autor
```

#### b)

```js
const auto = {
  marca: "Toyota",
  modelo: "Corolla",
  año: 2023
};

auto.año = 2024;
const añoActual = auto.año;
// valor de añoActual
```

#### c)

```js
const persona = {
  nombre: "Carlos",
  direccion: {
    ciudad: "Madrid",
    pais: "España"
  }
};

const ciudad = persona.direccion.ciudad;
// valor de ciudad
```

#### d)

```js
const productos = [
  { nombre: "Mouse", precio: 25 },
  { nombre: "Teclado", precio: 50 }
];

const precioSegundo = productos[1].precio;
// valor de precioSegundo
```

#### e)

```js
const estudiante = {
  nombre: "Ana",
  notas: [8, 9, 7]
};

const segundaNota = estudiante.notas[1];
// valor de segundaNota
```

### 2. Encuentra los errores

Identifica y corrige los errores:

#### a)

```js
const persona = {
  nombre: "Pedro"
  edad: 25
};
```

#### b)

```js
const auto = {
  marca: "Toyota",
  modelo: "Corolla"
};

const marca = auto[marca];
```

#### c)

```js
const producto = {
  nombre: "Laptop",
  precio: 1000
};

const nombre = producto.name;
```

### 3. Crea objetos

#### a)

Crea un objeto llamado `mascota` con las propiedades: nombre, tipo (perro, gato, etc.), edad, y color.

#### b)

Crea un objeto llamado `pelicula` con: título, director, año, y duración (en minutos).

#### c)

Crea un objeto llamado `restaurante` que tenga: nombre, dirección (como objeto con calle y número), y especialidades (como array de strings).

### 4. Accede y modifica

Para estos ejercicios, usa tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea un objeto `persona` con nombre, edad y ciudad. Luego:
- Accede y guarda cada propiedad en variables separadas
- Modifica la edad
- Agrega una nueva propiedad `profesion`
- Elimina la propiedad `ciudad`

#### b)

Crea un objeto `tienda` con nombre, productos (array de objetos con nombre y precio), y ubicación (objeto con ciudad y dirección). Luego:
- Accede al nombre del segundo producto
- Accede a la ciudad de la ubicación
- Modifica el precio del primer producto
- Agrega un nuevo producto al array

#### c)

Crea un array llamado `biblioteca` que contenga 3 objetos libro. Cada libro debe tener: título, autor, páginas, y disponible (booleano). Luego:
- Accede al título del primer libro
- Accede a las páginas del tercer libro
- Cambia el estado de disponible del segundo libro

### 5. Usa objetos en condicionales

#### a)

Crea un objeto `producto` con nombre, precio y stock. Escribe condicionales que asignen un mensaje diferente a una variable `estado` según:
- Si stock > 10: "Disponible"
- Si stock > 0 y <= 10: "Pocas unidades"
- Si stock === 0: "Agotado"

#### b)

Crea un objeto `usuario` con nombre, edad, y suscripcion (true/false). Usa condicionales para determinar:
- Si puede acceder a contenido premium (edad >= 18 Y suscripcion === true)
- Asigna el resultado a una variable `acceso`

#### c)

Crea un array de objetos `estudiantes`, cada uno con nombre y calificación. Usa condicionales para cada estudiante y determina si:
- calificacion >= 90: "Excelente"
- calificacion >= 70: "Bien"  
- calificacion >= 50: "Regular"
- menor a 50: "Insuficiente"

Asigna los resultados a variables para cada estudiante.

#### d)

Crea un objeto `pedido` con cliente (objeto con nombre y email), productos (array de objetos), y total. Usa condicionales para:
- Verificar si el total es mayor a 100 (envío gratis)
- Verificar si tiene más de 3 productos (descuento)
- Asigna mensajes apropiados a variables

#### e)

Crea un objeto `evento` con nombre, fecha, capacidad, y registrados. Usa condicionales para determinar:
- Si aún hay lugares (registrados < capacidad)
- Si está casi lleno (registrados >= capacidad * 0.8)
- Si está completamente lleno (registrados >= capacidad)

Asigna estados apropiados a variables según cada caso.



