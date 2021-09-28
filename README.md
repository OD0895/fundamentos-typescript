# Fundamentos de TypeScript

# Que es TypeScript?

Según su definición forma es un superconjunto tipado de JavaScript, que compila a JavaScript. Pero esto no nos dice mucho, desmenuzando un poco su definición tenemos que es un lenguaje de:

- Programación tipado, esto quiere decir que posee un conjunto de tipos para definir las variables.
- Alto nivel, lo que quiere decir que es entendible por humanos y posee un alto nivel de abstracción del código máquina.
- Programación que genera código JavaScript, sí, al final del día emite código JavaScript el cual es compatible con los navegadores.
- Código abierto.
- Desarrollo para cualquier sistema.
- Programación que puede ejecutarse en cualquier navegador o plataforma que soporte JavaScript.

**¿Por qué deberíamos utilizarlo?** Porque obtendremos un JavaScript con superpoderes. Esto quiere decir que tenemos programación orientada a objetos, podemos potenciar nuestro código de JavaScript ya que soporta ES5, ES6 y más, es un proyecto muy activo ya que es open source por lo que también tenemos actualizaciones periódicas y una comunidad creciente.

💡 Con TypeScript podemos prevenir cerca del 15% de bugs de un proyecto a diferencia que si lo hicieramos con JavaScript.

Es un superconjunto tipado de javascript, que compila a javascript.

**Lenguaje de programación tipado:** Posee un conjunto de tipos para poder usarlos con las variables, pudiendo personalizarlos o extenderlos.

**Lenguaje de alto nivel:** Entendible por humanos y posee un alto nivel de abstracción del código máquina.

**Genera como resultado código JavaScript**: Emite código javascript compatible con browsers y otras herramientas de javascript.

**Código abierto.**

**Desarrollo desde cualquier sistema.**

**El código puede ejecutarse en cualquier navegador o plataforma que soporte javascript.**

### Porque usar TypeScript

- Programación orientada a objetos
- Potenciar tu código JavaScript
- Mayor productividad
- Poderoso sistema de tipos
- Compila a ES5, ES6 y más
- Proyecto muy activo/Open source
- Actualizaciones periódicas
- Comunidad creciente
- Puede prevenir cerca del 15% de bugs
- Puede usar TypeScript para backend**__**

## Instalación y funcionamiento del compilador de TypeScript

### Para instalar varias versiones de nodejs ⇒ [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

Instalamos globalmente:

```
npm install -g typescript

```

El rol del compilador tsc es transformar nuestro codigo escrito en Ts a plano Js para que pueda ser interpretado por los navegadores y otras plataformas

<h4>Como compilar un archivo Ts</h4>

```
// compilamos el archivo ts
tsc hello.ts

// ejecutamos el nuevo archivo creado por el compilador
node hello.js

```

<h4>Compilamos de manera automatica un archivo en particular</h4>

este se va a compilar cada vez que haya un cambio en el archivo en cuestion

```
tscc --watch hello.ts
```

## Instalación de TypeScript

Con el siguiente comando lo instalaremos de manera global:

```
npm install -g typescript

```

## Consultar la versión del compilador de TS:

```
tsc -v

```

## Compilar nuestros ficheros .ts

```
tsc your_file.ts

```

## Compilar de manera ‘automática’ nuestros ficheros .ts

```
tsc --watch your_file.ts

```

No hay que tenerle miedo al TypeScript, ya que este nos creará un archivo: your_file.js.Es decir un archivo .js compatible con todo.

Gracias por la explicación profesor.

## Configurar Typescript

`tsconfig.json`

- Especifica la raiz de un proyecto TS
- Permite configurar opciones para el compilador

Para crear este archivo en cualquier proyecto:

```
tsc --init
```

Este comando nos generar el archivos tsconfig.json

El archivo tsconfig se trata de un objeto json con un atributo

`compilerOptions` que nos permite configurar las diferentes opciones en nuestro typescript

ejemplo podemos cambiar los parametros:

“`targe`”: “es5” → para especificar la version de ecmascript que obtendremos como resultado de la compilación

“`module`” : “commonjs” → especificacion de la configuracion para la generacion de modulos

“`stric`” "true or false"→ tipado estricto

“`removeComments`”:true → eliminar comentarios al compilar

`Include` podremos configurar opciones adicionales para la configuracion de nuestro proyecto

include es una lista de declaraciones de tipo que se van a incluir en el proceso de compilación

`Exclude` para que no tome los archivos o carpetas en cuenta en el proceso de compilación

`Extens` Podremos definir un archivo de configuracion general para nuestro proyecto y heredar las configuraciones utilizando extends

`CompileOnSave` Realizar Compilacion de manera automatica

El archivo base es este:

```
{
	"extends": "./config/base"
	"compilerOptions":{
		"target": "es6",
		"module": "commonjs"
		"strict":true,
		"removeComments":true
	},
	"include":[
		"src/**/*.ts"
	],
	"exclude": [
		"node_modules",
		"**/*.test.ts"
	]
}

```

Una vez que este archivo es generado, ejecutamos:

```
tsc // Busa la configuracion dentro del proyecto
tsc --project platzi // Especifica el directorio donde esta la configuracion
tsc file.ts // Omite la configuracion

```

Para ver todas las configuraciones que podemos hacer:

[TSConfig Reference - Docs on every TSConfig option](https://www.typescriptlang.org/tsconfig)

**Comando tsc Funciones**

```
tsc  // Busca la configuracion
tsc --project platzi //Especificaciones de un directorio que contiene la configuracion
tsc file.ts // Omite la configuración
```

## Tipado en TypeScript

Tipado de TS:

- Explícito: Se define explícitamente una sintaxis (el orden, la formación y la combinación de las reglas) del tipo de la variables a usar.

```
miVariableExplicita : string = 'Esta variable es explícita' // el `:` permite especificar el tipo del dato

```

- Inferido: TS tiene la habilidad de deducir el tipo de variable que se usa a partir del valor asignado a dicha variable

```
miVariableInferida = "Esta variable será un string"  // TS deduceel tipo de miVariableInferidayel valor,a partir dela inicialización dela misma

```

**Tipos de datos primitivos:**

- Number
- Boolean
- String
- Array
- Tuple
- Enum
- Any
- Void
- Null
- Undefined
- Never
- Object

### Tipos de datos

Dentro de los tipos explícitos que maneja TypeScript, tenemos:

1. **Number**. Este tipo de dato incluye valores numéricos, hexadecimales, binarios y octales.
    
    ```
    // Explícito
    let phone: number
    phone = 3315015804
    
    let hex: number = 0xf00d
    let binary: number = 0b1010
    let octal: number = 0o744
    
    // Implícito
    let phoneNumber = 3315015804
    
    ```
    
2. **Boolean**. Es el tipo de dato más simple en TypeScript ya que solo acepta dos tipos de valores que son `true` o `false`.
    
    ```
    // Explícito
    let isTrue: boolean =true// Implícito
    let isFalse =false
    ```
    
3. **String**. Es el tipo de dato para trabanar con datos textuales o cadenas, para definir este tipo de dato se puede usar comilla dobles `""` o simples `''`.
    
    ```
    // Explícito
    let userName: string = 'Alejandra'
    
    // Implícito
    let lastName = 'Camacho'
    
    ```
    
    Dentro del tipo de dato *string* también podemos crear *templates* de la siguiente forma:
    
    ```
    // Template string
    // Uso de back-tick ``
    let userInfo: string = `
      User info:
      firstName: ${firstName}
      lastName: ${lastName}
      phone: ${phone}
      isValid: ${isTrue}
    `
    ```
    
    ### **Tipo: Any**
    
    - Usado para capturar valores dinámicos
    - Los valores pueren cambiar de tipo en el tiempo:– APIs externas– Librerías de terceros
    
    ```tsx
    // type Any --> For dynamic variables
    // Explicit type
    let idUser: any;
    idUser = 1; // Number
    idUser = '1'; // String
    console.log('iduser ', idUser);
    console.log(typeof idUser);
    
    // Inferred type
    let otherId;
    otherId = '1';
    otherId = 1;
    // otherId = true;
    console.log('otherId ', otherId);
    console.log(typeof otherId);
    
    let suprise: any = 'Hello typescript';
    // suprise.sayHello(); // Error
    const res = suprise.substring(10);
    console.log(`res ${res}`);
    ```
    
    ## Void y never
    
    **Tipo Void:**
    
    Representa la ausencia de tipo. usado en funciones que no retornan nada.
    
    **Tipo Never:**
    
    Representa funciones que lanzan excepciones o nunca retornan un valor.
    
    ```tsx
    // type void for functions
    // Explicit type
    
    function showInfo(user: any): any {
      console.log(`User Info ${user.id} ${user.username} ${user.firstname}`);
      //   return 'hola';
    }
    
    showInfo({id: 1, username: 'Antúnez Durán', firstname: 'Francisco Javier'});
    
    // Inferred type
    function showFormattedInfo(user: any) {
      console.log(`User Info,
            id: ${user.id}
            username: ${user.username}
            firstname: ${user.firstname}`);
    }
    
    showFormattedInfo({id: 1, username: 'Antúnez Durán', firstname: 'Francisco Javier'});
    
    // Type void as variable data type
    let unusable: void;
    // unusable = null; --> colocar "strict": false en tsconfig.json para poder hacer uso
    unusable = undefined;
    
    // Type never
    function handleError(code: number, message: string): never {
      // Process your code
      // Generate a message
      throw new Error(`${message}. Code: ${code}`);
    }
    
    try {
      console.log('La funcion handleError no devuelve nada bajo esta linea');
      handleError(404, 'Not found');
    } catch (error) {}
    
    function sumNumbers(limit: number): never {
      let sum = 0;
      while (true) {
        sum++;
      }
      // return sum;
    }
    
    sumNumbers(10); // --> Llamada a un bucle infinito no acabaria nunca, typescript no compila, al verlo.
    ```
    
    ### null y undefined
    
    - En TypeScript, ambos “valores” tienen sus respectivos tipos:
        - null
        - undefined
    - Null y Undefined se pueden asumir como subtipos de los otros tipos de datos.
    - Significa que se pueden asignar null y undefied a una variable de tipo string, por ejemplo.
    
    Opción --strictNullChecks
    
    - Solo permite asignar null y undefined a una variable de tipo any o a sus respectivos
    - Ayua a evitar errores comunes en programación de apps en el ámbito JavaScript
    
    Generará un reporte de los errores que encuentre, hacemos `tsc nombreDelArchivo.ts --strictNullChecks`
    
    - En Typescript, ambos “valores” tienen sus respectivos tipos:
    
    ```tsx
    //Explicita
      //Definir variables con tipo de dato null es valido y solo acepta valor tipo null nada ma
    let nullVariable:null;
    nullVariable =null;
    // nullVariable = 1;  Error
    
    //Implicita
    let otherVariable =null;
    otherVariable = 'test';
    
    //Undefined
      //Solo soporta ese tipo de dato como asignacion
    let undefinedVariable:undefined =undefined;
    // undefinedVariable = 'test'; Error
    
    let otherUndefined =undefined; //como no le pusimos ningun tipo de dato a la variable podremos reasignarla
    otherUndefined = 1;
    
    console.log('undefinedVariable', undefinedVariable);
    console.log('otherUndefined', otherUndefined);
    
    ```
    
    **Tipo: Null y Undefined Como subtipos**
    
    - Null y Undefined se pueden asumir como subtipos de los otros tipos de datos
    - Significa que se puede asignar null y undefined a una variable de tipo string, por ejemplo.
    
    **Tipo: Null y Undefined La Opcion —strictNullChecks**
    
    - Solo permite asignar null y undefined a una variable de tipo any o sus tipos respectivos
    - Ayuda a evitar errores comunes en programación de apps en el ambito Javascript
    
    ```tsx
    //Null y undefined como subtimos
    
    // --strictNullChecks
      //Consiste en agregar una bandera al compilador de typecrit para identificar las diferentes asignaciones
    let albumName:string;
    //albumName = null;
    //albumName = undefined;
    
    ```
    
    para evitar errores con null or undefined utilizaremos la flag
    
    ```bash
    tsc --watch src/main.ts --stringNullChecks
    ```
    
    ## Array
    
    Un Array es un tipo especial de tipo de datos que puede almacenar múltiples valores de diferentes tipos de datos secuencialmente usando una sintaxis especial.TypeScript admite matrices, similar a JavaScript. Hay dos formas de declarar una Array :
    
    1. Utilizando corchetes. Este método es similar a cómo declararía matrices en JavaScript.
    
    ```tsx
    let fruits: string[] = ['Apple', 'Orange', 'Banana'];
    
    ```
    
    1. Usando un tipo de arreglo genérico, Array <elementType>.
    
    ```tsx
    let fruits: Array<string> = ['Apple', 'Orange', 'Banana'];
    
    ```
    
    Ambos métodos producen el mismo resultado.
    
    ## Tupla
    
    Una tupla en TypeScript es un array de elementos que están tipados. De esta manera cada vez que haya que insertar un elemento se validará que dicho elemento coincida con el tipo de dato establecido en la tupla.
    
    - Las tuplas permiten expresar un arreglo con un número fijo de elementos
    - Los tipos de datos son conocidos
    
    ## Enum
    
    - Los enumerados permiten definir un conjunto de constantes con nombre
    - Tienen la ventaja de adaptarse al contexto de la aplicación
    
    ```tsx
    enum DiasLaborales {
      Lunes = 'MON',
      Martes = 'TUE',
      Miercoles = 'WED',
      Jueves = 'THU',
      Viernes = 'FRI'
    }
    ```
    
    ## Unión de Tipos, Alias y Tipos Literales
    
    ### Unión de Tipos
    
    - En TypeScript se puede definir una variable con múltiples tipos de datos: `Union Type`
    - Se usa el símbolo de pipe `|` entre los tipos
    
    ### Alias de Tipos
    
    Para evitar redundancias en nuestro codigo (debido a la utilizacion de la misma combinacion de tipos de datos) podemos utilizar **alias.**
    
    - TypeScript permite crear un alias como nuevo nombre para un tipo
    - El alias se puede aplicar también a un conjunto de combinación de tipos
    - Se usa la palabra reservada `type`
    
    ### Tipos Literales
    
    - Una variable con un tipo literal puede contener únicamente una cadena del conjunto
    - Se usan cadenas como “tipos”, combinados con el símbolo de pipe | entre ellos
    
    ```tsx
    export {}
    
    //* Por ejemplo, tenemos usuarios que tienen un ID numérico o de tipo string 10, '10'
    let idUser: number | string //* Aceptará strings y number
    idUser = 10
    idUser = '10'
    
    //* Buscar username dado un ID
    
    functiongetUserNameById(id: number | string) {
      //* Lógica de negocio, find the user
    return id
    }
    
    //* No da errores 😄
    getUserNameById(10)
    getUserNameById('10')
    
    //--------------------------------------------------------------------------------------------
    
    //* Alias de tipos de TS
    type IdUser = number | string
    type UserName = string
    let userID: IdUser
    idUser = 10
    idUser = '10'
    
    //* Buscar username dado un ID
    
    functiongetUserName(id: IdUser):UserName {
      //* Lógica de negocio, find the user
    return 'Mike'
    }
    
    //----------------------------------------------------------------------------------------------------
    
    //* Tipos literales
    //* Por ejemplo, sólo aceptamos fotos de 100x100, 500x500 y 1000x1000
    type SquareSize = '100x100' | '500x500' | '1000x1000'
    //! let smallPicture: SquareSize = "200x200" //!Esto da un error, no está incluido ese valor en SquareSize
    let smallPicture: SquareSize = "100x100"
    let mediumPicture: SquareSize = "500x500"
    let bigPicture: SquareSize = "1000x1000"
    
    console.log('small Picture: ', smallPicture)
    console.log('medium Picture: ', mediumPicture)
    console.log('big Picture: ', bigPicture)
    ```
    
    ## Aserciones de tipo
    
    La prioridad de usar **as** por encima de **<>** es desde la versión 1.6 de Typescript debido a que había ambigüedad en archivos **.jsx**
    
    [Para más información aquí](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-1-6.html#new-tsx-file-extension-and-as-operator)
    
    - Cuando el programador puede conocer más que typescript sobre el valor de una variable
    - Es un mensaje al compilador: “Confia en mi, se lo que hago”
    - Se parece al casting de tipos en otros lenguajes de programación
    - Usa dos sintaxis: <Angle Bracket> y (variable as tipo)
    
    ```jsx
    export{}
    //<tipo> // Angle Bracket sintax
    let username:any;
    username = 'luixaviles';
    
    //tenemos una cadena, TS confia en mi!
      //Queremos utilizar la funcion length pero la variable esta declarada con any
        //Entonces lo que hacemos es utilizar <tipoDato> para indicarle que es un string
           //Y poder utilizar length para conocer la longitud del string
    let message:string = (<string>username).length > 5?
                          `Welcome ${username}`:
                          'Username es muy corto';
    console.log(message);
    
    let usernameWithId: any  = 'luixviles 1';
    //Como obtener el username
    
    username = (<string>usernameWithId).substring(0,10);
    console.log(username);
    
    //Sintaxis as
      //Es otra forma de insertar tipos en ts
        //En lugar de los <> podemos utilizar as dentro de los parentisis para especificarle
          // Un tipo de dato a la variable
    
    message = (username as string).length > 5?
                          `Welcome ${username}`:
                          'Username es muy corto';
    console.log(message);
    
    let helloUser: any;
    helloUser = "hello paparazzi";
    username = (helloUser as string).substring(6);
    ```
    
    ## Funciones en TypeScript
    
    - Los parámetros en las funciones son tipados
    - Se pueden definir parámetros opcionales
    - El tipo de retorno puede ser un tipo básico, enum, alias, tipo literal o una combinación de ellos
    - Se puede definir que tipo de datos devolvera la funcion
    
    ```jsx
    // Funciones en TypeScript
    
    // // Crear una Fotografia: JS
    // function createPicture(title, date, size) {
    //     // title
    // }
    
    type SquareSize = '100x100' | '500x500' | '1000x1000'
    // Usamos TS, definimos tipos para paramentros
    function createPicture(title:string, date: string, size: SquareSize) {
        // Se crea la fotografia
        console.log('create Picture using', title, date, size);
    }
    
    createPicture('My Birthday', '2020-03-10', '500x500');
    createPicture('Colombia', '2020-03-20'); // --> Error
    
    // Parametros opcionales
    function createPicture(title?:string, date?: string, size?: SquareSize) {
        // Se crea la fotografia
        console.log('create Picture using', title, date, size);
    }
    
    // Flat Array Function
    let createPic = (title: string, date: string, size: SquareSize): object => {
        // return {
        //     title: title,
        //     date: date,
        //     size: size
        // };
        return { title, date, size };
    };
    
    const picture = createPic('Platzi session', '2020-03-10', '100x100');
    console.log(picture);
    ```
    
    ### Parámetros Rest.
    
    Otra característica de TypeScript es la posibilidad de pasar una lista indefinida de valores y que los reciba un vector.
    
    El concepto de parámetro Rest se logra antecediendo tres puntos al nombre del parámetro:
    
    ```
    functionsumar(...valores:number[]) {
      let suma=0;
    for(let x=0;x<valores.length;x++)
        suma+=valores[x];
    return suma;
    }
    console.log(sumar(10, 2, 44, 3));
    console.log(sumar(1, 2));
    console.log(sumar());
    
    ```
    
    El parámetro ‘valores’ se le anteceden los tres puntos seguidos e indicamos que se trata de un vector de tipo ‘number’. Cuando llamamos a la función le pasamos una lista de valores enteros que luego la función los empaqueta en el vector:
    
    ```
    console.log(sumar(10, 2, 44, 3));
    console.log(sumar(1, 2));
    console.log(sumar());
    
    ```
    
    La función con un parámetro Rest puede tener otros parámetros pero se deben declarar antes.
    
    Los parámetros Rest no pueden tener valores por defecto
    
    - *Functions : ** Se pueden usar parámetros opcionales y se pueden definir los tipos de datos para estos parámetros.Puede definir algún tipo de retorno ( puede ser un tipo primitivo o básico p.e. number, boolean, string o los tres).—>Parámetros opcionales: mecanismo para manejar/permitir el paso de diferentes valores o formas diferentes de usar la función.
    
    ## Resumen
    
    Parámetros/argumentos son tipados y opcionales.El retorno puede ser una combinación de tipos. En Ts hay parámetros opcionales con ?. undefinded, cuando una variable no tiene un valor.
    
    Flat array functión, function comprenhension.
    
    Qué espero recibir de respuesta.
    
    Tipado en el retorno.
    
    El tipado de datos en TS es muy importante.
    
    Usar never cuando vamos a lanzar excepciones en la función.Al momento de usar la función, ponerlo en un try catch.
    
    null y undefined son subtipos de void. A su vez, null y undefined son subtipos de :
    
    - number
    - boolean
    - string
    - array
    - tuple
    - enum
    - any
    - void
    - object
    
    ## Interfaces
    
    Las interfaces en TS constituyen una forma poderosa de definir “contratos” tanto para tu proyecto, como para el código externo del mismo.
    
    [Documentación oficial sobre interfaces en TS](https://www.typescriptlang.org/docs/handbook/2/objects.html#interfaces-vs-intersections)
    
    [Interfaces en TS explicado en TutorialsTeacher](https://www.tutorialsteacher.com/typescript/typescript-interface)
    
    [Interfaces en TS explicado en Desarrollo Web](https://desarrolloweb.com/articulos/definicion-interfaces-typescript.html)
    
    [Interfaces en TS explicado en TutorialsPoint](https://www.tutorialspoint.com/typescript/typescript_interfaces.htm)
    
    Se constituyen como forma de contratos para el codigo que vaya a implementarla.
    
    Es una forma de definir que propiedades y metodos deben implementar si o si las propiedades que se declaren de este tipo de interfas
    
    ```tsx
    interface Picture{
    	title: string,
    	date: string,
    	orientation: PhotoOrientation // Enum
    }
    
    // el parametro picture va a verificar si el valor recibido cumple con la interface
    functionshowPicture(picture: Picture){
    	console.log(`[title: ${picture.title},
    								date: ${picture.date}
    								orientation: ${picture.orientation}]`
    }
    ```
    
    ### Interfaces: propiedades opcionales
    
    No todas las propiedades de una interfaz podrían ser requeridas.
    
    Establecemos una propiedad como opcional con el símbolo ‘?’ después del nombre.
    
    ```tsx
    interface PictureConfig {
      title?: string, //* El '?' indica que el parámetro es opcional
      date?: string,
      orientation?: PhotoOrientation
    }
    
    functiongeneratePicture(config: PictureConfig) {
    const picture = {title: 'Default title', date: '2020-01-01'} //*Valores por defecto
    if (config.title) {
        picture.title = config.title
      }
    if (config.date) {
        picture.date = config.date
      }
    
    return picture
    }
    
    let picture = generatePicture({})
    console.table({picture})
    
    picture = generatePicture({title: 'Travel Pic'})
    console.table({picture})
    
    picture = generatePicture({title: 'Travel Pic', date: '2016-06-23'})
    console.table({picture})
    
    ```
    
    ### Interfaces: Propiedades de solo lectura
    
    Algunas propiedades de la interfaz podrían no ser modificables una vez creado el objeto. Esto es posible usando `readonly` antes del nombre de la propiedad.
    
    ```tsx
    //* Interfaz: Usuario
    
    interface User {
    readonly id: number,
      username: string,
      isPro: boolean
    }
    
    let user: User = {id: 10, username: 'Mike', isPro:true}
    console.table({user})
    //*modificamos ahora un campo
    //! user.id = 20 ahora no podemos modificar este campo
    user.username = 'paparazzi'
    console.table({user})
    ```
    
    ### Extensión de interfaces
    
    La herencia es un mecanismo para poder reutilzar código dentro de la programación orientada a objetos. TS provee esto con las interfaces. Las interfaces pueden extenderse de otras. Esto permite copiar los miembros ya definidos en una interfaz a otra, ganando flexibilidad y reusabilidad de componentes.
    
    ```tsx
    export {}
    
    enum PhotoOrientation{
      Landscape,
      Portrait,
      Square,
      Panorama
    }
    
    //*Herencia de interfaces
    
    interface Entity {
      id: number,
      title: string,
    }
    
    interface Albumextends Entity{
      //*Copia de los atributos de Entity
      description: string
    }
    
    interface Picture extends Entity {
      orientation: PhotoOrientation
    }
    
    const album: Album = {
      id: 5,
      title: 'Meetups',
      description: 'Community events around the world'
    }
    
    const picture: Picture = {
      id: 10,
      title: 'Family',
      orientation: PhotoOrientation.Square
    }
    
    let newPicture = {} as Picture
    newPicture.id = 2
    newPicture.title = 'Moon'
    
    console.table({album})
    console.table({picture})
    console.table({newPicture})
    ```
    
    ## Clases
    
    Definiendo Clases y Constructores
    
    A partir de ECMAScript 2015 es posible construir clases y hacer uso del paradigma de la Programación Orientada a Objetos en Javascript
    
    Typescript permite aplicar estas técnicas sin tener que es esperar por otra versión.
    
    - Las clases y a la POO, se puede conectar las diferentes entidades y se puede relacionar
    - Una clase es la asbtracción de un conjunto de objetosejemplo:Para definir una entidad usuario, se hace uso de una clase: Se debe definir una clase quedentro tenga una función que permita crear objetos a partir de esta Clase y poder interactuar con ellos.
    
    ```tsx
    export {}
    
    enum PhotoOrientation {
        Landscape,
        Portrait,
        Square,
        Panorama,
    };
    
    class Picture {
        // properties
        id: number;
        title: string;
        orientation: PhotoOrientation;
        //constructor
        constructor( id: number, title: string, orientation: PhotoOrientation ) {
    this.id = id;
    this.title = title;
    this.orientation = orientation;
        }
        //Performance
        toString() {
    return `[id: ${this.id}, title: ${this.title}, orientation: ${this.orientation}]`
        }
    }
    
    class Album {
        id: string;
        title: string;
        pictures: Picture[];
    
        constructor( id: string, title: string ) {
    this.id = id;
    this.title = title;
    this.pictures = [];
        }
    
        addPicture(picture: Picture) {
    this.pictures.push(picture);
        }
    }
    
    let album: Album =new Album('stories-1', 'Photos of mine');
    const newPic: Picture =new Picture(2, 'my new pic!', PhotoOrientation.Panorama);
    const new2Pic: Picture =new Picture(3, 'my 2nd new pic!', PhotoOrientation.Portrait);
    const new3Pic: Picture =new Picture(4, 'my 3rd new pic!', PhotoOrientation.Portrait);
    album.addPicture(newPic);
    album.addPicture(new2Pic);
    album.addPicture(new3Pic);
    console.log('album -> ', album);
    ```
    
    ### Clases publicas
    
    Ts define un modificador de acceso publico por defecto para todos los miembros de la clase
    
    Pero tambien podemos dejarlo mas claro con la keyboard `public`
    
    ### Clases privadas
    
    Podemos “bloquear” ciertas propiedades o directamente clases enteras para evitar que se puedan acceder desde fuera de la misma, con esto logramos encapsulación
    
    Usamos la keyboard `private` o directamente `#` esta ultima es mejor
    
    - TS define un modificador de acceso publico por defecto para los miembros de clase ( public )
    - TS define un modificador de acceso privado para los miembros que no se deseen ser leídos por fuera de la clase ( private )
    - con TS se tiene una sintaxis para métodos privados. Usando el signo # antes del nombre del miembro de clase: p.e. #atributoEsto se hace debido a que ofrece garantías de aislamiento en miembros privados.( Private identifiers are only available when targeting ECMAScript 2015 and higher. )
    
    ```tsx
    export {}
    
    enum PhotoOrientation {
        Landscape,
        Portrait,
        Square,
        Panorama,
    };
    
    class Picture {
        // properties
        #id: number;
        #title: string;
        #orientation: PhotoOrientation;
        //constructor
        public constructor( id: number, title: string, orientation: PhotoOrientation ) {
            this.#id = id;
            this.#title = title;
            this.#orientation = orientation;
        }
        //Performance
        private toString() {
            return `[id: ${this.#id}, title: ${this.#title}, orientation: ${this.#orientation}]`
        }
    }
    
    class Album {
        #id: string;
        #title: string;
        #pictures: Picture[];
    
        public constructor( id: string, title: string ) {
            this.#id = id;
            this.#title = title;
            this.#pictures = [];
        }    
    
        private addPicture(picture: Picture) {
            this.#pictures.push(picture);
        }
    }
    
    let album: Album = new Album('stories-1', 'Photos of mine');
    /** Don't care about commented code below. The classes has private members, the output will be empty  */
    // const newPic: Picture = new Picture(2, 'my new pic!', PhotoOrientation.Panorama);
    // const new2Pic: Picture = new Picture(3, 'my 2nd new pic!', PhotoOrientation.Portrait);
    // const new3Pic: Picture = new Picture(4, 'my 3rd new pic!', PhotoOrientation.Portrait);
    // album.addPicture(newPic); there's an error due to private class props
    // album.addPicture(new2Pic); there's an error due to private class props
    // album.addPicture(new3Pic);  there's an error due to private class props
    console.log('album -> ', album);
    ```
    
    ## Métodos Get y Set
    
    Modificadores de acceso.
    
    Get(accesa) y Set(muta), Interceptar y controlar el acceso a los miembros privados del objeto. Son métodos de la clase para leer y cambiar los valores de los miembros privados. De que forma podemos acceder & mutar el valor en los miembros. Validación de los nuevos valores en los miembros.
    
    TypeScript soporta getters/setters como una forma de interceptar accesos a un miembro de un objeto. Esto le da una forma de tener un control más fino sobre cómo se accede a un miembro en cada objeto.
    
    Convirtamos una clase simple para usar get y set. Primero, empecemos con un ejemplo sin getters y setters.
    
    ```
    class Employee {
      fullName: string;
    }
    
    let employee =new Employee();
    employee.fullName = "Bob Smith";
    
    if (employee.fullName) {
      console.log(employee.fullName);
    }
    
    ```
    
    Aunque permitir que la gente establezca directamente el nombre completo al azar es bastante útil, también podemos querer imponer algunas restricciones cuando se establece el nombre completo.
    
    En esta versión, añadimos un configurador que comprueba la longitud del nuevo Nombre para asegurarse de que es compatible con la longitud máxima de nuestro campo de base de datos de respaldo. Si no lo es, arrojamos un error notificando al código del cliente que algo salió mal.
    
    Para preservar la funcionalidad existente, también añadimos un simple programa que recupera el nombre completo sin modificar.
    
    ```
    const fullNameMaxLength = 10;
    
    classEmployee {
    private _fullName:string;
    
    getfullName():string {
    returnthis._fullName;
      }
    
    setfullName(newName:string) {
    if (newName && newName.length > fullNameMaxLength) {
    thrownew Error("fullName has a max length of " + fullNameMaxLength);
        }
    
    this._fullName = newName;
      }
    }
    
    let employee =new Employee();
    employee.fullName = "Bob Smith";
    
    if (employee.fullName) {
      console.log(employee.fullName);
    }
    
    ```
    
    Para probarnos a nosotros mismos que nuestro accesorio está comprobando ahora la longitud de los valores, podemos intentar asignar un nombre de más de 10 caracteres y verificar que obtenemos un error.
    
    Un par de cosas a tener en cuenta sobre los accesorios:
    
    Primero, los accessores requieren que el compilador dé como resultado ECMAScript 5 o superior. La bajada de nivel a ECMAScript 3 no está soportada. Segundo, los accesorios con un get y sin set se infieren automáticamente para ser de solo lectura. Esto es útil cuando se genera un archivo.d.ts a partir de su código, porque los usuarios de su propiedad pueden ver que no pueden cambiarlo.
    
    ## Herencia de clases y propiedades estáticas
    
    - Abstract = cuando requieres que una clase no sea instanciada
    - Protected = Entre público y privado, para que los elementos puedan ser accedidos por la clase y subclases
    - Extends = herencia de SUPER clase a subclases, para invocar al constructor de la SUPERclase en las subclases usar super(propiedades)
    - Static = Puede acceder a métodos y propiedades de una clase sin instanciarla
    - Readonly = Indica propiedades que solo se pueden leer
    
    ## Modulos en TypeScript
    
    Módulos en TypeScript: Los módulos en typescript proveen un mecanismo para una mejor organización del código y promueven su reutilizaciónA partir de ECMAScript 2015 los módulos son parte nativa del lenguaje Javascript
    
    Importando y exportando modulos: Generalmente se define un modulo con la idea de agrupar codigo relacionado. Podemos tomar criterios en torno a la funcionalidad, features, utilitarios, modelos, etc.
    
    Los miembros de modulo interactúan con el uso de las palabras reservadas **import** y **export**
    
    Mecanismo para una mejor organización.
    
    Código relacionado será un módulo.
    
    import y export.
    
    tsc --init, crear src para almacenar js, en el archivo json outDir / dist, en el archivo principal contentrá toda la definición del código. Se usa export antes de las clases para decirle que voy a exportar y a cada hoja importar lo deseado.
    
    ## Principios de responsabilidad única
    
    Principio de responsabilidad unica. Idealmente un archivo deberia tener un proposito o responsabilidad unica: definir una clase, una interfaz, un enumerado, etc.Esto mejora la legibilidad de codigo, facilita la lectura, testing y favorece su mantenimiento.
    
    Utilizamos archivos separados y la utilizacion de import, export para lograr un poco mas de mantenibiilidad. Podemos usar tambien carpetas para separar nuestros archivos.
    
    Para observar una carpeta entera usamos:
    
    ```
    tsc--project myFolder--watch
    ```
    
    ## Resolviendo módulos ⇒ [https://www.typescriptlang.org/docs/handbook/module-resolution.html](https://www.typescriptlang.org/docs/handbook/module-resolution.html)
    
    Resolviendo Modulos: Typescript resuelve la ubicacion de modulos observando referencias relativas y no relativas.Posteriormente intenta localizar el modulo usando una estrategia de resolucion de modulos.
    
    ```
    tsc --moduleResolutionnodetsc --moduleResolution classic
    
    ```
    
    diferenciasnode: Modulos CommonJs o UMD, mas opciones de configuraciónclassic: Modulos AMD, System, ES2015, poco configurable
    
    en tsconfig.json
    
    ```
    "moduleResolution": "node|classic"
    "traceResolution":true
    ```
    
    existen los path alias para que no tengamos que lidiar con esa mano de puntos y slash en nuestros proyectos.Esta configuración la pueden poner en el ts.config.json dentro de compilerOptions y así pueden acceder al shortcut @item para llegar a esa carpeta en específico que están buscando.Para el ejemplo yo tengo una carpeta item y dentro el archivo index.ts.
    
    ```
    "paths": {
          "@item": ["item/index.ts"],
        }
    
    ```
    
    y así se podría importar
    
    ```
    import { Item }  from  '@item'
    ```
    
    ## Webpack y agrupación de Módulos
    
    Webpack es una herramienta habitual para el desarrollo web, para procesar archivos ts es un bundler en programacion.
    
    Instalar las siguientes dependencias
    
    ```tsx
    npm i -D typescript webpack webpack-cli
    ```
    
    Webpack
    
    ```
    module.exports = {
        mode: 'production',
        entry: "./src/main.ts",
        output: {
          filename: "./dist/bundle.js",
        },
    
        // Enable sourcemaps for debugging webpack's output.
        devtool: "source-map",
    
        resolve: {
          // Add '.ts' and '.tsx' as resolvable extensions.
          extensions: [".webpack.js", ".web.js", ".ts", ".tsx", ".js"],
        },
    
        module: {
          rules: [
            // All files with a '.ts' or '.tsx' extension will be handled by 'ts-loader'.
            { test: /\.tsx?$/, loader: "ts-loader", exclude: /node_modules/ },
    
            // All output '.js' files will have any sourcemaps re-processed by 'source-map-loader'.
            { test: /\.js$/, loader: "source-map-loader" },
          ],
        },
    
        // Other options...
      };
    ```