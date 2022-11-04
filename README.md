# Notas React Native

React native es un framework para desarrollar aplicaciones móviles nativas para Android y iOS.

Existen dos formas de crear una aplicación con React Native:

- Usando el CLI de React Native
- Usando Expo

En este ejemplo se usa expo, ya que es más sencillo de configurar y no requiere de tantas configuraciones.

Para instalar expo se debe ejecutar el siguiente comando:

```bash
npm install -g expo-cli
```

Con esto instalamos el CLI de expo, que nos permite crear proyectos, ejecutarlos y publicarlos mediante el comando `expo`.

Por ejemplo, para crear un proyecto se ejecuta el siguiente comando:

```bash
expo init my-project
```

El CLI se encarga de instalar todas las dependencias necesarias para crear el proyecto, de crear la estructura de carpetas y los archivos necesarios.

Al ser un proyecto que usa JavaScript, React y Node, podemos ejecutarlo con el comando `npm start`.

## Para debuggear

Existen varias formas de debuggear una aplicación con React Native, pero la más sencilla en mi caso es usar la consola de Chrome, al poner en marcha el proyecto con el comando `npm start` podemos escoger la opción de ejecutar el proyecto en el navegador, de esta forma podemos usar la consola de Chrome para debuggear.

### Linter

Es recomendable usar un linter para mantener un código limpio y ordenado.

Podemos instalar eslint con el siguiente comando:

```bash
npm install --save-dev babel-eslint eslint-config-standard eslint-config-standard-jsx eslint-config-standard-react eslint-plugin-promise eslint-plugin-import eslint-plugin-node eslint-plugin-react
```

Una vez instaladas las dependencias, debemos configurar un poco el package.json para que el linter se ejecute correctamente.

Agregamos:

```json
"eslintConfig": {
    "parser": "babel-eslint",
    "extends": [
        "standard",
        "standard-jsx",
        "standard-react"
    ]
}
```

De esta forma el editor nos marcará errores de estilo en el código que escribamos.

## Conceptos básicos de React-native

La diferencia principal entre React y React-native, está en los componentes disponibles, por ejemplo, no tenemos `<div>` o `<p>`, React-native tiene sus propios componentes que mas o menos simulan esa funcionalidad.

Por ejemplo, un componente importante de React-native es `<Text></Text>` porque es la única manera en la que podemos renderizar textos.

Otro componente importante, quizás el mas, es `<View></View>`, con este componente creamos las interfaces, un dato importante es que con este componente por defecto se comporta como un contenedor con flexbox.

`TextInput`, `Button`, `Touchable`, son otros componentes importantes.

Touchable, son todos aquellos componentes que se pueden tocar en la interfaz. Una diferencia de este componente es que en vez de usar onClick, usamos onPress.

Otra cosa importante es que en React normalmente cualquier componente puede ser clickable, pero en React-native cualquier cosa que queramos que sea clickable hay que usar un Touchable, no podemos hacer que una vista sea tocable, ni que un texto sea tocable, pero podemos hacer lo siguiente:

```jsx
<TouchableWithoutFeedback onPress={() => console.log('click')}>
    <Text>Click me</Text>
</TouchableWithoutFeedback>
```

De esta forma podemos hacer que un texto sea clickable o tocable.

