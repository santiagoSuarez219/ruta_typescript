# Tabla de contenidos

- [Tabla de contenidos](#tabla-de-contenidos)
- [Modulo 1. Fundamentos de TypeScript](#modulo-1-fundamentos-de-typescript)
  - [TS vs JS](#ts-vs-js)
  - [Configurando nuestro proyecto](#configurando-nuestro-proyecto)
  - [Atrapando bugs](#atrapando-bugs)
  - [El compilador de TypeScript](#el-compilador-de-typescript)
  - [TSConfig](#tsconfig)
    - [Compilacion en TS](#compilacion-en-ts)
  - [Tipos de datos primitivos](#tipos-de-datos-primitivos)
  - [tipos inferidos](#tipos-inferidos)
  - [Numbers](#numbers)
  - [Operaciones](#operaciones)
  - [Uso de variables sin inicializar](#uso-de-variables-sin-inicializar)
  - [Conversion de numeros de tipo string a tipo number](#conversion-de-numeros-de-tipo-string-a-tipo-number)
  - [Binarios y Hexadecimales](#binarios-y-hexadecimales)
  - [Boolean](#boolean)
  - [Strings](#strings)
  - [Arrays](#arrays)
  - [Tipado de arrays en TypeScript](#tipado-de-arrays-en-typescript)
  - [Any](#any)
  - [Union Types](#union-types)
  - [Alias y tipos literales](#alias-y-tipos-literales)
  - [Tipos literales](#tipos-literales)
  - [Alias + tipos literales](#alias--tipos-literales)
  - [Null y Undefined](#null-y-undefined)
  - [Funciones](#funciones)
  - [Retorno de funciones](#retorno-de-funciones)
    - [Retornos tipados en TS](#retornos-tipados-en-ts)
  - [Objetos en funciones](#objetos-en-funciones)
  - [Objetos como tipos](#objetos-como-tipos)
  - [Modulo import y export](#modulo-import-y-export)
  - [Usando librerias que soportan TS](#usando-librerias-que-soportan-ts)
  - [Usando librerías que NO soportan TypeScript](#usando-librerías-que-no-soportan-typescript)
- [Modulo 2. Tipos avanzados y funciones](#modulo-2-tipos-avanzados-y-funciones)
  - [libreria ts-node](#libreria-ts-node)
  - [New Types](#new-types)
    - [Enums](#enums)
    - [Tuplas](#tuplas)
    - [Unknown type](#unknown-type)
    - [Unknown en funciones](#unknown-en-funciones)
    - [Never type](#never-type)
    - [Never type en codigo con errores](#never-type-en-codigo-con-errores)
  - [Funciones](#funciones-1)
    - [Parametros opciones y nullish coalescing](#parametros-opciones-y-nullish-coalescing)
    - [Valores por defencto con el operador OR](#valores-por-defencto-con-el-operador-or)
    - [Nullish-coalescing para asignar valores por defecto](#nullish-coalescing-para-asignar-valores-por-defecto)
  - [Parametros por defecto](#parametros-por-defecto)
  - [Parametros rest](#parametros-rest)
  - [Sobrecarga de funciones: el problema](#sobrecarga-de-funciones-el-problema)
    - [Un problema que puede resolver la sobrecarga de funciones](#un-problema-que-puede-resolver-la-sobrecarga-de-funciones)
    - [Solucion con sobrecarga de funciones](#solucion-con-sobrecarga-de-funciones)
  - [Interfaces](#interfaces)
  - [Interfaces vs Type](#interfaces-vs-type)
  - [Estructuras complejas](#estructuras-complejas)
  - [Extender interfaces](#extender-interfaces)
  - [Herencia de interfaces en TS](#herencia-de-interfaces-en-ts)
  - [Propiedades de solo lectura](#propiedades-de-solo-lectura)
  - [CRUD](#crud)
  - [Omit y Pick Type](#omit-y-pick-type)
    - [Proyecto](#proyecto)
  - [Partial y Required Type](#partial-y-required-type)
    - [Proyecto](#proyecto-1)
  - [Readonly Type](#readonly-type)
  - [Proyecto](#proyecto-2)
  - [Acceder al tipado por indice](#acceder-al-tipado-por-indice)
    - [Proyecto](#proyecto-3)
  - [ReadonlyArray Type](#readonlyarray-type)
    - [Proyecto](#proyecto-4)
- [Modulo 3. Programacion Orientada a Objetos](#modulo-3-programacion-orientada-a-objetos)
  - [Fundamentos de POO](#fundamentos-de-poo)
    - [Clases](#clases)
    - [Métodos](#métodos)
  - [Acceso publico y privado](#acceso-publico-y-privado)
  - [Constructores](#constructores)
  - [Getters y Setters](#getters-y-setters)
  - [Herencia](#herencia)
  - [Acceso protegido](#acceso-protegido)
  - [Static](#static)
  - [Interfaces](#interfaces-1)
  - [Clases abstractas](#clases-abstractas)
  - [Singleton: constructor privado](#singleton-constructor-privado)
  - [Asincronismo](#asincronismo)
    - [Promesas](#promesas)
  - [Tipando respuestas HTTP](#tipando-respuestas-http)
  - [Consumiento ProductMemoryService](#consumiento-productmemoryservice)
  - [Creando ProductHttpService](#creando-producthttpservice)
  - [Consumiendo ProductHttpService](#consumiendo-producthttpservice)
  - [Genericos](#genericos)
  - [Generics en clases](#generics-en-clases)
  - [Generics en metodos](#generics-en-metodos)
  - [Decoradores](#decoradores)

# Modulo 1. Fundamentos de TypeScript

TypeScript es un superset de JavaScript, pues sobre este lenguaje se añaden características adicionales como por ejemplo el tipado estático que no viene por defecto en JS.

- Según un estudio, TypeScript puede prevenir hasta un 15% de fallas en tus proyectos. TypeScript va a estar analizando tu código constantemente indicando posibles fallas o mejores maneras de escribir tu código.
- Según Octoverse 2021, una encuesta que realiza GitHub a sus desarrolladores en la que mide la percepción de ciertos lenguajes, TypeScript ha tenido una acogida creciente desde el 2017 hasta el 2021

![05](https://static.platzi.com/media/articlases/Images/cft-1.jfif)

- NPM Trends nos dice, basado en la descarga de paquetes, que TypeScript está siendo usado por muchas librerías y proyectos en todo el ecosistema JavaScript

![06](https://static.platzi.com/media/articlases/Images/cft-2.jfif)

- TypeScript en la encuesta de Stack Overflow de 2020 quedó como el segundo lenguaje más amado por los desarrolladores

![07](https://static.platzi.com/media/articlases/Images/ctf-3.jfif)

**Testimonios**

- Según VueJS, puede evitar varios errores que podrían ir a producción
- ReactJS nos dice que puede prevenir muchos problemas antes de correr el código
- Slack indica que tiene una gran integración con el editor, incrementando la productividad de los desarrolladores
- Airbnb comenta que le ayudó a prevenir hasta un 38% de bugs y que los ingenieros pueden avanzar más rápido y seguro

## TS vs JS

¿TypeScript es diferente a JavaScript? ¿Un desarrollador en TypeScript es diferente a uno en JavaScript? La respuesta a ambas es sí, sin embargo, no hay una notable diferencia. Uno (TypeScript) se base en el otro (JavaScript) añadiendo elementos para mejorar la detección de bugs y experiencia de desarrollo.

JavaScript ha sufrido un incremento exponencial en su uso, pues se puede usar en Frontend, Backend, IoT, entre otros. No obstante, este no fue creado como un lenguaje maduro desde el inicio, fue con el tiempo que ha ido mejorando hasta lo que es hoy en día.

En JavaScript solo te das cuenta de que tienes un error hasta el momento en que lo ejecutas, sea en el navegador o en un entorno de ejecución como NodeJS, más no antes. Lo que queremos como desarrolladores es obtener retroalimentación lo antes posible para tener la menor cantidad de errores en producción

TypeScript abarca todo lo que tiene JavaScript, más las nuevas versiones de ECMAScript, y añade análisis estático a nuestro código.

**Analisis de codigo estatico**

`Entre más rápido encuentres un error, más fácil será solucionarlo`

En el libro Software Engineering at Google[1] señalan ciertas capas para detectar fallas en el desarrollo de programas:

- Análisis de código estático: corre en el editor de código en busca de un typo (error en la escritura de un término), llamadas incorrectas a funciones y brinda autocompletado de código
- Pruebas Unitarias (Unit Tests): se realiza pruebas para verificar si una parte del código hace lo que queremos que ejecute
- Pruebas de Integración (Integration Tests): vemos como todo el código funciona en conjunto y que se ejecute cómo deseamos
- Revisión de código (Code Review): se verifica si se ha seguido con las normas, estándares y mejores prácticas establecidas por el equipo
- [1] Sofware Engineering at Google. Lessons Learned from Programming Over Time - Titus Winters, Tom Manshreck y Hyrum Wright

## Configurando nuestro proyecto

1. Crear un proyecto de node

```bash
npm init
```

2. Instalar typescript de forma local

```bash
npm install typescript --save-dev
```

3. Para saber la version de ts, ejecutar el siguiente comando

```bash
npx tsc --version
```

## Atrapando bugs

1. Crear un archivo demo.js

```js
(()=> {
  const myCart = [];
  const products = [];
  const limit = 2;

  async function getProducts() {
    const rta = await fetch('http://api.escuelajs.co/api/v1/products', {
      mehtod: 'GET'
    });
    const data = await rta.parseJson();
    products.concat(data);
  }
  function getTotal() {
    const total = 0;
    for (const i = 0; i < products.length(); i++) {
      total += products[i].prize;
    }
    return total;
  }
  function addProduct(index) {
    if (getTotal <= limit) {
      myCart.push(products[index]);
    }
  }

  await getProducts();
  addProducto(1);
  addProducto(2);
  const total = getTotal();
  console.log(total);
  const person = {
    name: 'Nicolas',
    lastName: 'Molina'
  }
  const rta = person +  limit;
  console.log(rta);
});
```

Al analizarlo nos damos cuenta de que tiene unos errores que podrían pasar desapercibidos al no ver advertencias. Es hasta que lo ejecutamos en un navegador web o entornos como NodeJS que los bugs saldrán a relucir. Por lo que, nosotros como desarrolladores, esto no es conveniente, pues queremos feedback lo más pronto posible.

**Activando poderes de TypeScript en JS**

Si estás en Visual Studio Code, puedes activar el analizador de código estático de TypeScript sobre un archivo JavaScript. Para esto, en la primera línea del archivo debe ir lo siguiente:

```js
// @ts-check
```

Al hacer esto, VSCode nos mostrará advertencias de errores en nuestro código JavaScript.

## El compilador de TypeScript

Por defecto, los navegadores y node no reconocen ts, por lo que debemos convertirlo a js.

El compilador de TypeScript es una herramienta que nos permite convertir código TypeScript a JavaScript. Para esto, debemos ejecutar el siguiente comando:

1. Crear un archivo 01_hello.ts

```ts
const myName = "Santiago";
console.log(myName);
```

2. Ejecutar el compilador de ts

```bash
npx tsc 01_hello.ts
```

Puedes ver que se ha creado un archivo 01_hello.js, el cual es el resultado de la compilación de TypeScript.

**Compilación a una versión específica**

El compilador de TypeScript nos permite compilar a una versión específica de JavaScript. Para esto, debemos ejecutar el siguiente comando:

```bash
npx tsc archivo_typescript.ts --target es6
```

**Enviando compilacion a una carpeta**

Si deseas que los archivos transpilados no se generen en la misma carpeta donde están tus archivos TypeScript, puedes indicarle al compilador hacia donde quieres que vayan:

```bash
npx tsc archivo_typescript.ts --target es6 --outDir carpeta_destino
```

por lo general, se crea un directorio llamado dist para almacenar los archivos transpilados.

También podrías indicar que deseas aplicar la anterior operación a todos los archivos con extensión TypeScript:

```bash
npx tsc *.ts --target es6 --outDir carpeta_destino
```

## TSConfig

Nos ayuda a ahorrar mucho trabajo manual como transpilar archivo por archivo, indicar el target, etc.

Para crear un archivo de configuración de TypeScript, debemos ejecutar el siguiente comando:

```bash
npx tsc --init
```

Nos creará automáticamente el archivo con propiedades básicas activadas:

![tsconfig](https://static.platzi.com/media/articlases/Images/tsconfigjson1light.png)

Dentro del archivo TSConfig.json podemos ver que tiene muchas propiedades comentadas (desactivadas) y de las cuales solo algunas están activadas.

Podemos activar las siguiente propiedades dentro de dicho archivo

```javascript
"outDir": "./dist", // Indica la carpeta donde se almacenarán los archivos transpilados
"rootDir": "./src", // Indica la carpeta donde se encuentran los archivos TypeScript
```

### Compilacion en TS

Nuestro código TypeScript se transpilará según las propiedades indicadas en nuestro archivo `TSConfig.json`:

```bash
npx tsc
```

Nos puede resultar tedioso estar ejecutando el comando anterior siempre después de escribir nuestro código. Para evitar esto, podemos hacer que el compilador esté detectando cada cambio que realicemos en nuestros archivos TypeScript y haga la transpilación de inmediato:

```bash
npx tsc --watch
```

## Tipos de datos primitivos

El tipado en TypeScript hace referencia a cómo declaramos una variable, necesitamos asignar el tipo de dato, conocido como type annotation, con esto evitamos mezclar distintos tipos de datos. Nosotros podemos declarar una variable de un tipo de valor y a lo largo del código ir cambiándolo si lo deseamos. Por lo que en un momento puede ser de tipo string y después de tipo boolean:

![01](https://static.platzi.com/media/articlases/Images/tsl.jpg)

Para proyectos de sofware que tienen una gran escalabilidad, esto podría ser fuente de fallas en el programa. Gracias a TypeScript podemos manejar el tipado de las variables para evitar anomalías en el código. En JavaScript, para declarar una variable constante lo realizamos así:

```js
const productPrice = 12;
```

En TypeScript, para el caso anterior, es similar solo que añadimos : y el tipo de dato de la variable, la cual sería number. A esto último se le llama type annotation o anotación de tipo:

```ts
const productPrice: number = 12;
```

## tipos inferidos

TypeScript puede inferir el tipo de dato de una variable a pesar de no haberlo declarado explícitamente.

A partir de la inicialización de la variable TypeScript infiere el tipo que será a lo largo del código y este no puede variar. Por ejemplo:

```ts
let myName = "Santiago";
```

Si bien no indicamos el tipo de dato como se haría de esta manera:

```ts
let myNmae: string = "Santiago";
```

TypeScript infiere que la variable myName será del tipo string y en adelante no podrá tomar un valor que no sea de este tipo de dato. Por lo tanto el siguiente código nos dará un error:

```ts
myName = 12;
```

En Visual Studio Code puedes obtener autocompletado teniendo sugerencias según el tipo de dato que sea la variable:

![02](https://static.platzi.com/media/articlases/Images/ts6l.png)

**Nombres de variables iguales**
TypeScript te indicará como error aquellas variables con el mismo nombre a pesar de estar en archivos distintos. Esto no sucederá en entornos preconfigurados como por ejemplo Angular o React, ya que estos trabajan de forma modular o tienen un alcance (scope) para cada variable.

Si deseas trabajar con los mismos nombres de variables en diferentes archivos, puedes crear una función anónima autoejecutada:

```ts
(() => {
  let myName = "Victoria";
})();
```

Lo mismo por cada variable que desees tener el mismo nombre (myName para este ejemplo) deberás crear este tipo de función para evitar que te den estas advertencias.

## Numbers

El tipo de dato number se usa para variables que contendrán números positivos, negativos o decimales.

## Operaciones

En JS, una variable de tipo number puede facilmente ser concatenada con un string, por ejemplo:

```js
let myNumber = 30;
myNumber = myNumber + "5"; // Devuelve 305
```

Sin embargo, esto podria llevar a confusiones y errores durante la ejecucion del programa, ademas de estar cambiando el tipo de dato de la variable. Por ello, en TS solo se pueden hacer operaciones numericas entre numeros y no con strings.

```ts
let myNumber: number = 30;

myNumber = myNumber + 10; // Correcto
myNumber = myNumber + "5"; // Error
```

## Uso de variables sin inicializar

Seran indicados como errores aquellas variables que no hayan sido inicializadas, por ejemplo:

```ts
let productInStock: number;
console.log(productInStock); // Error
```

Cabe resaltar que si no se va a inicializar aun la variable, debemos indicar el tipo de dato, pues ts, no puede inferirlo

## Conversion de numeros de tipo string a tipo number

Para esto usaremos el metodo parseInt:

```ts
let discount: number = parseInt("50");

let numeroString: string = "100";
let nuevoNumero: number;
nuevoNumero = parseInt(numeroString);
```

Esto funciona si el string tiene solo y exclusivamente numeros que no empiecen con 0, de lo contrario, nos dara un NaN (Not a Number)

```ts
let numeroPrueba: number = parseInt("palabra");
console.log(numeroPrueba); //NaN
```

## Binarios y Hexadecimales

TypeScript nos puede indicar error si intentamos definir números binarios que tengan números que no sean 0 o 1 y si declaramos hexadecimales usando valores fuera del rango:

```ts
//**********TypeScript**********
//Binarios: se definen colocando "0b" al inicio del valor
let primerBinario = 0b1010; //CORRECTO
let segundobinario = 0b1210; //INCORRECTO. El 2 es inválido

//Hexadecimales: se definen colocando "0x" al inicio del valor
let primerHexa = 0xfff; //CORRECTO
let segundoHexa = 0xffz; //INCORRECTO. El "z" es inválido
```

En consola, si estan correctamente asignados, se hara una conversion a decimal de dichos numeros:

```ts
let primerHexa = 0xfff;
console.log(primerHexa); // 4095

let primerBinario = 0b1010;
console.log(primerBinario); // 10
```

**Consejo**
Cuando definas una variable de tipo de dato number, es preferible que el nombre de tipo sea en minúscula. Esto como buena práctica, pues se hará referencia al tipo de dato number y no al objeto Number propio del lenguaje:

```ts
let myNumber: number = 20; // Buena practica.
let otherNumber: Number = 20; // Mala practica.
```

## Boolean

Este tipo de dato puede tomar dos valores: true o false.

**Ejemplo**

```ts
(() => {
  let isEnable = true;
  //  isEnable = 'as';
  //  isEnable = 1212;
  isEnable = false;

  let isNew: boolean = false;
  console.log("isNew", isNew);
  isNew = true;
  console.log("isNew", isNew);

  const random = Math.random();
  console.log("random", random);
  isNew = random >= 0.5 ? true : false;
  console.log("isNew", isNew);

  const myBoolean: boolean = true;
})();
```

## Strings

Este tipo de dato nos permite almacenar una cadena de caracteres. Podemos definir un string con:

1. Comillas simples

```ts
let myProduct = 'Soda'; //CORRECTO
let comillasDobles = 'Puedo "usar" comillas dobles tambien'; //CORRECTO
let comillaInvalida = 'No puedo 'usar' otra vez una comilla simple'; //INCORRECTO
```

2. Comillas dobles

```ts
let myProduct = "Soda"; //CORRECTO
let comillaSimple = "Puedo 'usar' comilla simple tambien"; //CORRECTO
let comillaInvalida = "No puedo "usar" otra vez las comillas dobles"; //INCORRECTO
```

3. Backticks

```ts
let myName = `Frank`;

let texto = `
    Nunca
    pares
    de aprender :)
`;

let variableTitulo = "TypeScript";
let summary = `
    title: ${variableTitulo}
`;

let html = `
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
  </head>
  <body>
    ...
  </body>
</html>
`;
```

## Arrays

Es una colección de datos ordenada. Los definimos de la siguiente manera:

```ts
let prices = [1, 2, 3, 4, 5];

/* Método Push para agregar un elemento al final del array */
prices.push(6);
console.log(prices); // [1,2,3,4,5,6]
```

Para el array prices, TypeScript, de no indicarle explícitamente, va a inferir que este solo contendrá valores del tipo number, por lo que si se quiere agregar un valor string, por ejemplo, nos indicará un error:

```ts
prices.push("texto"); //ERROR. Se espera agregar solo números al array.
```

Esto debido a que en su inicialización se le asignó un array que solo contenía números.

También nos indicará error si pretendemos hacer operaciones exclusivas de un tipo de dato sobre la de otro tipo:

```ts
let meses = ["Mayo", "Junio", "Julio"];
meses.map((item) => item * 2); //ERROR. Se pretende realizar una multiplicación usando strings.
```

## Tipado de arrays en TypeScript

Lo puedes definir así:

- Indicar explícitamente los tipos de datos que almacenará el array:

```ts
let prices: (number | string)[] = ["hola", 2, 4, 6, "mundo"];
let otherPrices: (boolean | number)[];
```

Para este caso, a menos que la variable sea una constante, no es necesario que inicialices la variable, pues ya le indicaste el tipo de dato.

- En la inicialización de la variable, colocar datos con el tipo de dato que quieres que soporte tu array en adelante para que lo pueda inferir TypeScript:

```ts
let prices = ["hola", 2, 4, 6, "mundo"];
// "hola", "mundo" => string
// 2,4,6 => number
```

## Any

Es un tipo de dato exclusivo de TypeScript. Su traducción sería “cualquiera”, pues literalmente nos permite almacenar cualquier tipo de dato en una variable:

```ts
let myDynamicVar: any;

myDynamicVar = 100; // number
myDynamicVar = null;
myDynamicVar = {}; // Object
myDynamicVar = ""; // string
myDynamicVar = true; // boolean
```

Se recomienda no usar este tipo de dato, pues se considera **mala práctica**. La utilidad de any radica cuando se quiere migrar de a pocos a TypeScript desde JavaScript, ya que incrementalmente definiríamos el tipo de dato donde sea necesario sin romper nuestro programa de golpe.

**Tratar Any como un primitivo**

Se pueden realizar conversiones a tipos de datos primitivos de JavaScript:

```ts
//Caso 1
myDynamicVar = "HOLA";
const otherString = (myDynamicVar as string).toLowerCase();

//Caso 2
myDynamicVar = 1212;
const otherNumber = (<number>myDynamicVar).toFixed();
```

Como observamos, podemos tratar nuestra variable any como string en el primer caso y como number en el segundo. Después de esto, podemos acceder a los métodos toLowerCase() y toFixed() según el tipo de dato correspondiente.

## Union Types

Nos permite definir más de un tipo de dato a una variable, argumento de una función, etc. Se definen de la siguiente manera:

```ts
let userId: string | number;

userId = 10;
userId = "10";

function helloUser(id: string | number) {
  console.log(`Hola usuario con el número de id ${id}`);
}
```

Aquí indicamos que id y userId pueden ser de tipo string o number.

El tipo de dato any nos brinda la flexibilidad de JavaScript en TypeScript con respecto al tipado. Sin embargo, si deseamos eso, es mejor hacer uso de los Union Types.

## Alias y tipos literales

Los Alias nos permiten darle un nombre a uno o varios tipos de datos en conjunto. Un ejemplo de como se definen sería así:

```ts
type UserID = string | boolean | number;
```

¡Ahora UserID lo podemos usar como si fuese un tipo de dato string, boolean o number!

```ts
let dynamicVar: UserID = "300";

dynamicVar = true;
dynamicVar = 200;
```

Los Union Types que vayamos a utilizar ahora serán menos tediosos de escribir, pues con los Alias podemos utilizar el mismo conjunto de tipos de datos en la definición de varias variables, beneficiándonos en escribir menos código

```ts
type UserID = string | boolean | number;

let dynamicVar: UserID = "300";

function helloUser(userId: UserID) {
  console.log(`Un saludo al usuario con el número de id ${userId}`);
}
```

**Nota:** la palabra type en los Alias es algo propio de TypeScript.

## Tipos literales

Gracias a esto podemos definir explícita y literalmente los posibles valores que puede tomar nuestra variable. Por ejemplo:

```ts
let shirtSize: "S" | "M" | "L" | "XL";

shirtSize = "M"; //CORRECTO
shirtSize = "S"; //CORRECTO
shirtSize = "qwrty"; //ERROR. No está en las opciones.
shirtSize = "SS"; //ERROR. Letra de más.
shirtSize = "m"; //ERROR. Está en minúscula.
```

Definimos que la variable shirtSize pueda ser una de las 4 posibles opciones de valores, que estos sean de tipo string y que estén en mayúscula, por tanto, si queremos asignar un valor que no sea exactamente como lo declaramos, TypeScript nos mostrará un error.

## Alias + tipos literales

También podríamos combinarlas para facilitar aún más el desarrollo de nuestro programa:

```ts
type Sizes = "S" | "M" | "L" | "XL";

let shirtSize: Sizes;
shirtSize = "M";

function yourSize(userSize: Sizes) {
  console.log(`Tu medida es ${userSize}`);
}
```

## Null y Undefined

Estos dos funcionan como dos tipos de datos, al igual que, por ejemplo, string o number.

El tipo de dato null es para indicar un valor nulo y undefined para algo indefinido. Son tipos diferentes.

En TypeScript, si no especificamos que va a ser null o undefined, estos son inferidos como tipo any

```ts
let myVar = null; //Tipo any
let otherVar = undefined; //Tipo any

let myNull: null = null; // Tipo null
let myUndefined: undefined = undefined; //Tipo undefined
```

Hay casos en la que queremos que una variable sea de tipo string o number y que al inicializarlas sean de tipo null o undefined para luego asignarles un valor del tipo de dato de los primeros mencionados. En este contexto podríamos usar los Union Types:

```ts
let myNumber: number | null = null;
myNumber = 50;

let myString: string | undefined = undefined;
myString = "Hola TypeScript";
```

## Funciones

Las funciones son nativas de JavaScript y esencialmente funcionan igual en TypeScript. Sin embargo, este último, con su sistema de tipado, nos ayudará a llevar a cabo una implementación más segura:

- Podemos definir que los argumentos de la función tengan un determinado tipo de dato (o más de uno si se usa Union Types):

```ts
type Sizes = "s" | "M" | "L" | "XL"; //Alias y Tipos Literales

function createProductJson(
  title: string,
  createdAt: Date,
  stock: number,
  size: Sizes
) {
  return {
    title,
    createdAt,
    stock,
    size,
  };
}
```

En el argumento createdAt se indica que es de tipo Date en alusión al objeto Date propio de JavaScript y no a un tipo de dato como string o number. Son diferentes las definiciones.

- Cuando hagamos uso de nuestra función, TypeScript comprobará que le envíes todos los parámetros en orden y con el tipo de dato que se declaró en la función:

```ts
const producto1 = createProductJson("titulo", new Date("10/10/3030"), 30, "M");
```

![03](https://static.platzi.com/media/articlases/Images/ts10l.png)

_En Visual Studio Code, si dejas el cursor sobre el nombre de la función que vas a invocar, te mostrará un mensaje con los detalles de la función, lo que espera como parámetros y lo que devolverá indicando además el orden y el tipo de dato de cada variable._

- Si queremos que un argumento sea opcional de enviar, podemos usar el modificador ? junto al nombre del argumento:

```ts
type Sizes = "s" | "M" | "L" | "XL"; //Alias y Tipos Literales

function createProductJson(
  title: string,
  createdAt: Date,
  stock?: number,
  size?: Sizes
) {
  /*Código de la función*/
}
```

**Nota:** cuando definamos argumentos opcionales en una función, estas deben ubicarse al final, si no TypeScript nos indicará un \*\*error, ya que podría haber confusiones al momento de invocar la función y enviar los respectivos parámetros:

```ts
function randomFunc(title: string, amount?: number) {} //CORRECTO

function otherFunc(title?: string, amount: number) {} // ERROR
```

## Retorno de funciones

En TypeScript podemos especificar el tipo de dato del valor que nos retornará una función o indicar si no se devolverá dato alguno:

### Retornos tipados en TS

El tipo de retorno se especificará después de los paréntesis en los que se encuentran los argumentos de la función:

1. Void: Este tipo de función ejecuta ciertas instrucciones, pero no devuelve dato alguno. Estas son conocidas como funciones de tipo void. Se definen así

```ts
function imprimirNombre(yourName: string): void {
  console.log(`Hello ${yourName}`);
}
```

2. Funciones con retorno: Por el contrario, si en la función devolveremos algún valor, podemos especificar el tipo de dato de este:

```ts
function suma(a: number, b: number): number {
  return a + b;
}

function holaMundo(): string {
  return "Hello, World!";
}
```

También los retornos pueden ser más de un tipo de dato:

```ts
function devolverMayor(a: number, b: number): number | string {
  if (a > b) {
    // Retorna un número
    return a;
  } else if (b > a) {
    // Retorna un número
    return b;
  } else {
    // Retorna un string
    return `Los números ${a} y ${b} son iguales`;
  }
}
```

Si no indicamos en nuestra declaración de la función el tipado del retorno, TypeScript, al igual que con las variables, lo puede inferir según si retornas datos (sea string, number, etc.) o si nada es devuelto (tipo void).

## Objetos en funciones

Nuestras funciones pueden recibir objetos como argumentos. En TypeScript también podemos declarar el tipado de estos. Veamos un ejemplo:

```ts
function imprimirDatos(data: { username: string; email: string }): void {
  console.log(
    `Tu nombre de usuario es ${data.username} y tu email es ${data.email}`
  );
}

imprimirDatos({
  username: "freddier",
  email: "freddy@email.com",
});
```

En el ejemplo, el nombre data hace referencia al objeto que recibirá la función imprimirDatos. Por ello, para acceder al valor de username lo definimos en el console.log como data.username y para el email como data.email, pues así es como se accede a las propiedades de un objeto.

Finalmente, cuando invocamos imprimirDatos y queremos enviar el objeto que nos pide como parámetro, simplemente se colocará entre llaves los atributos del mismo sin colocar un nombre de referencia como data tal como lo hicimos en la definición de la función.

## Objetos como tipos

En TypeScript también podemos usar los Alias para definir la estructura de tipado que debería tener un objeto:

```ts
type userData = {
  username: string;
  email: string;
};
```

Y luego este “nuevo tipo” puede ser usado en un array, por ejemplo, para definir el tipado de los objetos que queramos añadir:

```ts
type userData = {
  username: string;
  email: string;
};

let usersList: userData[] = [];

usersList.push({
  username: "freddier", //CORRECTO
  email: "freddy@email.com", //CORRECTO
});
usersList.push({
  username: "cvander", //CORRECTO
  email: true, // ERROR. Debe ser de tipo string y NO de tipo boolean
});
```

## Modulo import y export

Nuestro código puede ser dividido en varios módulos (archivos), por lo que para poder usar las funciones o variables que existen en uno y queramos acceder desde otro, utilizamos import y export. Para exportar una función, variable o clase, simplemente se coloca la palabra reservada export antes de la declaración de la misma:

```ts
export function suma(a: number, b: number): number {
  return a + b;
}

export function resta(a: number, b: number): number {
  return a - b;
}

export let numerosRandom = [1, 30, 40, 50];
export type Sizes = "S" | "M" | "L" | "XL";
```

Como observamos, tenemos un archivo llamado funciones.ts la cual contiene dos funciones: suma y resta. Si estas queremos usarlas desde otro archivo, necesitamos usar la palabra reservada export justo antes de definir nuestra función (lo mismo aplica para las variables). De esta forma indicamos que serán exportados para ser utilizados desde otro archivo JavaScript/TypeScript.

Para importar una función, variable o clase, simplemente se coloca la palabra reservada import antes de la declaración de la misma:

```ts
import { suma, resta, Sizes } from "./funciones.ts";
```

Finalmente, las funciones o variables que queramos utilizar desde otro archivo son importadas de la siguiente manera:

1. Usamos la palabra reservada import
2. Entre llaves indicamos las funciones y/o variables que queremos acceder. Hacemos una separación con comas
3. Usamos la palabra reservada from, seguido de, entre comillas dobles o simples, la ruta de la ubicación en la que se encuentra el archivo del cual estamos importando su código.

**Nota:** Si es un módulo TypeScript lo que estamos importando, es importante que en la ruta de los import figure la extensión .ts de dicho archivo. Si es un archivo JavaScript, colocar la extensión .js es opcional.

## Usando librerias que soportan TS

Las librerías que tienen soporte para TypeScript nos facilitan su uso, y más aún si usas editores de código que se integran bien con este “lenguaje”, pues brindan información muy útil como indicar:

- La cantidad de parámetros esperados por una función
- El tipo de datos de los parámetros y variables
- El tipo de dato que retornará la función
- Autocompletado al usar métodos de un módulo
- Mejores prácticas

## Usando librerías que NO soportan TypeScript

El ecosistema de TypeScript ha creado unos módulos para agregar manualmente el tipado a las librerías que no tienen soporte de tipos.

Por ejemplo, si quieres trabajar con la librería lodash, en Visual Studio Code se te indicará que instales un sistema de tipos para que puedas desarrollar sin problemas desde TypeScript:

![04](https://static.platzi.com/media/articlases/Images/lodash-tiny.png)

Para instalar el sistema de tipos, simplemente debes hacer clic en el mensaje que te aparece en el editor de código y se instalará automáticamente o puedes instalarlo de forma manual de esta forma

```bash
npm install --save-dev @types/lodash
```

# Modulo 2. Tipos avanzados y funciones

## libreria ts-node

Acondicionemos nuestro entorno de trabajo con los archivos y configuraciones necesarias para trabajar con TypeScript. Además, haremos uso de la librería ts-node la cual nos va a permitir ejecutar directamente archivos TypeScript en NodeJS sin necesidad de hacer un proceso de transpilación.

1. cree los archivo .editorconfig y .gitignore

```
# Editor configuration, see <https://editorconfig.org>
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
insert_final_newline = true
trim_trailing_whitespace = true

[*.ts]
quote_type = single

[*.md]
max_line_length = off
trim_trailing_whitespace = false
```

2. Instale TS con Node

```bash
npm install typescript --save-dev
```

3. Configuración de TypeScript

```bash
npx tsc --init
```

Recuerde configurar en el archivo tsconfig.json el atributo outDir para que los archivos transpilados se guarden en la carpeta dist. Recuerde tambien crear la carpeta src para todos los archivos TypeScript.

4. Recuerde que puede transpilar de forma constante ante cualquier cambio que hagamos en los archivos TypeScript con el siguiente comando:

```bash
npx tsc --watch
```

5. Instale la librería ts-node

```bash
npm install -D ts-node
```

6. Verifique lo anterior con el siguiente codigo

```ts
type UserId = string | number;
let userId: UserId;

userId = "string";
userId = 1;

console.log("Hoola!" + userId); // 👈
```

7. Ejecute el archivo anterior con el siguiente comando

```bash
npx ts-node src/index.ts
```

## New Types

### Enums

Un enum es un tipo de dato que nos permite crear un set de opciones. Estas opciones son almacenadas bajo una estructura llave-valor similar a un objeto.

```ts
enum ROLES {
  ADMIN = "admin",
  SELLER = "seller",
  CUSTOMER = "customer",
}

type User = {
  username: string;
  role: ROLES;
};

const santiagoUser: User = {
  username: "santiago",
  role: ROLES.ADMIN,
};
```

La ventaja que nos da esto es que disponemos de una lista de valores predeterminados que podemos asignar a una variable o a un atributo de la misma. Por tanto, no podemos asignar otro valor que no este dentro de las opciones que nos brinde el enum:

![01](https://static.platzi.com/media/articlases/Images/06-los-posibles-valores-que-puede-tomar-el-atributo-role-en-la-constante-nicouser-curso-de-typescript-tipos-avanzados-y-funciones.png)

### Tuplas

Las tuplas o tuples nos permiten crear un array fuertemente tipado especificando el tipo de dato de cada elemento, así como una cantidad definida de elementos que podrá almacenar.

Las tuplas no vienen en el conjunto de tipos de datos por defecto de JavaScript.

```ts
const user: [string, number] = ["santiago", 15];
```

Al definir el tipado de cada uno también estamos definiendo la cantidad de valores que tendrá la tupla, por tanto, no podemos agregar más elementos.

```ts
let user: [string, number];

user = ["nico"]; // Error: la tupla debe almacenar 2 valores (un `string` y un `number`)
user = ["nico", true]; // Error: el segundo elemento de la tupla debe ser del tipo `number`
user = ["nico", 20]; // Correcto: el primer elemento es del tipo `string` y el segundo de tipo `number`
```

Podemos aplicar desestructuración para asignar a ciertas variables respectivamente los valores dentro de una tupla.

```ts
const user: [string, number] = ["Santiago", 15];
const [username, age] = user;
console.log(username); // Santiago
console.log(age); // 15
```

### Unknown type

El unknown type nos indica que una variable es de un tipo de dato desconocido. Es similar a any, pero sin quitar el análisis de código estático que nos brinda TypeScript.

El tipo unknown nos fuerza a hacer una verificación de tipo. Esta es la forma que TypeScript sugiere trabajar con variables de las cuales no sabemos de qué tipo serán. Así evitamos utilizar constantemente any.

Con any podemos hacer lo que queramos, no hay restricción alguna, pero con unknown vamos a tener advertencias al momento de utilizar alguna función o método con variables de este tipo.

```ts
let unknownVar: unknown;

unknownVar.toUpperCase(); // Nos marcará el editor una advertencia
```

Por ejemplo, no podemos directamente aplicar un método propio de un string a una variable unknown. Para ello debemos realizar una verificación de tipo para asegurarnos que se ejecutará dicho método siempre cuando unknownVar sea del tipo string en algún punto del programa:

```ts
let unknownVar: unknown;

if (unknownVar === "string") {
  unknownVar.toUpperCase(); // Ahora ya no nos marcará como error.
}
```

### Unknown en funciones

```ts
const parse = (str: string): unknown => {
  return JSON.parse(str);
};
```

### Never type

El never type se usa para funciones que nunca van a terminar o que detienen el programa. Con esto TypeScript nos ayuda a detectarlos como por ejemplo un ciclo infinito cuando lanzamos un mensaje de error.

```ts
const withoutEnd = () => {
  while (true) {
    console.log("Nunca parar de aprender");
  }
};
```

### Never type en codigo con errores

Una función también puede ser del tipo never cuando tenemos un throw que lance un error y, como resultado, haga detener la ejecución.

```ts
const fail = (message: string) => {
  // TypeScript infiere que esta función se de tipo `never`
  throw new Error(message);
};

const example = (input: unknown) => {
  if (typeof input === "string") {
    return "Es un string";
  } else if (Array.isArray(input)) {
    return "Es un array";
  }
  return fail("Not Match"); // Lanzamos un error
};

console.log(example("Hola")); //'Es un string'
console.log(example([1, 1, 1, 1])); // 'Es un array'
console.log(example(1212)); // error: Uncaught Error: Not Match
console.log(example("Hola después del fail")); // NUNCA SE EJECUTA, porque se lanzó un error previamente
```

## Funciones

### Parametros opciones y nullish coalescing

Los parámetros opcionales son aquellos que podemos obviar su envío cuando mandamos datos en una función que requiere argumentos.

El nullish-coalescing nos permite evaluar si una variable está definida, pero si esta es null o undefined, retorna un segundo valor diferente.

Para denotar que un parámetro será opcional usamos el operador ? al lado. Siempre debemos colocar los parámetros opcionales al final.

```ts
const createProduct = (
  id: string | number, // Puede ser de tipo `string` o `number`.
  isNew: boolean,
  stock?: number // PARÁMETRO OPCINAL.
) => {
  return {
    // Retornamos un objeto con los valores pasados como parámetros.
    id,
    stock,
    isNew,
  };
};

console.log(createProduct(1, true)); // { id: 1, stock: undefined, isNew: true }
```

### Valores por defencto con el operador OR

Para evitar tener como retorno valores undefined podríamos emplear el operador lógico || (OR) para asignar un valor por defecto

```ts
const createProduct = (
  id: string | number, // Puede ser de tipo `string` o `number`.
  isNew?: boolean, // PARÁMETRO OPCINAL.
  stock?: number // PARÁMETRO OPCINAL.
) => {
  return {
    // Retornamos un objeto con los valores pasados como parámetros.
    id,
    stock: stock || 10,
    isNew: isNew,
  };
};

console.log(createProduct(1, true)); // { id: 1, stock: undefined, isNew: true }
```

El operador || evalúa si el primer valor es falsy, de serlo retorna un segundo valor, si no es falsy retorna el primero. Los valores que son considerados falsy en JavaScript son:

- String vacío “”
- Número 0
- El valor booleano false

Aquí surge un problema: si nosotros deseáramos mandar como argumento un valor que JavaScript considera falsy, entonces el operador || no tomará en cuenta nuestros valores y los cambiará por los de defecto:

```ts
const createProduct = (
  id: string | number, // Puede ser de tipo `string` o `number`.
  isNew?: boolean, // PARÁMETRO OPCINAL.
  stock?: number // PARÁMETRO OPCINAL.
) => {
  return {
    // Retornamos un objeto con los valores pasados como parámetros.
    id,
    stock: stock || 10,
    isNew: isNew || true,
  };
};

console.log(createProduct(1, false, 0)); // { id: 1, stock: 10, isNew: true }
// 👆 JavaScript retorna los valores por defecto de `isNew` y `stock`
//		y no los que mandamos en los argumentos.
```

Este problema podemos solucionarlo con el nullish-coalescing.

### Nullish-coalescing para asignar valores por defecto

El nullish-coalescing se representa con el operador ??. Esto evalúa si el primer valor está definido, si no lo está, retorna el segundo:

```ts
const createProduct = (
  id: string | number, // Puede ser de tipo `string` o `number`.
  isNew?: boolean, // PARÁMETRO OPCINAL.
  stock?: number // PARÁMETRO OPCINAL.
) => {
  return {
    // Retornamos un objeto con los valores pasados como parámetros.
    id,
    stock: stock ?? 10,
    isNew: isNew ?? true,
  };
};

console.log(createProduct(1, false, 0)); // { id: 1, stock: 0, isNew: false }
```

## Parametros por defecto

Los parámetros por defecto se usan para predefinir valores a los parámetros de una función en caso de no especificar un valor al invocarla.

```ts
// Definición de función
const createProduct = (
  id: string | number,
  isNew: boolean = true, // 👀
  stock: number = 10 // 👀
) => {
  return {
    // Retornamos un objeto con los valores pasados como parámetros.
    id,
    stock,
    isNew,
  };
};

// Impresión en consola
console.log(createProduct(1)); // { id: 1, stock: 10, isNew: true } `stock` y `isNew` por defecto

console.log(createProduct(2, false)); // { id: 1, stock: 10, isNew: false } `stock` por defecto

console.log(createProduct(3, false, 50)); // { id: 1, stock: 50, isNew: false }
```

Podemos usar esto como alternativa al nullish-coalescing.

## Parametros rest

En JavaScript, los parámetros rest nos permiten enviar la cantidad de parámetros que queramos a una función. Se denotan con ... seguido del nombre con el cual identificaremos a estos parámetros:

```js
const myFunction = (...args) => console.log(args);
myFunction();
myFunction(1);
myFunction(2, 3, 4, 5, 6, 7, 8, 9, 09, 12, 32, 45, 56);
```

En TypeScript, podemos definir el tipo de dato que tendrán los parámetros rest:

```ts
import { User, ROLES } from "./01-enum";

const currentUser: User = {
  username: "nicobytes",
  role: ROLES.CUSTOMER,
};

export const checkAdminRole = () => {
  if (currentUser.role === ROLES.ADMIN) {
    return true;
  }
  return false;
};

const rta = checkAdminRole();
console.log("checkAdminRole", rta);

export const checkRole = (role1: string, role2: string) => {
  if (currentUser.role === role1) {
    return true;
  }
  if (currentUser.role === role2) {
    return true;
  }
  return false;
};

const rta2 = checkRole(ROLES.ADMIN, ROLES.SELLER);
console.log("checkRole", rta2);
//
export const checkRoleV2 = (roles: string[]) => {
  if (roles.includes(currentUser.role)) {
    return true;
  }
  return false;
};

const rta3 = checkRoleV2([ROLES.ADMIN, ROLES.SELLER]);
console.log("checkRoleV2", rta3);
//
export const checkRoleV3 = (...roles: string[]) => {
  if (roles.includes(currentUser.role)) {
    return true;
  }
  return false;
};

const rta4 = checkRoleV3(ROLES.ADMIN, ROLES.SELLER, ROLES.CUSTOMER);
console.log("checkRoleV2", rta4);
```

## Sobrecarga de funciones: el problema

Con la sobrecarga de funciones definimos diferentes firmas de una función en la que cada firma puede manejar cierto tipado de entrada y salida. TypeScript decidirá de manera automática qué firma es la correcta para usar basándose en los argumentos enviados y el tipo de datos de estos.

### Un problema que puede resolver la sobrecarga de funciones

Imaginemos que deseamos implementar una función que devuelva un string en el caso de que le envíes un array o que devuelva un array en caso de que le mandes un string como argumento:

```ts
// 1️⃣Si le enviamos un array, nos debe unir cada elemento del array y devolver un string.
// 2️⃣Si le enviamos un string, nos debe separar cada caracter y formar un array como respuesta.
// [N,i,c,o] => 'Nico' ... string[] => string 1️⃣
//  'Nico' => [N,i,c,o] ... string => string[] 2️⃣

function parseStr(input: string | string[]): string | string[] {
  if (Array.isArray(input)) {
    return input.join(""); // string
  } else {
    return input.split(""); // string[]
  }
}

// Llamando a la función...
const rptaArray = parseStr("Nico"); // Entrada: string - Salida: Array
console.log("rptaArray", "Nico =>", rptaArray);

const rptaStr = parseStr(["N", "i", "c", "o"]); // Entrada: array - Salida: string
console.log("rptaStr", "['N','i','c','o'] =>", rptaStr);
```

Definimos la función con un parámetro que puede ser del tipo string o string[] (un array que contiene valores de tipo string) y un retorno que puede ser de igual manera string o string[].

Cuando invocamos la función para enviar los argumentos que deseamos probar, TypeScript no sabe inicialmente qué tipo de dato le estás mandando de manera específica en el código. Por tanto, no podemos acceder en la siguiente línea de código a ningún método propio de un string o un array:

```ts
const rptaArray = parseStr("Nico"); // Entrada: string - Salida: Array
// La salida y por tanto el valor que es asignado a `rptaArray` será un Array.
// Si intentamos aplicar un método propio de los Arrays:
rptaArray.reverse(); // ⛔ ...Nos marcará error 👀

const rptaStr = parseStr(["N", "i", "c", "o"]); // Entrada: array - Salida: string
// La salida y por tanto el valor que es asignado a `rptaStr` será un string.
// Si intentamos aplicar un método propio de los strings:
rptaStr.toLowerCase(); // ⛔ ...Nos marcará error 👀
```

Una posible solución es realizar una pequeña validación de tipos previo a querer ejecutar algún método propio del tipo de dato correspondiente:

```ts
const rptaArray = parseStr("Nico");
// rtaArray.reverse(); ⛔ NO directamente
if (Array.isArray(rtaArray)) {
  //✅ Validación de tipos previamente...
  rtaArray.reverse(); // 👍 Ahora sí nos permite utilizar este método de los arrays.
}
console.log("rtaArray", "Nico =>", rtaArray); // Vemos en consola

const rtaStr = parseStr(["N", "i", "c", "o"]);
// rtaStr.toLowerCase(); ⛔ NO directamente
if (typeof rtaStr === "string") {
  //✅ Validación de tipos previamente...
  rtaStr.toLowerCase(); // 👍 Ahora sí nos permite utilizar este método de los strings.
}
console.log("rtaStr", "['N','i','c','o'] =>", rtaStr); // Vemos en consola
```

### Solucion con sobrecarga de funciones

Para resolver este problema con sobrecarga de funciones debemos declarar 2 firmas adicionales con el mismo nombre de la función: una firma manejará el tipado de entrada/salida como string/string[] y la otra forma de manera viceversa, es decir string[]/string. El parámetro de la función que tendrá la lógica puede manejar el tipado unknown, pues ya estamos dejando declarado previamente los tipados de entrada y salida que manejará la función:

```ts
// SOBRECARGAS:
function parseStr(input: string): string[]; // Entrada: string - Salida: string[]
function parseStr(input: string[]): string; // Entrada: string[] - Salida: string

// Función principal con las instrucciones deseadas y a la que se le aplicarán las sobrecargas:
function parseStr(input: unknown): unknown {}
```

Ahora en la función principal haremos una validación de tipos y según ello retornaremos las respuestas respectivas a lo que se busca como output:

```ts
// SOBRECARGAS:
function parseStr(input: string): string[]; // Entrada: string - Salida: string[]
function parseStr(input: string[]): string; // Entrada: string[] - Salida: string

// Función principal y a la que se le aplicarán las sobrecargas:
function parseStr(input: unknown): unknown {
  if (Array.isArray(input)) {
    return input.join(""); // string
  } else {
    return input.split(""); // string[]
  }
}
```

Finalmente, ya podríamos utilizar los métodos según el tipo de dato de la respuesta obtenida de la función:

```ts
// SOBRECARGAS:
function parseStr(input: string): string[]; // Entrada: string - Salida: string[]
function parseStr(input: string[]): string; // Entrada: string[] - Salida: string

// Función principal y a la que se le aplicarán las sobrecargas:
function parseStr(input: unknown): unknown {
  if (Array.isArray(input)) {
    return input.join(""); // string
  } else {
    return input.split(""); // string[]
  }
}

const rtaArray = parseStr("Nico"); // Salida: array
rtaArray.reverse(); // ✅ Ya podemos acceder a los métodos de un array
console.log("rtaArray", "Nico =>", rtaArray);

const rtaStr = parseStr(["N", "i", "c", "o"]); // Salida: string
rtaStr.toLowerCase(); // ✅ Ya podemos acceder a los métodos de un string
console.log("rtaStr", "['N','i','c','o'] =>", rtaStr);
```

## Interfaces

Las interfaces nos permiten crear moldes de objetos con sus respectivas propiedades y tipado. Para generar interfaces usamos la palabra reservada interface.

```ts
interface Product {
  id: number | string;
  title: string;
  price: number;
  stock: number;
}
```

Si bien podemos hacerlo mismo con type:

```ts
type Product = {
  id: number | string;
  title: string;
  price: number;
  stock: number;
};
```

Existen algunas diferencias que hacen a interface una mejor opción para definir objetos.

## Interfaces vs Type

Veamos la diferencia entre usar interface y type:

- Utilizamos type para definir principalmente tipos primitivos o directos (declaraciones cortas y puntuales), mientras que con una interface definimos una estructura llave-valor de propiedades que describan lo que debe tener un objeto.
- Los interface se pueden fácilmente extender (realizar herencia), mientras que con los type no. Esto los hace más escalables.

```ts
type Sizes = "S" | "M" | "L" | "XL";

interface Product {
  id: number | string;
  title: string;
  price: number;
  stock: number;
  size?: Sizes;
}
```

## Estructuras complejas

1. Crear una carpeta app
2. Crear un archivo main.ts

```ts
import { addProduct } from "./products/product.service";

addProduct({
  id: "1",
  title: "p1",
  createdAt: new Date(),
  stock: 90,
  category: {
    id: "12",
    name: "c1",
  },
});
```

3. Crear una carpeta products, categories, orders, users -> Crear un archivo nombre.model.ts

```ts
import { Category } from "./../categories/category.model";

export type Sizes = "S" | "M" | "L" | "XL";
export interface Product {
  id: string | number;
  title: string;
  createdAt: Date;
  stock: number;
  size?: Sizes;
  category: Category;
}
```

```ts
import { Product } from "./../products/product.model";
import { User } from "./../users/user.model";

export interface Order {
  id: string | number;
  createdAt: Date;
  products: Product[];
  user: User;
}
```

```ts
export interface Category {
  id: string | number;
  name: string;
}
```

```ts
export enum ROLES {
  ADMIN = "admin",
  SELLER = "seller",
  CUSTOMER = "customer",
}

export interface User {
  id: string | number;
  username: string;
  role: ROLES;
}
```

4. Crear el archivo product.service.ts

```ts
import { Product } from "./product.model";

export const products: Product[] = [];

export const addProduct = (data: Product) => {
  products.push(data);
};
```

## Extender interfaces

En TypeScript, la herencia en interfaces permite crear una interfaz nueva basada en otra interfaz existente, heredando sus propiedades y métodos.

## Herencia de interfaces en TS

1. Crear archivo en la carpeta app -> base.model.ts

```ts
export interface BaseModel {
  id: string;
  createdAt: Date;
  updatedAt: Date;
}
```

2. Modificar los modelos de las demas entidades como se muestra en el ejemplo

```ts
import { BaseModel } from "./../base.model";
import { Category } from "./../categories/category.model";

export type Sizes = "S" | "M" | "L" | "XL";
export interface Product extends BaseModel {
  title: string;
  stock: number;
  size?: Sizes;
  category: Category;
}
```

3. Modificar main.ts

```ts
import { addProduct } from "./products/product.service";

addProduct({
  id: "1",
  title: "p1",
  createdAt: new Date(),
  updatedAt: new Date(),
  stock: 90,
  category: {
    id: "12",
    name: "c1",
    createdAt: new Date(),
    updatedAt: new Date(),
  },
});
```

**Otro ejemplo**

```ts
interface Animal {
  nombre: string;
  comer(): void;
}

interface Mascota extends Animal {
  // 👈 Herencia de interfaces
  // Hereda la propiedad `nombre` y el método `comer()` de la interfaz `Animal`
  jugar(): void;
}

class Perro implements Mascota {
  nombre: string;

  constructor(nombre: string) {
    this.nombre = nombre;
  }

  comer() {
    console.log(this.nombre + " está comiendo.");
  }

  jugar() {
    console.log(this.nombre + " está jugando.");
  }
}

const miPerro = new Perro("Firulais");
miPerro.comer(); // "Firulais está comiendo."
miPerro.jugar(); // "Firulais está jugando."
```

En el ejemplo, declaramos una interface llamada Animal con un atributo nombre y un método comer(). Después, implementamos otra llamada Mascota que extiende la interfaz Animal y agrega un nuevo método con el nombre jugar(). La clase Perro implementa la interfaz Mascota, por lo que no solo debe implementar el método jugar(), sino también el atributo nombre y el método comer() que fueron heredados de la interfaz Animal en la interfaz Mascota.

## Propiedades de solo lectura

Las propiedades de solo lectura son atributos de un objeto que solo pueden ser asignadas durante la creación del mismo y no pueden ser cambiados después. Esto asegura que el valor de la propiedad se mantenga constante y no pueda ser cambiado de forma accidental o intencional.

en el archivo base.model.ts

```ts
export interface BaseModel {
  readonly id: string;
  readonly createdAt: Date;
  updatedAt: Date;
}
```

**Otro ejemplo**

```ts
class Persona {
  // SOLO LECTURA 👀
  readonly nombre: string;
  readonly edad: number;
  // ---

  constructor(nombre: string, edad: number) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar() {
    console.log(`Hola, mi nombre es ${this.nombre} y tengo ${this.edad} años.`);
  }
}

const persona = new Persona("Freddy", 35);
persona.saludar(); // ✅"Hola, mi nombre es Freddy y tengo 35 años."

persona.nombre = "Pepe"; // ⛔Error: La propiedad 'nombre' solo se puede leer
persona.edad = 42; // ⛔Error: La propiedad 'edad' solo se puede leer
```

## CRUD

1. product.model.ts

```ts
import { BaseModel } from "./../base.model";
import { Category } from "./../categories/category.model";

export type Sizes = "S" | "M" | "L" | "XL";
export interface Product extends BaseModel {
  title: string;
  image: string;
  description: string;
  stock: number;
  size?: Sizes;
  color: string;
  price: number;
  category: Category;
  isNew: boolean;
  tags: string[];
}
```

2. instalar faker

```bash
npm install @faker-js/faker --save-dev
```

3. main.ts

```ts
import faker from "@faker-js/faker";

import { addProduct, products } from "./products/product.service";

for (let index = 0; index < 50; index++) {
  addProduct({
    id: faker.datatype.uuid(),
    description: faker.commerce.productDescription(),
    image: faker.image.imageUrl(),
    color: faker.commerce.color(),
    size: faker.random.arrayElement(["M", "S", "XL", "L"]),
    price: parseInt(faker.commerce.price(), 10),
    isNew: faker.datatype.boolean(),
    tags: faker.random.arrayElements(),
    title: faker.commerce.productName(),
    createdAt: faker.date.recent(),
    updatedAt: faker.date.recent(),
    stock: faker.datatype.number({ min: 10, max: 100 }),
    category: {
      id: faker.datatype.uuid(),
      name: faker.commerce.department(),
      createdAt: faker.date.recent(),
      updatedAt: faker.date.recent(),
    },
  });
}

console.log(products);
```

4. product.service.ts

```ts
import { Product } from "./product.model";

export const products: Product[] = [];

export const addProduct = (data: Product) => {
  // data.id = 'hksjdhfskdfh';
  // data.createdAt = new Date(1998, 1, 1);
  products.push(data);
};

export const updateProduct = (id: string, changes: Product) => {
  // code
};
```

## Omit y Pick Type

Los tipos Omit y Pick en TypeScript son utility types que te permiten crear un nuevo tipo basado en un tipo existente, pero omitiendo o seleccionando algunas de las propiedades del tipo original.

Utilizamos la siguiente expresión para definir un Omit: Omit<T, K>. Con esto generamos un nuevo tipo que tiene todas las propiedades de T excepto las especificadas en K. Veamos ejemplo en código:

```ts
interface User {
  id: number;
  name: string;
  email: string;
  phoneNumber: string;
}

// Usando `Omit` para omitir ciertas propiedades de la interfaz User
type UserWithoutContact = Omit<User, "email" | "phoneNumber">; // 👈 Nuevo tipo

// `UserWithoutContact` es ahora un tipo con las propiedades `id` y `name`, pero sin `email` ni `phoneNumber`.

let user: UserWithoutContact = {
  id: 1,
  name: "Carlos Araujo",
};

console.log(user); // { id: 1, name: 'Carlos Araujo' }
```

En este caso, hemos usado Omit para excluir las propiedades email y phoneNumber de la interfaz User. Por lo tanto, el nuevo tipo UserWithoutContact solo tiene las propiedades id y name.

Empleamos la siguiente expresión para definir un Pick: Pick<T, K>. Con esto producimos un nuevo tipo que solo tiene las propiedades de T que se especifican en K. Veamos ejemplo en código:

```ts
interface User {
  id: number;
  name: string;
  email: string;
  phoneNumber: string;
}

// Usando `Pick` para seleccionar ciertas propiedades de User
type UserContactInfo = Pick<User, "email" | "phoneNumber">;

// `UserContactInfo` es ahora un tipo con solo las propiedades `email` y `phoneNumber`

let contactInfo: UserContactInfo = {
  email: "user@email.com",
  phoneNumber: "653-951-802",
};

console.log(contactInfo); // { email: "user@email.com", phoneNumber: "653-951-802" }
```

En este caso, hemos empleado Pick para seleccionar las propiedades email y phoneNumber de la interfaz User. Por lo tanto, el nuevo tipo UserContactInfo solo tiene los atributos email y phoneNumber.

### Proyecto

1. product.dto.ts

```ts
import { Product } from "./product.model";

export interface CreateProductDto
  extends Omit<Product, "id" | "createdAt" | "updatedAt" | "category"> {
  categoryId: string;
}

type example = Pick<Product, "color" | "description">;
```

2. product.service.ts

```ts
import faker from "@faker-js/faker";

import { Product } from "./product.model";
import { CreateProductDto } from "./product.dto";

export const products: Product[] = [];

export const addProduct = (data: CreateProductDto): Product => {
  const newProduct = {
    ...data,
    id: faker.datatype.uuid(),
    createdAt: faker.date.recent(),
    updatedAt: faker.date.recent(),
    category: {
      id: data.categoryId,
      name: faker.commerce.department(),
      createdAt: faker.date.recent(),
      updatedAt: faker.date.recent(),
    },
  };
  products.push(newProduct);
  return newProduct;
};

export const updateProduct = (id: string, changes: Product) => {
  // code
};
```

3. main.ts

```ts
import faker from "@faker-js/faker";

import { addProduct, products } from "./products/product.service";

for (let index = 0; index < 50; index++) {
  addProduct({
    description: faker.commerce.productDescription(),
    image: faker.image.imageUrl(),
    color: faker.commerce.color(),
    size: faker.random.arrayElement(["M", "S", "XL", "L"]),
    price: parseInt(faker.commerce.price(), 10),
    isNew: faker.datatype.boolean(),
    tags: faker.random.arrayElements(),
    title: faker.commerce.productName(),
    stock: faker.datatype.number({ min: 10, max: 100 }),
    categoryId: faker.datatype.uuid(),
  });
}

console.log(products);
```

## Partial y Required Type

Los tipos Partial y Required en TypeScript son utility types que te permiten crear un nuevo tipo basado en un tipo existente, pero haciendo que todas las propiedades de ese tipo sean opcionales u obligatorias.

Utilizamos la siguiente expresión para definir un Partial type: Partial<T>. Esto genera un nuevo tipo que tiene todas las propiedades de T, pero cada atributo es opcional. Veamos un ejemplo:

```ts
interface User {
  id: number;
  name: string;
  email: string;
  phoneNumber: string;
}

// Usando `Partial` para hacer todas las propiedades de User opcionales
type PartialUser = Partial<User>;

// `PartialUser` es ahora un tipo con todas las propiedades de `User`, pero cada una de ellas es opcional.

let partialUser: PartialUser = {
  id: 1,
  name: "Benjamin Hernández",
  // Podemos omitir `email` y `phoneNumber` ya que son opcionales en `PartialUser`
};

console.log(partialUser); // { id: 1, name: 'Benjamin Hernández' }
```

Hemos usado Partial para hacer que todas las propiedades de User sean opcionales. Por lo tanto, el nuevo tipo PartialUser tiene las propiedades id, name, email y phoneNumber, pero todas ellas son opcionales.

Empleamos la siguiente expresión para definir un Required type: Required<T>. Esto genera un nuevo tipo que tiene todas las propiedades de T, pero cada atributo es obligatoria. Veamos un ejemplo:

```ts
interface User {
  id: number;
  name: string;
  email?: string;
  phoneNumber?: string;
}

// Usando `Required` para hacer todas las propiedades de User obligatorias
type RequiredUser = Required<User>;

// `RequiredUser` es ahora un tipo con todas las propiedades de `User`, pero cada una de ellas es obligatoria.

let requiredUser: RequiredUser = {
  id: 1,
  name: "Fatima Fernández",
  email: "fatima@email.com",
  phoneNumber: "343-545-789",
  // No podemos omitir `email` y `phoneNumber` ya que son obligatorias en `RequiredUser`
};

console.log(requiredUser); // { id: 1, name: 'Fatima Fernández', email: 'fatima@email.com', phoneNumber: '343-545-789' }
```

Hemos empleado Required para hacer que todas las propiedades de User sean obligatorias. Por lo tanto, el nuevo tipo RequiredUser tiene las propiedades id, name, email y phoneNumber, pero todas ellas son obligatorias.

### Proyecto

1. product.dto.ts

```ts
import { Product } from "./product.model";

export interface CreateProductDto
  extends Omit<Product, "id" | "createdAt" | "updatedAt" | "category"> {
  categoryId: string;
}

export interface UpdateProductDto extends Partial<CreateProductDto> {}
```

2. product.service.ts

```ts
import faker from "@faker-js/faker";

import { Product } from "./product.model";
import { CreateProductDto, UpdateProductDto } from "./product.dto";

export const products: Product[] = [];

export const updateProduct = (
  id: string,
  changes: UpdateProductDto
): Product => {
  const index = products.findIndex((item) => item.id === id);
  const prevData = products[index];
  products[index] = {
    ...prevData,
    ...changes,
  };
  return products[index];
};
```

## Readonly Type

El tipo Readonly en TypeScript es un utility type que te permite crear un nuevo tipo basado en un otro existente, pero haciendo que todas las propiedades de ese tipo sean de solo lectura.

Utilizamos la siguiente expresión para definir un Readonly type: Readonly<T>. Esto genera un nuevo tipo que tiene todas las propiedades de T, pero cada propiedad es de solo lectura, lo que significa que una vez que se asigna un valor a la propiedad, no puede ser cambiado. Veamos un ejemplo:

```ts
interface User {
  id: number;
  name: string;
  email: string;
}

// Usando `Readonly` para hacer todas las propiedades de User de solo lectura
type ReadonlyUser = Readonly<User>;

// `ReadonlyUser` es ahora un tipo con todas las propiedades de `User`, pero cada una de ellas es de solo lectura.

let readonlyUser: ReadonlyUser = {
  id: 1,
  name: "Rosa López",
  email: "rosa@email.com",
};

console.log(readonlyUser); // { id: 1, name: 'Rosa López', email: 'rosa@email.com' }

// Tratar de cambiar una propiedad lanzaría un error
// readonlyUser.name = 'Jennifer Rodríguez'; // ⛔Error
```

Hemos usado Readonly para hacer que todas las propiedades de User sean de solo lectura. Por lo tanto, el nuevo tipo ReadonlyUser tiene las propiedades id, name y email, pero todas ellas son de solo lectura y no pueden ser cambiadas después de la asignación inicial.

## Proyecto

1. product.dto.ts

```ts
import { Product } from "./product.model";

export interface CreateProductDto
  extends Omit<Product, "id" | "createdAt" | "updatedAt" | "category"> {
  categoryId: string;
}

export interface UpdateProductDto extends Partial<CreateProductDto> {}

export interface FindProductDto extends Readonly<Partial<Product>> {}

type example3 = Readonly<Product>;
```

2. product.servive.ts

```ts
import faker from "@faker-js/faker";

import { Product } from "./product.model";
import {
  CreateProductDto,
  UpdateProductDto,
  FindProductDto,
} from "./product.dto";

export const products: Product[] = [];

export const findProducts = (dto: FindProductDto): Product[] => {
  // code
  // dto.color = 'blue';
  // dto.isNew = true;
  return products;
};
```

3. main.ts

```ts
import faker from "@faker-js/faker";

import {
  addProduct,
  products,
  updateProduct,
  findProducts,
} from "./products/product.service";

findProducts({
  stock: 10,
  color: "red",
  createdAt: new Date(),
  isNew: true,
});
```

## Acceder al tipado por indice

Acceder al tipado por índice se hace de una manera muy similar a la cual accedemos a valores en arrays dentro de JavaScript, pero en este caso, aplicado a una interface, enum, entre otros, para acceder al tipo de dato de una propiedad y que dicho tipado sea asignado en otra parte del código.

### Proyecto

1. product.service.ts

```ts
export const updateProduct = (
  id: Product["id"],
  changes: UpdateProductDto
): Product => {
  const index = products.findIndex((item) => item.id === id);
  const prevData = products[index];
  products[index] = {
    ...prevData,
    ...changes,
  };
  return products[index];
};
```

## ReadonlyArray Type

En TypeScript, ReadonlyArray es un tipo que representa una versión de solo lectura de un array. Esto quiere decir que una vez creado un ReadonlyArray, no puedes cambiar sus elementos o su longitud

La sintaxis para crear un ReadonlyArray en TypeScript es la siguiente:

```ts
let nombreArray: ReadonlyArray<tipo> = [...];
```

Veamos cómo puedes utilizarlo con un ejemplo:

```ts
let numbers: ReadonlyArray<number> = [30, 76, 21, 85, 42];

console.log(numbers[3]); // ✅SÍ está permitido, imprime el valor 85
console.log(numbers.length); // ✅SÍ está permitido, imprime 5 que es la longitud del array

//numbers[0] = 10; // ⛔NO permitido porque se intenta modificar un valor en el array
//numbers.push(6); // ⛔NO permitido porque se intenta agregar un nuevo elemento en el array y con ello aumentar su longitud
```

La variable numbers es un array de números de solo lectura. Puedes leer los elementos del array y puedes consultar su longitud, pero no puedes modificar los elementos ni cambiar la longitud de este. Si intentas hacerlo, TypeScript lanzará un error en tiempo de compilación.

### Proyecto

1. product.dto.ts

```ts
export interface FindProductDto
  extends Readonly<Partial<Omit<Product, "tags">>> {
  readonly tags: ReadonlyArray<string>;
}
```

# Modulo 3. Programacion Orientada a Objetos

1. Crear y acceder carpeta ts-poo
2. Crear repositorio con

```bash
git init
```

3. Iniciar proyecto de Node

```bash
npm init -y
```

5. instalar typescript

```bash
npm i -D typescript
```

6. Iniciar proyecto de typescript

```bash
npx tsc --init
```

8. Instalar ts-node

```bash
npm i -D ts-node
```

9. Crear archivo .gitignore y .editorconfig
10. Crea las carpetas src y dist
11. Modifica el archivo TSconfig.json

```js
    "target": "es6",
    "outDir": "./dist",
    "rootDir": "./src",
```

## Fundamentos de POO

### Clases

Las clases nos sirven para construir instancias de objetos. Es un molde para crear objetos.

1. Crear archivo src/01-class.ts

```ts
const date = new Date();
date.getHours();
date.getMinutes();
date.toISOString();

const date2 = new Date(1993, 1, 12); // 0 Enero 11 Dic
date2.getMinutes();
date2.toISOString();
date2.getHours();

console.log(date);
console.log(date2);
```

Ejecutar el archivo anterior

2. Crear clase

```ts
export class MyDate {
  year: number;
  month: number;
  day: number;

  constructor(year: number, month: number, day: number) {
    this.year = year;
    this.month = month;
    this.day = day;
  }
}

const myDate = new MyDate(1993, 1, 12);
console.log(myDate);
const myDate2 = new MyDate(2020, 2, 2);
console.log(myDate2);
```

### Métodos

Los métodos son funciones que se pueden ejecutar en un objeto.

1. Crear archivo src/02-methods.ts

```ts
export class MyDate {
  year: number;
  month: number;
  day: number;

  constructor(year: number, month: number, day: number) {
    this.year = year;
    this.month = month;
    this.day = day;
  }

  printFormat(): string {
    return `${this.day}/${this.month}/${this.year}`;
  }

  add(amount: number, type: "year" | "month" | "day") {
    if (type === "year") {
      this.year += amount;
    } else if (type === "month") {
      this.month += amount;
    } else if (type === "day") {
      this.day += amount;
    }
  }
}

const myDate = new MyDate(1993, 1, 12);
console.log(myDate.printFormat());
myDate.add(3, "day");
console.log(myDate.printFormat());
myDate.add(1, "month");
console.log(myDate.printFormat());
console.log(myDate.day);
console.log(myDate.month);
console.log(myDate.year);
```

## Acceso publico y privado

Por defecto todas las propiedades y métodos de una clase son públicos. Esto quiere decir que se pueden acceder desde cualquier parte de la aplicación.

Si queremos que una propiedad o método sea privado, debemos agregar la palabra reservada `private` antes de la declaración.

1. Crear archivo src/03-access.ts

```ts
export class MyDate {
  private year: number;
  private month: number;
  private day: number;

  constructor(year: number, month: number, day: number) {
    this.year = year;
    this.month = month;
    this.day = day;
  }

  public printFormat(): string {
    const day = this.addPadding(this.day);
    const month = this.addPadding(this.month);
    return `${this.day}/${this.month}/${this.year}`;
  }

  private addPadding(value: number): string {
    if (value < 10) {
      return `0${value}`;
    }
    return `${value}`;
  }

  public add(amount: number, type: "year" | "month" | "day") {
    if (type === "year") {
      this.year += amount;
    } else if (type === "month") {
      this.month += amount;
    } else if (type === "day") {
      this.day += amount;
    }
  }

  getDay(): number {
    return this.day;
  }
}

const myDate = new MyDate(1993, 1, 12);
console.log(myDate.day); // Error
myDate.day = 20; // Error
console.log(myDate.day); // Error

console.log(myDate.printFormat());
myDate.addPadding(3); // Error
myData.getDay();
```

## Constructores

Los constructores son métodos que se ejecutan al momento de crear una instancia de la clase.

1. Crear archivo src/04-constructors.ts

```ts
export class MyDate {
  constructor(
    private year: number = 1993,
    private month: number = 7,
    private day: number = 9
  ) {}

  public printFormat(): string {
    const day = this.addPadding(this.day);
    const month = this.addPadding(this.month);
    return `${this.day}/${this.month}/${this.year}`;
  }

  private addPadding(value: number): string {
    if (value < 10) {
      return `0${value}`;
    }
    return `${value}`;
  }

  public add(amount: number, type: "year" | "month" | "day") {
    if (type === "year") {
      this.year += amount;
    } else if (type === "month") {
      this.month += amount;
    } else if (type === "day") {
      this.day += amount;
    }
  }

  getDay(): number {
    return this.day;
  }
}

const myDate = new MyDate();
console.log(myDate.printFormat());

const myDate2 = new MyDate(2022);
console.log(myDate2.printFormat());

const myDate3 = new MyDate(2022, 3);
console.log(myDate3.printFormat());
```

## Getters y Setters

Los getters y setters son métodos que nos permiten obtener y establecer valores de una propiedad privada.

1. Crear archivo src/05-getters-setters.ts

```ts
export class MyDate {
  constructor(
    private year: number = 1993,
    private _month: number = 7,
    private _day: number = 9
  ) {}

  public printFormat(): string {
    const day = this.addPadding(this._day);
    const month = this.addPadding(this._month);
    return `${this._day}/${this._month}/${this.year}`;
  }

  private addPadding(value: number): string {
    if (value < 10) {
      return `0${value}`;
    }
    return `${value}`;
  }

  public add(amount: number, type: "year" | "month" | "day") {
    if (type === "year") {
      this.year += amount;
    } else if (type === "month") {
      this._month += amount;
    } else if (type === "day") {
      this._day += amount;
    }
  }

  get day(): number {
    //code
    return this._day;
  }

  get isLeapYear(): boolean {
    if (this.year % 400 === 0) return true;
    if (this.year % 100 === 0) return false;
    return this.year % 4 === 0;
  }

  get month(): number {
    return this._month;
  }
  // Por defecto es un metodo void
  set mounth(value: number) {
    if (value < 1 || value > 12) {
      throw new Error("Invalid mounth");
    }
    this._mounth = value;
  }
}

const myDate = new MyDate();
console.log(myDate.printFormat());
myDate.day;
myDate.day = 20; // Error
console.log(myDate.isLeapYear); // Error
myDate.month = 12;
console.log(myDate.printFormat());
myDate.month = 78; // Error
```

## Herencia

La herencia es un mecanismo que nos permite crear clases a partir de otras clases. La clase que hereda se conoce como clase hija y la clase de la que hereda se conoce como clase padre.

1. Crear archivo src/06-inheritance.ts

```ts
export class Animal (){
    constructor(
        private name: string,
        private age: number
    ){}

    move(){
        console.log('Moving...');
    }

    greeting(){
        return `Hello, my name is ${this.name}`;
    }
}

export class Dog extends Animal {
    owner: string;

    constructor(
        name: string,
        public owner: string
    ){
        super(name);
    }

    woof(times: number): void{
        for(let i = 0; i < times; i++){
            console.log('Woof!');
        }
    }
}

const fifi = new Animal('Fifi', 2);
fifi.move();
console.log(fifi.greeting());

const cheis = new Dog('Cheis', 'Nico', 3);
cheis.move();
console.log(cheis.greeting());
cheis.woof(5);
console.log(cheis.owner);
```

## Acceso protegido

El modificador de acceso protected nos permite acceder a las propiedades y métodos de una clase desde sus clases hijas.

1. Crear archivo src/07-protected.ts

```ts
export class Animal (){
    constructor(
        protected name: string,
        private _age: number
    ){}

    move(){
        console.log('Moving...');
    }

    greeting(){
        return `Hello, my name is ${this._name}`;
    }

    protected doSomething(){
        console.log('dooo');
    }
}

export class Dog extends Animal {
    owner: string;

    constructor(
        name: string,
        public owner: string
    ){
        super(name);
    }

    woof(times: number): void{
        for(let i = 0; i < times; i++){
            console.log(`Woof! ${this.name}`);
        }
        this.doSomething();
    }

    move(){
        //code
        console.log('Moving as a dog');
        super.move();
    }
}

const cheis = new Dog('Cheis', 'Nico', 3);
cheis.move();
console.log(cheis.greeting());
cheis.woof(5);
console.log(cheis.owner);
cheis.name = 'Otro nombre'; // Error
cheis.doSomething(); // Error
cheis.move();
```

## Static

El modificador de acceso static nos permite acceder a las propiedades y métodos de una clase sin necesidad de instanciarla.

1. Crear archivo src/08-static.ts

```ts
console.log(Math.PI);
// const math = new Math();
// math.PI;

console.log(Math.max(1, 2, 3, 4, 5, 6, 7, 8, 9, 10));

class MyMath {
  static readonly PI: number = 3.1416;

  static max(...values: number[]): number {
    let max = 0;
    values.forEach((value) => {
      if (value > max) {
        max = value;
      }
    });
    return max;
  }
}

console.log(MyMath.PI);
Math.PI = 3.14; // Error
myMath.PI = 3.14; // Error
myMath.max(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
```

## Interfaces

Las interfaces son un mecanismo que nos permite definir la estructura de un objeto. Las interfaces son únicamente una abstracción de la estructura de un objeto, por lo que no podemos implementar lógica en ellas.

Cada una de las clases que implementen una interfaz deberá implementar los métodos y propiedades definidos en la interfaz.

1. Crear archivo src/09-interfaces.ts

```ts
interface Driver {
  database: String;
  password: String;
  port: number;

  connect(): void;
  disconnect(): void;
  isConnect(name: string): boolean;
}

class PostgresDriver implements Driver {
  constructor(
    public database: String,
    public password: String,
    public port: number,
    private host: number
  ) {}

  connect(): void {
    console.log("Connecting to Postgres...");
  }

  disconnect(): void {
    console.log("Disconnecting to Postgres...");
  }

  isConnect(name: string): boolean {
    return true;
  }
}

class MySQLDriver implements Driver {
  constructor(
    public database: String,
    public password: String,
    public port: number
  ) {}

  connect(): void {
    console.log("Connecting to MySQL...");
  }

  disconnect(): void {
    console.log("Disconnecting to MySQL...");
  }

  isConnect(name: string): boolean {
    return true;
  }
}
```

## Clases abstractas

Las clases abstractas son clases que no se pueden instanciar, es decir, no podemos crear objetos de una clase abstracta. Las clases abstractas se utilizan como clases base para otras clases que sí pueden ser instanciadas.

1. Crear archivo src/10-abstract.ts

```ts
import { Animal, Dog } from "./07-protected";

const animal = new Animal("elite");
animal.greeting();

const cheis = new Dog("Cheis", "Santi");
cheis.greeting();
cheis.woof(2);
```

Si en el archivo 07-protected.ts cambiamos la clase Animal por una clase abstracta, nos dará error en el archivo 10-abstract.ts

Puesto que, no podemos instanciar una clase abstracta.

## Singleton: constructor privado

El patrón de diseño Singleton nos permite crear una única instancia de una clase. Para ello, debemos crear un constructor privado y un método estático que se encargue de crear una instancia de la clase en caso de que no exista una.

1. Crear archivo src/11-singleton.ts

```ts
export class MyService {
  constructor(public name: string) {}

  getName() {
    return this.name;
  }
}

const myService1 = new MyService("service 1");
console.log(myService1.getName());
const myService2 = new MyService("service 2");
console.log(myService2.getName());

console.log(myService1 === myService2); // false

// ejecutar
```

```ts
export class MyService {
  static instance: MyService | null = null;

  private constructor(public name: string) {}

  getName() {
    return this.name;
  }

  static create(name: string) {
    if (MyService.instance === null) {
      console.log("Debiria entrar una vez");
      MyService.instance = new MyService(name);
    }
    return MyService.instance;
  }
}

const myService1 = MyService.create("service 1");
console.log(myService1.getName());
const myService2 = MyService.create("service 2");
console.log(myService2.getName());
const myService3 = MyService.create("service 3");

console.log(myService1 === myService2); // true

// ejecutar
```

## Asincronismo

### Promesas

1. Instalar axios

```bash
npm i axios
```

2. Crear archivo src/12-promises.ts

```ts
(async () => {
  function delay(time: number) {
    const promise = new Promise<string>((resolve) => {
      setTimeout(() => {
        resolve("3 segundos después...");
      }, time);
    });
    return promise;
  }
  console.log("---".repeat(20));
  const rta = await delay(3000);
  console.log(rta);

  //ejecutar
})();
```

```ts
import axios from "axios";

(async () => {
  function delay(time: number) {
    const promise = new Promise<string>((resolve) => {
      setTimeout(() => {
        resolve("string");
      }, time);
    });
    return promise;
  }

  function getProducts() {
    const promise = axios.get("https://api.escuelajs.co/api/v1/products");
    return promise;
  }

  async function getProductsAsync() {
    const rta = await axios.get("https://api.escuelajs.co/api/v1/products");
    return rta.data;
  }

  console.log("---".repeat(10));
  const rta = await delay(3000);
  console.log(rta);
  console.log("---".repeat(10));
  const products = await getProducts();
  console.log(products.data);
  const productsv2 = await getProductsAsync();
  console.log(productsv2);
})();
```

[API platzi](https://api.escuelajs.co/docs/)

## Tipando respuestas HTTP

1. Crear carpeta app
2. Crear carpeta models
3. Crear archivo productModel.ts

```ts
import { Category } from "./categoryModel";

export interface Product {
  id: number;
  title: string;
  price: number;
  description: string;
  category: Category;
  images: string[];
}
```

4. crear archivo categoryModel.ts

```ts
export interface Category {
  id: number;
  name: string;
  image: string;
}
```

5. Crear archivo 01-main.ts

```ts
import axios from "axios";

import { Product } from "./models/product.model";

(async () => {
  // async function getProducts(): Promise<Product[]> {
  //   const { data } = await axios.get<Product[]>('https://api.escuelajs.co/api/v1/products');
  //   return data;
  // }

  // async function getProducts() {
  //   const rta = await axios.get('https://api.escuelajs.co/api/v1/products');
  //   const data = rta.data as Product[];
  //   return data;
  // }

  async function getProducts() {
    const { data } = await axios.get<Product[]>(
      "https://api.escuelajs.co/api/v1/products"
    );
    return data;
  }

  const products = await getProducts();
  console.log(products.map((item) => `${item.id} - ${item.title}}`));
})();
```

[Convert JSON into gorgeous, typesafe code in any language.](https://quicktype.io/)

**Proyecto:migrando de funciones a clases**

[ts: tipos avanzados](https://github.com/platzi/curso-typescript-tipos-avanzados/tree/step-20)

1. Crear carpeta dtos
2. Traer archivos dtos del repo anterior
3. Modificar productDto.ts

```ts
import { Product } from "./../models/productModel";
import { Category } from "./../models/categoryModel";

export interface CreateProductDto extends Omit<Product, "id" | "category"> {
  categoryId: Category["id"];
}

export interface UpdateProductDto extends Partial<CreateProductDto> {}
```

1. Copiar y migrar archivo product.service.ts

```ts
import faker from "@faker-js/faker";

import { Product } from "../models/product.model";
import { CreateProductDto, UpdateProductDto } from "../dtos/product.dto";
import { ProductService } from "../models/product-service.model";

export class ProductMemoryService implements ProductService {
  private products: Product[] = [];

  getAll() {
    return this.products;
  }

  create(data: CreateProductDto): Product {
    const newProduct = {
      ...data,
      id: faker.datatype.number(),
      category: {
        id: data.categoryId,
        name: faker.commerce.department(),
        image: faker.image.imageUrl(),
      },
    };
    return this.add(newProduct);
  }

  add(product: Product) {
    this.products.push(product);
    return product;
  }

  update(id: Product["id"], changes: UpdateProductDto): Product {
    const index = this.products.findIndex((item) => item.id === id);
    const prevData = this.products[index];
    this.products[index] = {
      ...prevData,
      ...changes,
    };
    return this.products[index];
  }

  findOne(id: Product["id"]) {
    return this.products.find((item) => item.id === id);
  }
}
```

## Consumiento ProductMemoryService

1. Crear 02-main.ts

```ts
import { ProductMemoryService } from "./services/product-memory.service";

const productService = new ProductMemoryService();

productService.create({
  title: "Producto 1",
  price: 100,
  description: "bla bla bla",
  categoryId: 12,
  images: [],
});

const products = productService.getAll();
const productId = products[0].id;

productService.update(productId, {
  title: "cambiar nombre",
});

const rta = productService.findOne(productId);
console.log(rta);
```

## Creando ProductHttpService

- product-service.model.ts

```ts
import { CreateProductDto, UpdateProductDto } from "../dtos/product.dto";
import { Product } from "./product.model";

export interface ProductService {
  getAll(): Product[] | Promise<Product[]>;
  update(
    id: Product["id"],
    changes: UpdateProductDto
  ): Product | Promise<Product>;
  create(dto: CreateProductDto): Product | Promise<Product>;
  findOne(
    id: Product["id"]
  ): Product | undefined | Promise<Product | undefined>;
}
```

1. Crear archivo product-http.service.ts

```ts
import axios from "axios";

import { UpdateProductDto, CreateProductDto } from "../dtos/product.dto";
import { ProductService } from "../models/product-service.model";
import { Product } from "../models/product.model";

export class ProductHttpService implements ProductService {
  private url = "https://api.escuelajs.co/api/v1/products";

  async getAll() {
    const { data } = await axios.get<Product[]>(this.url);
    return data;
  }

  async update(id: Product["id"], changes: UpdateProductDto) {
    const { data } = await axios.put(`${this.url}/${id}`, changes);
    return data;
  }

  async create(dto: CreateProductDto) {
    const { data } = await axios.post(this.url, dto);
    return data;
  }

  async findOne(id: Product["id"]) {
    const { data } = await axios.get(`${this.url}/${id}`);
    return data;
  }
}
```

## Consumiendo ProductHttpService

1. Crear archivo 03-main.ts

```ts
import { ProductHttpService } from "./services/product-http.service";

(async () => {
  const productService = new ProductHttpService();

  try {
    console.log("--".repeat(10));
    console.log("getAll");
    const products = await productService.getAll();
    console.log(products.length);
    console.log(products.map((item) => item.price));

    const productId = products[0].id;
    console.log("--".repeat(10));
    console.log("update");

    await productService.update(productId, {
      price: 10000,
      title: "new title",
      description: "new description",
    });
    console.log("--".repeat(10));
    console.log("findOne");

    const product = await productService.findOne(productId);
    console.log(product);
  } catch (error) {
    console.error(error);
  }
})();
```

## Genericos

1. Crear archivo generics.ts

```ts
import { Dog } from "./09-protected";

// function getValue(value: unknown ) {
//   return value;
// }

// function getValue(value: string | number ) {
//   return value;
// }

function getValue<T>(value: T) {
  const array: T[] = [value];
  return value;
}

getValue<number>(12).toFixed();
getValue<string>("12").toLowerCase();
getValue<number[]>([11, 1, 1]).forEach;
const fifi = new Dog("fifi", "nico");
getValue<Dog>(fifi).greeting;
```

## Generics en clases

- app/services/base-http.service.ts

```ts
import axios from "axios";

import { Category } from "./../models/category.model";
import { Product } from "./../models/product.model";

export class BaseHttpService<TypeClass> {
  // data: TypeClass[] = [];

  constructor(private url: string) {}

  async getAll() {
    const { data } = await axios.get<TypeClass[]>(this.url);
    return data;
  }
}

// const service = new BaseHttpService<string>();
// service.getAll()

// const service1 = new BaseHttpService<Category>();
// service1.getAll

(async () => {
  const url1 = "https://api.escuelajs.co/api/v1/products";
  const productService = new BaseHttpService<Product>(url1);

  const rta = await productService.getAll();
  console.log("products", rta.length);

  const url2 = "https://api.escuelajs.co/api/v1/categories";
  const categoryService = new BaseHttpService<Category>(url2);

  const rta1 = await categoryService.getAll();
  console.log("categories", rta1.length);
})();
```

## Generics en metodos

- app/services/base-http.service.ts

```ts
import axios from "axios";
import { UpdateProductDto } from "../dtos/product.dto";

import { Category } from "./../models/category.model";
import { Product } from "./../models/product.model";

export class BaseHttpService<TypeClass> {
  // data: TypeClass[] = [];

  constructor(protected url: string) {}

  async getAll() {
    const { data } = await axios.get<TypeClass[]>(this.url);
    return data;
  }

  async update<ID, DTO>(id: ID, changes: DTO) {
    const { data } = await axios.put(`${this.url}/${id}`, changes);
    return data;
  }
}

// const service = new BaseHttpService<string>();
// service.getAll()

// const service1 = new BaseHttpService<Category>();
// service1.getAll

(async () => {
  const url1 = "https://api.escuelajs.co/api/v1/products";
  const productService = new BaseHttpService<Product>(url1);

  const rta = await productService.getAll();
  console.log("products", rta.length);
  productService.update<Product["id"], UpdateProductDto>(1, {
    title: "asa",
  });

  const url2 = "https://api.escuelajs.co/api/v1/categories";
  const categoryService = new BaseHttpService<Category>(url2);

  const rta1 = await categoryService.getAll();
  console.log("categories", rta1.length);
})();
```

- product-crud.service.ts

```ts
import { UpdateProductDto } from "../dtos/product.dto";
import { Product } from "../models/product.model";
import { BaseHttpService } from "./base-http.service";
import { ProductHttpService } from "./product-http2.service";

export class ProductCRUDService {
  private url = "https://api.escuelajs.co/api/v1/products";
  private http = new ProductHttpService(this.url);

  async update(id: Product["id"], dto: UpdateProductDto) {
    // permisos
    // logica
    return this.http.update(id, dto);
  }
}
```

- product-http2.service.ts

```ts
import { Product } from "../models/product.model";
import { BaseHttpService } from "./base-http.service";

export class ProductHttpService extends BaseHttpService<Product> {
  otroRequest() {
    this.url;
    //code
    //code
  }
}
```

## Decoradores

1. Instalar class validator

```bash
npm i class-validator --save
```

2. Activar la funcion experimentalDecorators en el archivo tsconfig.json
3. category.dto.ts

```ts
import {
  IsEnum,
  IsNotEmpty,
  IsOptional,
  IsUrl,
  Length,
  validate,
  validateOrReject,
} from "class-validator";

import { AccessType, Category } from "../models/category.model";

export interface ICreateCategoryDto extends Omit<Category, "id"> {}
export class CreateCategoryDto implements ICreateCategoryDto {
  @IsNotEmpty()
  @Length(4, 140)
  name!: string;

  @IsUrl()
  @IsNotEmpty()
  image!: string;

  @IsOptional()
  @IsEnum(AccessType)
  access?: AccessType | undefined;
}

(async () => {
  try {
    const dto = new CreateCategoryDto();
    dto.name = "aqwqwqw";
    dto.image = "https://api.escuelajs.co/api/v1/products";
    await validateOrReject(dto);
  } catch (error) {
    console.log(error);
  }
})();
```
