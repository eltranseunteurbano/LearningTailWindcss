# Pasos para ejecutar un proyecto de TailWind CSS
1. Instalar las dependencias de Tail Wind, autoprefixer y postcss-cli
    ```sh
    $ npm install taildwindcss autoprefixer postcss-cli
    ```
2. Inicializar el tailwindcss
    ```sh
    $ npx tailwindcss init
    ```
    
3. Crear un archivo con el nombre "postcss.config.js" 
    ```sh
    $ touch postcss.config.js
    ```
    
4. En el archivo "postcss.config.js" pegar las lineas de codigo
    ```sh
       module.exports = {
        plugins: [
            require('tailwindcss'),
            require('autoprefixer'),
          ]
    }
    ```
    
5. Crear el archivo origin de CSS y el archivo de HTML
5.1 Crear una carpeta "css" en el root y dentro el archivo "tailwind.css". Dentro del archivo pegar las siguientes lineas
    ```sh
        @tailwind base;
        @tailwind components;
        @tailwind utilities;
    ```

    5.2 Crear una carpeta "public" en el root y dentro el archivo "index.html" y pegar esta linea en el head
    ```sh
        <link rel="stylesheet" href="css/style.css">
    ```
6. En el "package.json" colocar el script build:
     ```sh
        "build": "postcss css/tailwind.css -o public/css/style.css"
    ```

7. Correr el script build
     ```sh
        $ npm run build
    ```

8. Correr el navegador con un live-server
