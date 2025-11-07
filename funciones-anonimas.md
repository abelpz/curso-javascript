# Funciones anónimas

## Qué son las funciones anónimas

  Las funciones anónimas son funciones que no tienen nombre. Se utilizan generalmente como argumentos para otras funciones o para asignarlas a variables.

  Mira la diferencia entre una función tradicional y una función anónima:

  Una función tradicional:

  ```js
  function suma(a, b) {
    return a + b;
  };
  ```

  Una función anónima:

  ```js
  function(a, b) {
    return a + b;
  };
  ```

  >Vuelve a ver ambas funciones detenidamente.
  >
  > ¿Cuál es la diferencia entre las dos?

  Fíjate que la única diferencia es que la función anónima no tiene nombre después de la palabra `function` y por lo tanto no se puede llamar directamente. Si quisieras llamar a la función tradicional simplemente la llamas por su nombre y le pasas los valores que necesita para a y b.

  ```js
  suma(2, 3); // 5
  ```

  Pero, para poder utilizar una función anónima, primero debes asignarla a algo que tenga un nombre, como una variable, una propiedad de un objeto o un elemento de un array.

  Veamos cada uno de estos casos.

  Primero, asignándola a una variable:

  ```js
  const sumar = function(a, b) {
    return a + b;
  };
  ```

  Como puedes ver en el ejemplo, creamos una variable con el nombre con el que queremos llamar a la función (en este caso `sumar`) y le asignamos la función anónima usando el operador de asignación `=`. De esta forma podemos llamar a la función a través del nombre de la variable.

  Así llamamos a la función:

  ```js
  sumar(2, 3);
  ```

  Como sabemos, el resultado será 5. Porque la función toma los valores 2 y 3 como argumentos para a y b respectivamente, y devuelve su suma.
  
  ___

  También se pueden asignar las funciones anónimas a la propiedad de un objeto:

  ```js

  const calculadora = {
    suma: function(a, b) {
      return a + b;
    }
  };

  calculadora.suma(2, 3); // 5
  ```

  > Vuelve a ver el ejemplo detenidamente.
  > ¿Qué es calculadora y qué es suma?

  calculadora es una variable que contiene un objeto con una propiedad llamada suma. Y suma es una propiedad del objeto que contiene una función anónima. Podemos llamar a la función a través de la propiedad del objeto:
  
  ```js
  calculadora.suma(2, 3)
  ```

  > Como puedes ver, cada vez que llamamos a una función utilizamos los paréntesis y dentro de ellos pasamos los valores o datos que necesita la función para retornar un valor. Como la propiedad suma contiene una función, podemos llamarla como llamaríamos a cualquier otra función.

  ---

  También se pueden introducir funciones anónimas dentro de un array.

  ```js
  const operaciones = [
    function(a, b) {
      return a + b;
    },
    function(a, b) {
      return a - b;
    }
  ];
  operaciones[0](2, 3);
  operaciones[1](5, 2);
  ```

  > Vuelve a observar el ejemplo detenidamente.
  > ¿Qué es operaciones? ¿Cuántos elementos tiene el array dentro de la variable operaciones?

  operaciones es una variable que contiene un array con dos elementos, cada uno de ellos es una función anónima. Podemos llamar a las funciones a través de su índice en el array:
  
  ```js
    const a = operaciones[0](2, 3)
    const b = operaciones[1](5, 2)
  ```

  > ¿Cuál es el valor de a? y ¿cuál es el valor de b?

  operaciones[0] corresponde a función anónima que está de primera en el array, y operaciones[1] corresponde a función anónima que está de segunda en el array.

  Por lo tanto, `operaciones[0](2, 3)` es igual a 5 y `operaciones[1](5, 2)` es igual a 3.

---

  Las funciones anónimas también se utilizan mucho como parámetros para otras funciones, en este caso se les llama **callbacks**, de los que hablaremos más adelante, en otra lección.

---

## Ejercicios

### 1. Encuentra los errores

#### a)

```js
function(a, b) {
  return a + b;
};

const resultado = suma(2, 3);
```

#### b)

```js

const operaciones = {
  suma:  suma(a, b) {
    return a + b;
  }
}

const resultado = operaciones.suma(2, 3);
```

### 2. Resuelve

#### a)

```js
const f = function(a,b) {
  return a * b + 5
}

const resultado = f(2,4);
//valor de resultado
```

#### b)

```js
const o = {
  name: "Elisa",
  actions: {
    greet: function(name) {
      return "Hello " + name;
    },
  }
}

const x = o.actions.greet("Henry");
//valor de x
```

#### c)

```js
const a = [
  function(a, b) {
    return a + b;
  },
  function(a, b) {
    return a - b;
  }
];

const resultado = a[0](2, 2) * a[1](4, 2);
//valor de resultado
```

### 3. Crea funciones anónimas

Para estos ejercicios, utiliza vs-code o tu editor de código favorito. Toma una captura de pantalla de cada uno y compartela con tu instructor.

#### a)
Crea una función anónima que sume dos números y retorne el resultado.

#### b)
Crea una función anónima que reste dos números y retorne el resultado.

#### c)
Crea una variable que contenga un objeto que tenga una propiedad llamada "saludos". "saludos" debe ser un objeto que tenga varias propiedades, cada una de ellas con una función anónima que retorne un saludo diferente. Cada saludo es un string diferente, como: "hola", "hello", "buenos días", "buenas tardes", "buenas noches", etc.