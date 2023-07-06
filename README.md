# Tabla de contenidos
- [Tabla de contenidos](#tabla-de-contenidos)
  - [Porque usar TypeScript](#porque-usar-typescript)
    - [Percepcion](#percepcion)
    - [Testimonios](#testimonios)
  - [TS vs JS](#ts-vs-js)
  - [Configurando nuestro proyecto](#configurando-nuestro-proyecto)
  - [Atrapando bugs](#atrapando-bugs)
    - [Activando poderes de TypeScript en JS](#activando-poderes-de-typescript-en-js)
  - [El compilador de TypeScript](#el-compilador-de-typescript)
    - [Compilación a una versión específica](#compilación-a-una-versión-específica)
    - [Enviando compilacion a una carpeta](#enviando-compilacion-a-una-carpeta)
  - [TSConfig](#tsconfig)
    - [Compilacion en TS](#compilacion-en-ts)
  - [Tipos de datos primitivos](#tipos-de-datos-primitivos)
    - [La flexibilidad de JavaScript](#la-flexibilidad-de-javascript)
    - [Controlando la flexibilidad](#controlando-la-flexibilidad)
    - [tipos inferidos](#tipos-inferidos)
  - [Numbers](#numbers)
    - [Operaciones](#operaciones)
    - [Uso de variables sin inicializar](#uso-de-variables-sin-inicializar)
    - [Conversion de numeros de tipo string  a tipo number](#conversion-de-numeros-de-tipo-string--a-tipo-number)
    - [Binarios y Hexadecimales](#binarios-y-hexadecimales)
  - [Boolean](#boolean)
    - [Ejemplo](#ejemplo)
  - [Strings](#strings)
  - [Arrays](#arrays)
    - [Tipado de arrays en TypeScript](#tipado-de-arrays-en-typescript)
  - [Any](#any)
    - [Importancia del Any](#importancia-del-any)
    - [Tratar Any como un primitivo](#tratar-any-como-un-primitivo)
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
    - [Export](#export)
    - [Import](#import)
  - [Usando librerias que soportan TS](#usando-librerias-que-soportan-ts)
  - [Usando librerías que NO soportan TypeScript](#usando-librerías-que-no-soportan-typescript)

## Porque usar TypeScript
Según un estudio, TypeScript puede prevenir hasta un 15% de fallas en tus proyectos. TypeScript va a estar analizando tu código constantemente indicando posibles fallas o mejores maneras de escribir tu código.

### Percepcion 
-  Según Octoverse 2021, una encuesta que realiza GitHub a sus desarrolladores en la que mide la percepción de ciertos lenguajes, TypeScript ha tenido una acogida creciente desde el 2017 hasta el 2021

![05](https://static.platzi.com/media/articlases/Images/cft-1.jfif)

- NPM Trends nos dice, basado en la descarga de paquetes, que TypeScript está siendo usado por muchas librerías y proyectos en todo el ecosistema JavaScript

![06](https://static.platzi.com/media/articlases/Images/cft-2.jfif)

- TypeScript en la encuesta de Stack Overflow de 2020 quedó como el segundo lenguaje más amado por los desarrolladores

![07](https://static.platzi.com/media/articlases/Images/ctf-3.jfif)

### Testimonios
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
- 
[1] Sofware Engineering at Google. Lessons Learned from Programming Over Time - Titus Winters, Tom Manshreck y Hyrum Wright

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

### Activando poderes de TypeScript en JS

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
const myName = 'Santiago';
console.log(myName);
```

2. Ejecutar el compilador de ts
```bash
npx tsc 01_hello.ts
```

Puedes ver que se ha creado un archivo 01_hello.js, el cual es el resultado de la compilación de TypeScript.

### Compilación a una versión específica

El compilador de TypeScript nos permite compilar a una versión específica de JavaScript. Para esto, debemos ejecutar el siguiente comando:

```bash
npx tsc archivo_typescript.ts --target es6
```

### Enviando compilacion a una carpeta
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
El tipado en TypeScript hace referencia a cómo declaramos una variable, necesitamos asignar el tipo de dato, conocido como type annotation, con esto evitamos mezclar distintos tipos de datos.

### La flexibilidad de JavaScript
Nosotros podemos declarar una variable de un tipo de valor y a lo largo del código ir cambiándolo si lo deseamos. Por lo que en un momento puede ser de tipo string y después de tipo boolean:

![01](https://static.platzi.com/media/articlases/Images/tsl.jpg)

Para proyectos de sofware que tienen una gran escalabilidad, esto podría ser fuente de fallas en el programa.

### Controlando la flexibilidad
Gracias a TypeScript podemos manejar el tipado de las variables para evitar anomalías en el código.

En JavaScript, para declarar una variable constante lo realizamos así:

```js
const productPrice = 12;
```

En TypeScript, para el caso anterior, es similar solo que añadimos : y el tipo de dato de la variable, la cual sería number. A esto último se le llama type annotation o anotación de tipo:

```ts
const productPrice: number = 12;
```

### tipos inferidos

TypeScript puede inferir el tipo de dato de una variable a pesar de no haberlo declarado explícitamente.

A partir de la inicialización de la variable TypeScript infiere el tipo que será a lo largo del código y este no puede variar. Por ejemplo:

```ts
let myName = 'Santiago';
```

Si bien no indicamos el tipo de dato como se haría de esta manera:

```ts
let myNmae: string = 'Santiago';
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
( () => {
    let myName = "Victoria";
})();
```

Lo mismo por cada variable que desees tener el mismo nombre (myName para este ejemplo) deberás crear este tipo de función para evitar que te den estas advertencias.

## Numbers
El tipo de dato number se usa para variables que contendrán números positivos, negativos o decimales.

### Operaciones
En JS, una variable de tipo number puede facilmente ser concatenada con un string, por ejemplo:

```js
let myNumber = 30;
myNumber = myNumber + '5'; // Devuelve 305
```

Sin embargo, esto podria llevar a confusiones y errores durante la ejecucion del programa, ademas de estar cambiando el tipo de dato de la variable. Por ello, en TS solo se pueden hacer operaciones numericas entre numeros y no con strings.

```ts
let myNumber: number = 30;

myNumber = myNumber + 10; // Correcto
myNumber = myNumber + '5'; // Error
```

### Uso de variables sin inicializar
Seran indicados como errores aquellas variables que no hayan sido inicializadas, por ejemplo:

```ts
let productInStock: number;
console.log(productInStock); // Error
```

Cabe resaltar que si no se va a inicializar aun la variable, debemos indicar el tipo de dato, pues ts, no puede inferirlo

### Conversion de numeros de tipo string  a tipo number
Para esto usaremos el metodo parseInt:

```ts
let discount: number = parseInt('50');

let numeroString: string = '100';
let nuevoNumero: number;
nuevoNumero = parseInt(numeroString);
```

Esto funciona si el string tiene solo y exclusivamente numeros que no empiecen con 0, de lo contrario, nos dara un NaN (Not a Number)

```ts
let numeroPrueba: number = parseInt("palabra");
console.log(numeroPrueba); //NaN
```

### Binarios y Hexadecimales
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

### Ejemplo
```ts
(() => {
   let isEnable = true;
  //  isEnable = 'as';
  //  isEnable = 1212;
   isEnable = false;

   let isNew: boolean = false;
   console.log('isNew', isNew);
   isNew = true;
   console.log('isNew', isNew);

   const random = Math.random();
   console.log('random', random);
   isNew = random >= 0.5 ? true : false;
   console.log('isNew', isNew);

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

let html= `
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
let prices = [1,2,3,4,5];

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
let meses = ["Mayo","Junio","Julio"];
meses.map( item => item * 2 ); //ERROR. Se pretende realizar una multiplicación usando strings.
```

### Tipado de arrays en TypeScript
Lo puedes definir así:

- Indicar explícitamente los tipos de datos que almacenará el array:

```ts
let prices: (number | string)[] = ["hola",2,4,6,"mundo"];
let otherPrices: (boolean | number)[];
```

Para este caso, a menos que la variable sea una constante, no es necesario que inicialices la variable, pues ya le indicaste el tipo de dato.

- En la inicialización de la variable, colocar datos con el tipo de dato que quieres que soporte tu array en adelante para que lo pueda inferir TypeScript:

```ts
let prices = ["hola",2,4,6,"mundo"];
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

Se recomienda no usar este tipo de dato, pues se considera **mala práctica**.

### Importancia del Any
La utilidad de any radica cuando se quiere migrar de a pocos a TypeScript desde JavaScript, ya que incrementalmente definiríamos el tipo de dato donde sea necesario sin romper nuestro programa de golpe.

### Tratar Any como un primitivo
Se pueden realizar conversiones a tipos de datos primitivos de JavaScript:
```ts
//Caso 1
myDynamicVar = "HOLA";
const otherString = (myDynamicVar as string).toLowerCase();

//Caso 2
myDynamicVar = 1212;
const otherNumber = (<number>myDynamicVar).toFixed()
```

Como observamos, podemos tratar nuestra variable any como string en el primer caso y como number en el segundo. Después de esto, podemos acceder a los métodos toLowerCase() y toFixed() según el tipo de dato correspondiente.

## Union Types
Nos permite definir más de un tipo de dato a una variable, argumento de una función, etc. Se definen de la siguiente manera:

```ts
let userId: string | number;

userId = 10;
userId = "10";

function helloUser(id: string | number){
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

function helloUser( userId: UserID ) {
    console.log(`Un saludo al usuario con el número de id ${userId}`);
}
```

**Nota:** la palabra type en los Alias es algo propio de TypeScript.

### Tipos literales
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

### Alias + tipos literales
También podríamos combinarlas para facilitar aún más el desarrollo de nuestro programa:

```ts
type Sizes = 'S' | 'M' | 'L' | 'XL';

let shirtSize: Sizes;
shirtSize = "M";

function yourSize( userSize: Sizes ){
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
type Sizes = 's' | 'M' | 'L' | 'XL'; //Alias y Tipos Literales

function createProductJson(
    title: string,
    createdAt: Date,
    stock: number,
    size: Sizes
){
   return {
        title,
        createdAt,
        stock,
        size
    }
}
```

En el argumento createdAt se indica que es de tipo Date en alusión al objeto Date propio de JavaScript y no a un tipo de dato como string o number. Son diferentes las definiciones.

- Cuando hagamos uso de nuestra función, TypeScript comprobará que le envíes todos los parámetros en orden y con el tipo de dato que se declaró en la función:

```ts
const producto1 = createProductJson(
    "titulo",
    new Date('10/10/3030'),
    30,
    'M'
)
```

![03](https://static.platzi.com/media/articlases/Images/ts10l.png)

*En Visual Studio Code, si dejas el cursor sobre el nombre de la función que vas a invocar, te mostrará un mensaje con los detalles de la función, lo que espera como parámetros y lo que devolverá indicando además el orden y el tipo de dato de cada variable.*

- Si queremos que un argumento sea opcional de enviar, podemos usar el modificador ? junto al nombre del argumento:

```ts
type Sizes = 's' | 'M' | 'L' | 'XL'; //Alias y Tipos Literales

function createProductJson(
    title: string,
    createdAt: Date,
    stock?: number,
    size?: Sizes
){
    /*Código de la función*/
}
```

**Nota:** cuando definamos argumentos opcionales en una función, estas deben ubicarse al final, si no TypeScript nos indicará un **error, ya que podría haber confusiones al momento de invocar la función y enviar los respectivos parámetros:

```ts
function randomFunc(title: string, amount?: number){} //CORRECTO

function otherFunc(title?: string, amount: number){} // ERROR
```

### Retorno de funciones
En TypeScript podemos especificar el tipo de dato del valor que nos retornará una función o indicar si no se devolverá dato alguno:

#### Retornos tipados en TS
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
    if(a > b){
        // Retorna un número
        return a;
    } else if( b > a ) {
        // Retorna un número
        return b;
    } else {
        // Retorna un string
        return `Los números ${a} y ${b} son iguales`;
    }
}
```

Si no indicamos en nuestra declaración de la función el tipado del retorno, TypeScript, al igual que con las variables, lo puede inferir según si retornas datos (sea string, number, etc.) o si nada es devuelto (tipo void).

### Objetos en funciones
Nuestras funciones pueden recibir objetos como argumentos. En TypeScript también podemos declarar el tipado de estos. Veamos un ejemplo:

```ts
function imprimirDatos( data: { username: string, email: string } ): void {

    console.log(`Tu nombre de usuario es ${data.username} y tu email es ${data.email}`)
    
}

imprimirDatos({
      username: 'freddier',
      email: 'freddy@email.com'
})
```

En el ejemplo, el nombre data hace referencia al objeto que recibirá la función imprimirDatos. Por ello, para acceder al valor de username lo definimos en el console.log como data.username y para el email como data.email, pues así es como se accede a las propiedades de un objeto.

Finalmente, cuando invocamos imprimirDatos y queremos enviar el objeto que nos pide como parámetro, simplemente se colocará entre llaves los atributos del mismo sin colocar un nombre de referencia como data tal como lo hicimos en la definición de la función.

### Objetos como tipos
En TypeScript también podemos usar los Alias para definir la estructura de tipado que debería tener un objeto:

```ts
type userData = {
    username: string,
    email: string
}
```

Y luego este “nuevo tipo” puede ser usado en un array, por ejemplo, para definir el tipado de los objetos que queramos añadir:

```ts
type userData = {
    username: string,
    email: string
}

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
Nuestro código puede ser dividido en varios módulos (archivos), por lo que para poder usar las funciones o variables que existen en uno y queramos acceder desde otro, utilizamos import y export.

### Export
Para exportar una función, variable o clase, simplemente se coloca la palabra reservada export antes de la declaración de la misma:

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

### Import
Para importar una función, variable o clase, simplemente se coloca la palabra reservada import antes de la declaración de la misma:

```ts
import {suma, resta, Sizes} from "./funciones.ts";
```

Finalmente, las funciones o variables que queramos utilizar desde otro archivo son importadas de la siguiente manera:

1. Usamos la palabra reservada import
2. Entre llaves indicamos las funciones y/o variables que queremos acceder. Hacemos una separación con comas
3. Usamos la palabra reservada from, seguido de, entre comillas dobles o simples, la ruta de la ubicación en la que se encuentra el archivo del cual estamos importando su código.

**Nota:**  Si es un módulo TypeScript lo que estamos importando, es importante que en la ruta de los import figure la extensión .ts de dicho archivo. Si es un archivo JavaScript, colocar la extensión .js es opcional.


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




















