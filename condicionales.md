# Condicionales

## Qué son los condicionales

Los condicionales nos permiten tomar decisiones en nuestro código. Dependiendo de si una condición es verdadera o falsa, el programa ejecutará diferentes bloques de código.

Imagina que estás escribiendo las reglas de un juego:
- "Si tienes más de 100 puntos, ganas"
- "Si la temperatura es menor a 15 grados, usa abrigo"
- "Si eres mayor de 18 años, puedes votar"

En JavaScript, usamos condicionales para escribir exactamente este tipo de lógica.

---

## La estructura if

La estructura más básica es `if` (que significa "si" en inglés). Si una condición es verdadera, se ejecuta el código dentro del bloque.

```js
const edad = 20;
let mensaje;

if (edad >= 18) {
  mensaje = "Eres mayor de edad";
}
// mensaje es "Eres mayor de edad"
```

> ¿Qué hace este código?
>
> Verifica si edad es mayor o igual a 18. Si es verdadero, asigna el mensaje a la variable.

La estructura es:

```js
if (condición) {
  // código que se ejecuta si la condición es verdadera
}
```

Más ejemplos:

```js
const temperatura = 35;
let clima;

if (temperatura > 30) {
  clima = "Hace mucho calor";
}
// clima es "Hace mucho calor"
```

```js
const puntos = 150;
let resultado;

if (puntos >= 100) {
  resultado = "¡Ganaste!";
}
// resultado es "¡Ganaste!"
```

```js
const nombre = "Ana";
let saludo;

if (nombre === "Ana") {
  saludo = "Hola Ana";
}
// saludo es "Hola Ana"
```

> ¿Cuándo se ejecuta el código dentro de las llaves?
>
> Solo cuando la condición entre paréntesis es `true`.

---

## La estructura if...else

La estructura `if...else` nos permite ejecutar un código si la condición es verdadera, y otro código diferente si es falsa.

```js
const edad = 15;
let mensaje;

if (edad >= 18) {
  mensaje = "Eres mayor de edad";
} else {
  mensaje = "Eres menor de edad";
}
// mensaje es "Eres menor de edad"
```

> ¿Qué valor tiene mensaje?
>
> "Eres menor de edad", porque 15 no es mayor o igual a 18.

La estructura es:

```js
if (condición) {
  // código si la condición es verdadera
} else {
  // código si la condición es falsa
}
```

Más ejemplos:

```js
const temperatura = 18;
let clima;

if (temperatura > 25) {
  clima = "Hace calor";
} else {
  clima = "No hace calor";
}
// clima es "No hace calor"
```

```js
const puntos = 50;
let resultado;

if (puntos >= 100) {
  resultado = "Ganaste";
} else {
  resultado = "Sigue intentando";
}
// resultado es "Sigue intentando"
```

Con variables:

```js
const precio = 100;
const dinero = 150;
let mensaje;

if (dinero >= precio) {
  mensaje = "Puedes comprarlo";
} else {
  mensaje = "No tienes suficiente dinero";
}
// mensaje es "Puedes comprarlo"
```

---

## La estructura if...else if...else

Cuando necesitas verificar múltiples condiciones, usas `else if`:

```js
const nota = 85;
let calificacion;

if (nota >= 90) {
  calificacion = "Excelente";
} else if (nota >= 70) {
  calificacion = "Bien";
} else if (nota >= 50) {
  calificacion = "Regular";
} else {
  calificacion = "Insuficiente";
}
// calificacion es "Bien"
```

> ¿Qué valor tiene calificacion?
>
> "Bien", porque 85 cumple la segunda condición (>= 70).

JavaScript evalúa las condiciones en orden:
1. ¿Es nota >= 90? No (85 no es >= 90)
2. ¿Es nota >= 70? Sí (85 >= 70) ✓ Se ejecuta este bloque y se detiene

```js
const hora = 14;
let saludo;

if (hora < 12) {
  saludo = "Buenos días";
} else if (hora < 18) {
  saludo = "Buenas tardes";
} else {
  saludo = "Buenas noches";
}
// saludo es "Buenas tardes"
```

> ¿Qué saludo se asigna si hora es 14?
>
> "Buenas tardes", porque 14 está entre 12 y 18.

Puedes tener tantos `else if` como necesites:

```js
const edad = 25;
let categoria;

if (edad < 13) {
  categoria = "Niño";
} else if (edad < 18) {
  categoria = "Adolescente";
} else if (edad < 30) {
  categoria = "Adulto joven";
} else if (edad < 60) {
  categoria = "Adulto";
} else {
  categoria = "Adulto mayor";
}
// categoria es "Adulto joven"
```

---

## Condiciones con operadores lógicos

Puedes combinar múltiples condiciones usando los operadores lógicos que aprendiste: `&&` (AND), `||` (OR), `!` (NOT).

### Usando AND (&&)

Ambas condiciones deben ser verdaderas:

```js
const edad = 25;
const tieneLicencia = true;
let mensaje;

if (edad >= 18 && tieneLicencia) {
  mensaje = "Puedes conducir";
} else {
  mensaje = "No puedes conducir";
}
// mensaje es "Puedes conducir"
```

```js
const temperatura = 28;
const esSoleado = true;
let recomendacion;

if (temperatura > 25 && esSoleado) {
  recomendacion = "Perfecto para ir a la playa";
}
// recomendacion es "Perfecto para ir a la playa"
```

### Usando OR (||)

Al menos una condición debe ser verdadera:

```js
const dia = "sábado";
let tipoDia;

if (dia === "sábado" || dia === "domingo") {
  tipoDia = "Es fin de semana";
} else {
  tipoDia = "Es día de semana";
}
// tipoDia es "Es fin de semana"
```

```js
const edad = 10;
let precio;

if (edad < 12 || edad > 65) {
  precio = "Tienes descuento";
} else {
  precio = "Precio normal";
}
// precio es "Tienes descuento"
```

### Usando NOT (!)

Invierte el valor booleano:

```js
const lloviendo = false;
let mensaje;

if (!lloviendo) {
  mensaje = "Puedes salir sin paraguas";
}
// mensaje es "Puedes salir sin paraguas"
```

```js
const disponible = true;
let estado;

if (!disponible) {
  estado = "Producto agotado";
} else {
  estado = "Producto disponible";
}
// estado es "Producto disponible"
```

### Combinando operadores

```js
const edad = 25;
const esEstudiante = true;
const esMaestro = false;
let descuento;

if ((edad >= 18 && esEstudiante) || esMaestro) {
  descuento = "Tienes descuento";
}
// descuento es "Tienes descuento"
```

> ¿Entiendes esta condición?
>
> Tiene descuento si: (es mayor de 18 Y es estudiante) O es maestro.

---

## Anidando condicionales

Puedes poner un `if` dentro de otro `if`:

```js
const edad = 25;
const tieneLicencia = true;
let mensaje;

if (edad >= 18) {
  if (tieneLicencia) {
    mensaje = "Puedes conducir";
  } else {
    mensaje = "Necesitas obtener tu licencia";
  }
} else {
  mensaje = "Eres muy joven para conducir";
}
// mensaje es "Puedes conducir"
```

Sin embargo, a menudo es mejor usar operadores lógicos:

```js
// Más claro
const edad = 25;
const tieneLicencia = true;
let mensaje;

if (edad >= 18 && tieneLicencia) {
  mensaje = "Puedes conducir";
} else if (edad >= 18 && !tieneLicencia) {
  mensaje = "Necesitas obtener tu licencia";
} else {
  mensaje = "Eres muy joven para conducir";
}
// mensaje es "Puedes conducir"
```

---

## Operador ternario

El operador ternario es una forma corta de escribir un `if...else` simple. Es útil cuando quieres asignar un valor basado en una condición.

La sintaxis es:

```js
condición ? valorSiVerdadero : valorSiFalso
```

Ejemplo con if...else:

```js
const edad = 20;
let mensaje;

if (edad >= 18) {
  mensaje = "Mayor de edad";
} else {
  mensaje = "Menor de edad";
}
```

El mismo ejemplo con operador ternario:

```js
const edad = 20;
const mensaje = edad >= 18 ? "Mayor de edad" : "Menor de edad";
```

> ¿Ves cómo es más corto?
>
> En una sola línea asignamos el valor a mensaje basándonos en la condición.

Más ejemplos:

```js
const puntos = 150;
const resultado = puntos >= 100 ? "Ganaste" : "Perdiste";
// resultado es "Ganaste"
```

```js
const temperatura = 30;
const clima = temperatura > 25 ? "Calor" : "Frío";
// clima es "Calor"
```

En template literals:

```js
const edad = 15;
const mensaje = `Eres ${edad >= 18 ? "mayor" : "menor"} de edad`;
// mensaje es "Eres menor de edad"
```

```js
const stock = 5;
console.log(`Estado: ${stock > 0 ? "Disponible" : "Agotado"}`);
```

> ¿Cuándo usar el operador ternario?
>
> Para condiciones simples que asignan valores. Si la lógica es compleja, usa if...else.

---

## Valores truthy y falsy

En JavaScript, algunos valores se consideran "falsy" (falsos) y otros "truthy" (verdaderos) cuando se usan en condiciones.

### Valores falsy (se comportan como false):

```js
false
0
"" (string vacío)
null
undefined
NaN
```

### Valores truthy (se comportan como true):

Todo lo demás es truthy, incluyendo:

```js
true
cualquier número diferente de 0
cualquier string no vacío
arrays (incluso vacíos [])
objetos (incluso vacíos {})
```

Ejemplos:

```js
const nombre = "";
let mensaje;

if (nombre) {
  mensaje = `Hola ${nombre}`;
} else {
  mensaje = "No ingresaste un nombre";
}
// mensaje es "No ingresaste un nombre"
```

```js
const puntos = 0;
let mensaje;

if (puntos) {
  mensaje = `Tienes ${puntos} puntos`;
} else {
  mensaje = "No tienes puntos";
}
// mensaje es "No tienes puntos"
```

```js
const edad = 25;
let mensaje;

if (edad) {
  mensaje = "Edad válida";
}
// mensaje es "Edad válida" (25 es truthy)
```

> ¿Por qué es útil esto?
>
> Puedes verificar rápidamente si una variable tiene un valor sin comparar explícitamente.

---

## Comparación de if vs else if vs else

```js
// Solo un if
const edad = 20;
let mensaje;

if (edad >= 18) {
  mensaje = "Mayor de edad";
}
// mensaje es "Mayor de edad"
// Si la condición es falsa, mensaje quedaría undefined

// if...else
let categoria;

if (edad >= 18) {
  categoria = "Mayor de edad";
} else {
  categoria = "Menor de edad";
}
// categoria es "Mayor de edad"
// Siempre se ejecuta uno de los dos bloques

// if...else if...else
let tipo;

if (edad >= 65) {
  tipo = "Adulto mayor";
} else if (edad >= 18) {
  tipo = "Adulto";
} else {
  tipo = "Menor de edad";
}
// tipo es "Adulto"
// Se ejecuta el primer bloque cuya condición sea verdadera
```

---

## Ejemplos prácticos

### Ejemplo 1: Sistema de calificaciones

```js
const nota = 75;
let calificacion;

if (nota >= 90) {
  calificacion = "A";
} else if (nota >= 80) {
  calificacion = "B";
} else if (nota >= 70) {
  calificacion = "C";
} else if (nota >= 60) {
  calificacion = "D";
} else {
  calificacion = "F";
}

const resultado = `Tu calificación es: ${calificacion}`;
// resultado es "Tu calificación es: C"
```

### Ejemplo 2: Calculadora de descuentos

```js
const precio = 1000;
const cantidad = 5;
let descuento = 0;

if (cantidad >= 10) {
  descuento = 0.20; // 20%
} else if (cantidad >= 5) {
  descuento = 0.10; // 10%
} else if (cantidad >= 3) {
  descuento = 0.05; // 5%
}

const precioFinal = precio * cantidad * (1 - descuento);
const mensaje = `Total a pagar: $${precioFinal}`;
// mensaje es "Total a pagar: $4500"
```

### Ejemplo 3: Validación de datos

```js
const usuario = "ana123";
const password = "secreto";
let mensaje;

if (usuario === "" || password === "") {
  mensaje = "Error: Debes llenar todos los campos";
} else if (usuario.length < 4) {
  mensaje = "Error: El usuario debe tener al menos 4 caracteres";
} else if (password.length < 6) {
  mensaje = "Error: La contraseña debe tener al menos 6 caracteres";
} else {
  mensaje = "Inicio de sesión exitoso";
}
// mensaje es "Inicio de sesión exitoso"
```

### Ejemplo 4: Recomendación de ropa

```js
const temperatura = 18;
const lloviendo = true;
let recomendacion;

if (temperatura < 10) {
  recomendacion = "Usa abrigo grueso";
} else if (temperatura < 20) {
  recomendacion = "Usa suéter";
} else {
  recomendacion = "Usa ropa ligera";
}

if (lloviendo) {
  recomendacion += " y lleva paraguas";
}
// recomendacion es "Usa suéter y lleva paraguas"
```

---

## Errores comunes

### Error 1: Usar = en lugar de ===

```js
// ✗ Incorrecto
const edad = 18;
let mensaje;
if (edad = 18) { // Esto es asignación, no comparación
  mensaje = "Mayor de edad";
}

// ✓ Correcto
if (edad === 18) {
  mensaje = "Mayor de edad";
}
```

### Error 2: Olvidar las llaves

```js
// Funciona pero puede causar problemas
let mensaje;
let mensaje2;
if (edad >= 18)
  mensaje = "Mayor de edad";
  mensaje2 = "Este mensaje SIEMPRE se asigna";

// Mejor con llaves
if (edad >= 18) {
  mensaje = "Mayor de edad";
}
mensaje2 = "Este mensaje SIEMPRE se asigna";
```

### Error 3: Condiciones inalcanzables

```js
// ✗ Incorrecto
const nota = 85;
let resultado;

if (nota >= 50) {
  resultado = "Aprobado";
} else if (nota >= 80) { // Esta condición nunca se alcanzará
  resultado = "Notable";
}

// ✓ Correcto - orden de mayor a menor
if (nota >= 80) {
  resultado = "Notable";
} else if (nota >= 50) {
  resultado = "Aprobado";
}
```

---

## Resumen

| Estructura | Uso |
|------------|-----|
| `if` | Ejecuta código si la condición es verdadera |
| `if...else` | Ejecuta un código u otro dependiendo de la condición |
| `if...else if...else` | Verifica múltiples condiciones en orden |
| `operador ternario` | Forma corta de if...else para asignaciones simples |

---

## Ejercicios

### 1. Predice el resultado

¿Cuál es el valor final de la variable?

#### a)

```js
const edad = 16;
let resultado;

if (edad >= 18) {
  resultado = "A";
} else {
  resultado = "B";
}
// ¿Cuál es el valor de resultado?
```

#### b)

```js
const puntos = 75;
let medalla;

if (puntos >= 100) {
  medalla = "Oro";
} else if (puntos >= 50) {
  medalla = "Plata";
} else {
  medalla = "Bronce";
}
// ¿Cuál es el valor de medalla?
```

#### c)

```js
const temperatura = 25;
const lloviendo = false;
let resultado;

if (temperatura > 20 && !lloviendo) {
  resultado = "X";
} else {
  resultado = "Y";
}
// ¿Cuál es el valor de resultado?
```

#### d)

```js
const edad = 25;
const mensaje = edad >= 18 ? "Mayor" : "Menor";
// ¿Cuál es el valor de mensaje?
```

### 2. Verdadero o falso

¿Estas afirmaciones son verdaderas o falsas?

#### a)

Un bloque `else` siempre es obligatorio después de un `if`.

#### b)

Puedes tener múltiples `else if` en una estructura condicional.

#### c)

En una estructura `if...else if...else`, se pueden ejecutar múltiples bloques al mismo tiempo.

#### d)

El operador ternario puede reemplazar cualquier estructura if...else sin importar su complejidad.

### 3. Encuentra los errores

Identifica y corrige los errores:

#### a)

```js
const edad = 20;
let mensaje;

if edad >= 18 {
  mensaje = "Mayor de edad";
}
```

#### b)

```js
const puntos = 50;
let resultado;

if (puntos >= 100) {
  resultado = "Ganaste";
else {
  resultado = "Perdiste";
}
```

#### c)

```js
const temperatura = 30;
let mensaje1;
let mensaje2;

if (temperatura > 25) 
  mensaje1 = "Hace calor";
  mensaje2 = "Usa protector solar";
```

### 4. Convierte a operador ternario

Convierte estos if...else a operador ternario:

#### a)

```js
let mensaje;
if (edad >= 18) {
  mensaje = "Adulto";
} else {
  mensaje = "Niño";
}
```

#### b)

```js
let estado;
if (stock > 0) {
  estado = "Disponible";
} else {
  estado = "Agotado";
}
```

### 5. Crea condicionales

Para estos ejercicios, usa tu editor de código favorito. Toma una captura de pantalla y compártela con tu instructor.

#### a)

Crea una variable `temperatura`. Escribe condicionales que asignen diferentes valores a una variable `clima`:
- Si es menor a 0: "Congelado"
- Si está entre 0 y 15: "Frío"
- Si está entre 15 y 25: "Templado"
- Si es mayor a 25: "Calor"

#### b)

Crea un sistema de descuentos basado en la cantidad de productos:
- 1-2 productos: Sin descuento (0)
- 3-5 productos: 5% de descuento (0.05)
- 6-10 productos: 10% de descuento (0.10)
- Más de 10: 15% de descuento (0.15)

Crea variables para precio unitario, cantidad, y calcula el precio final aplicando el descuento correspondiente.

#### c)

Crea un validador de edad para diferentes categorías de entrada a un evento:
- Menor de 12: Entrada niño ($50)
- 12-17: Entrada adolescente ($100)
- 18-64: Entrada adulto ($150)
- 65 o más: Entrada adulto mayor ($80)

Asigna el tipo de entrada a una variable `tipoEntrada` y el precio a una variable `precio`.

#### d)

Crea un sistema que evalúe si un usuario puede acceder a contenido basándose en:
- Edad (debe ser >= 18)
- Tiene suscripción activa (true/false)
- No está bloqueado (true/false)

Asigna diferentes mensajes a una variable `acceso` según los diferentes casos.

#### e)

Crea un programa que determine el estado de un pedido basado en los días transcurridos:
- Si días < 0: "Error en la fecha"
- Si días === 0: "Pedido realizado hoy"
- Si días entre 1-3: "En preparación"
- Si días entre 4-7: "En tránsito"
- Si días > 7: "Entregado"

Asigna el estado a una variable `estadoPedido` y prueba con diferentes valores de días.

