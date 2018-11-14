# Configuracion de Webpack desde CERO para React



## Pasos para crear un entorno de desarrollo de manera personalizada:

1. Creamos carpeta del proyecto.

2. Creamos archivos de webpack, **webpack.dev.config.js** y **webpack.config.js**.

3. Iniciamos el proyecto con **npm init** para crear nuestro **package.json**.

4. Agregamos e Instalamos las **dependencias** que necesitamos para la configuracion de webpack.

5. Configuramos **webpack** (enetry point, direcciones de output a transpilar, loaders, etc).

6. Creamos el fichero **index.js**.

7. Agregamos los scripts en el **package.json** para construir el proyecto (**builders**) y correrlo.

8. Corremos el proyecto usando los scripts.


 
## Ahora vamos a hacer unos cambios iniciales

Por ejemplo estamos usando la configuracion de otro proyecto llamado "invie" asi que lo vamos a cambiar 

```js
    entry: {
      invie: path.resolve(__dirname, 'src/index.js'),
    },
```

Y lo cambiaremos por el nombre que querramos de nuestro proyecto, como no tengo nada claro le pondre archivo proyecto (si, muy creativo)

```js
    entry: {
      "archivo-proyecto": path.resolve(__dirname, 'src/index.js'),
    },
```

Y como dice nuestra configuracion el archivo que **webpack** va a buscar sera **index.js** dentro de una carpeta **src**. Asi que si aun no existe la crearemos. Y no olvidar de tambien cambiar esta linea en nuestro archivo **webpack.dev.config.js**

Otro aspecto importante de este archivo de configuracion es el **output**:

```js
    output: {
      path: path.resolve(__dirname, 'dist'),
      filename: 'js/[name].[hash].js',
      publicPath: path.resolve(__dirname, 'dist')+"/",
      chunkFilename: 'js/[id].[chunkhash].js',
    },
```

Que nos dice esto ? Que el archivo resultante sera almacenado dentro de la carpeta **dist** con otra carpeta llamada **js** la cual guardara este archivo en especifico.

Vamos a probar esto. Agregando un hola mundo pequeño en nuestro **index.js**. Y lo correremos con nuestros scripts los cuales son:

```js
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build:dev": "webpack-dev-server --config ./webpack.dev.config.js",
    "build": "webpack",
    "build:local": "webpack --env.NODE_ENV=local",
    "build:prod": "webpack -p --env.NODE_ENV=production"
  },
```

Y usaremos en especifico el **build:prod**. De esta manera:

```console
$ npm run build:prod
```

Y se debe de haber creado la carpeta correspondiente.

Hasta ahora ya tenemos el setup basico y sabemos unas cuantas cosas indispensables acerca de esto.

## Setear informacion que se pondra en NPM

- Establecer el nombre y apellido con:
```console
npm set init.author.name"Cristian Sotomayor"
```
- Establecer el correo electronico con:
```console
npm set init.author.email"cristian123@gmail.com"
```

- Establecer el usuario de **Twitter**(opcional) con:
```console
npm set init.author.url"https://twitter.com/HolaSoyCristian"
```

Tambien puedes iniciar sesion en **NPM** con:
```console
npm login
```


