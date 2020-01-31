# Metodos-de-array


### forEach
* Podemos iterar o recorrer un array utilizando el método forEach()
* Este método acepta una función como parámetro
* La función que le pasamos a este método recibe como parámetro cada uno de los elementos del array

**Ejemplo:**
```js
var peliculas = ['Batman', 'Batman Begins', 'The Dark Knight', 'The Dark Knight Rises'];

peliculas.forEach((pelicula) => {
  console.log(pelicula);
});

// Batman Begins
// The Dark Knight
// The Dark Knight Rises
```

* En este ejemplo vemos que podemos utilizar el método forEach en el array peliculas
* Le pasamos un function como parámetro como si fuera cualquier otro tipo de parámetro (number, string, etc)
* El parámetro que recibe esta función en este caso le pusimos pelicula ya que estamos recorriendo una colección de peliculas
* Le podemos poner el nombre que queremos al parámetro

**Ejemplo:**
```js
var techsFrontend = ['react', 'vue', 'angular'];

techsFrontend.forEach((tech) => {
  console.log(tech);
});

// react
// vue
// angular
```

* En este caso la colección es de tecnologías por lo cual utilizamos el nombre `tech` para que tenga sentido que cada elemento de la colección es una tecnología. Podríamos utilizar otros como item, elemento o lo que a nosotros nos guste. Siempre es mejor poner un nombre con contexto que explique de forma fácil de que es la colección que estamos iterando y los elementos que estamos utilizando

* Podemos obtener otro parámetro más en la función que se ejecuta por cada elemento que es el índice del elemento

**Ejemplo:**
```js
var playlist = ['Smells Like Teen Spirit', 'Come As You Are', 'Heart-Shaped Box', 'Lithium'];

playlist.forEach((cancion, indice) => {
  console.log('indice', indice);
  console.log(cancion);
});

// indice 0
// Smells Like Teen Spirit
// indice 1
// Come As You Are
// indice 2
// Heart-Shaped Box
// indice 3
// Lithium
```

* Vemos en este ejemplo que agregando un segundo parámetro podemos obtener el índice de los elementos y como primer valor el elemento en sí.


### Map
* El método **map** crea un nuevo **array** con el resultado de la función que le pasamos como parámetros
* Podemos utilizar este método para cambiar los valores que tenemos en un array
* En la función que pasamos como parámetro tenemos que retornar el elemento que queremos en el nuevo array

**Ejemplo:**
```js
var nombres = ["Ada Lovelace", "Hedy Lamarr", "Grace Hopper"];
var nombresMayuscula = nombres.map((nombre) => {
  return nombre.toUpperCase();
});

console.log(nombresMayuscula) // [ 'ADA LOVELACE', 'HEDY LAMARR', 'GRACE HOPPER' ] Todos en mayúscula
console.log(nombres) // [ 'Ada Lovelace', 'Hedy Lamarr', 'Grace Hopper' ] Este array quedó igual que antes
```

* En este ejemplo vemos como podemos utilizar **map** para crear un nuevo array modificando los valores de otro array
* El array original queda intacto

**Ejemplo:**
```js
var numeros = [1, 2, 3, 4];
var triples = numeros.map((numero) => {
  return numero * 3;
});

console.log(triples) // [ 3, 6, 9, 12 ] todos los numeros multiplicados por 3
console.log(numeros) // [ 1, 2, 3, 4 ] este array quedó igual que antes
```

### Filter
* El método **filter** retorna un nuevo **array** utilizando un filtro
* Pasamos una función que retorna verdadero o falso para saber si debemos añadir el nuevo elemento al nuevo array o no

**Ejemplo:**
```js
var notas = [1, 2, 3, 4, 10, 5];
var notasGrosas = notas.filter((nota) => {
  return nota === 10;
});

console.log(notasGrosas); // [10] array con una sola nota grosa
console.log(notas); // [1, 2, 3, 4, 10, 5] array original
```

### Reduce
* El método **reduce** nos permite recorrer un array y obtener un sólo dato como resultado final
* Acepta como primer parámetro una función con dos parámetros
  * Primer parámetro es el acumulador
  * El segundo valor es cada item en el array
* Y reduce tiene un segundo parámetro, opcional, que es el valor inicial del acumulador. Si este parámetro no está, toma como valor inicial el primer elemento del array
* Podemos utilizar el acumulador para ir sumando valores, por ejemplo:

**Ejemplo:**
```js
var notas = [1, 2, 3, 4, 10, 5];
var sumaDeNotas = notas.reduce((total, nota) => {
  return total + nota;
});

console.log(sumaDeNotas); // 25 resultado final de sumar todas las notas
```

**Ejemplo:**
```js
var palabras = ['¡', 'Hola,', 'mundo', '!'];
// en este ejemplo estamos haciendo una reducción del array a un string
const frase = palabras.reduce((acumulador, item) => {
  return acumulador + ' ' + item;
}, 'Frase:');
console.log(frase); // Frase: ¡ Hola, mundo !
```

* A continuación una animación para ver como funciona `reduce` -> [Ver](http://reduce.surge.sh/)
* También podemos usar `reduce` para filtrar, ya que estaríamos haciendo una reducción de ese mismo array
* Por ejemplo, si tenemos un array de números, podemos quedarnos con todos los que son múltiplos de 3

**Ejemplo:**
```js
var numeros = [1, 2, 3, 5, 9, 11, 12, 14, 18];

var multiploDe3 = numeros.reduce((multiplosAcumulados, numero) => {
  // solo si el numero es multiplo de 3, lo agrego al array acumulador
  if (numero % 3 === 0) {
    multiplosAcumulados.push(numero);
  }

  return multiplosAcumulados;
}, []); // este array vacio, es el primer valor que va a tomar nuevas variable acumuladora, que en este ejemplo se llama multiplosAcumulados

console.log(multiploDe3); // [ 3, 9, 12, 18 ]
```


* Podes ver más métodos de array en el [sitio de MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Array)

