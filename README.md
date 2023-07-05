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






