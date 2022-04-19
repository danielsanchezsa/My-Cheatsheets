# Node JS Cheatsheet

- - -

- - -
## TEC
Construcción de software y toma de decisiones (Abril, 2022)
&nbsp;

### Que es Node JS?
- Entorno e ejecución que te permite correr código JS en un ***servidor***.

- Es capaz de recibir y ejecutar  ***múltiples*** ejecuciones "a la vez"
- Funciona con ***módulos***, el cuál son clases de JS, que permite corréos directamente con la ***terminal***.

Para comenzar a usar Node, es necesario inicializarlo en el folder :
```
npm init
```
Una vez hecho esto, se creara un archivo tipo JSON llamado ***package.json***


#### Configuraciones iniciales
Se tiene que agregar al valor de ***start***

```javascript
{
  "name": "modules_1",
  "version": "1.0.0",
  "description": "",
  "main": "module1file.js",

  "type": "module",
  "scripts": {
    "start":"node module1file.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}
```
Lo que esto hace, es declarar que al usar el comando *npm start*, va a correr automaticamente esa línea de comando, el cual va a correr module1file.js con node

&nbsp;


#### Importar módulo a HTML
```HTML
<script type="module" src="/module1.js"></script>
```

#### Correr Archivos

```
node {FILE_NAME}.js
node tester.js
```
&nbsp;


#### Módulos

Para poder usar módulos, es necesario exportarlos en el mismo archivo:
```javascript
class student{
    constructor(name, id){
        this.name = name;
        this.id = id;
    }
}
export default student;
```

Al inicio JS no ofrecía modulos, por lo que Node hizo los suyos. 

#### Importar Módulos Node
```javascript
 import express from "express";

 const express = require("express");

```
Es ***NECESARIO*** incluir el typo de archivo "module" en el [package.json](#configuraciones-iniciales)

&nbsp;

### Express
- un framework el cual facilita la la creacion y manejo del servidor.
- 
&nbsp;  
 
#### Instalar express

```
npm install express
```



&nbsp;

```javascript
import express  from "express";

const app = express();
const port = 3000;

app.get("/", (req, res)=>{
    res.send("Hello from api!")
})

app.listen(port, ()=>{
    console.log("Listening Worked on port " + port)
})

```

Para que esto funcione, es necesario [correr](#correr-archivos) el archivo

La funcion ***get()*** maneja el request y response del URI especificado. En este caso solo está enviando un mensaje.

La función ***listen()*** inicia el servidor.


- - -