1- initilize git repository using the command:
git init .

2- touch .gitignore and add node_modules to it.

3- run npm init -y

4- touch index.html and index.js inside src dir

5- npm install webpack webpack-cli webpack-dev-server --save-dev

6- make a webpack.config.js file in the root dir

7- npm install html-webpack-plugin --save-dev

8- add this script to webpack.config.js

```
     import path from 'path';

     module.exports = {
     entry: path.join(__dirname, 'src', 'index.js'),
     output: {
     path: path.resolve(__dirname, 'dist'),
     },
     };

```

9- add the html-webpack-plugin to the config file

```
 plugins: [
 new HtmlWebpackPlugin({
   template: path.join(__dirname, "src", "index.html"),
 }),
],
```

10- Babel setup:
run this command to install the packages required for babel

    ```
    npm install @babel/core babel-loader --save-dev

    ```

11- add this config to the webpack.config.js file:

     module: {
        rules: [
        {
            test: /\.?js$/,
            exclude: /node_modules/,
            use: {
            loader: 'babel-loader',
            },
        },
        ],
    }

12- install babel-preset packages to tell babel which files to transpile

```
npm install @babel/preset-env @babel/preset-react --save-dev
```

13- add the packges to the babel loader options in the use block

    @babel/preset-env for transpiling ES6 +
    @babel/preset-react for transpiling React JSX

```
use: {
       loader: "babel-loader",
       options: {
         presets: ['@babel/preset-env', '@babel/preset-react']
       }
     }
```

14- add build and dev scripts to package.json file

```
"scripts": {
  "dev": "webpack serve",
  "build": "webpack",

}
```

15- now, time to run
https://media.giphy.com/media/oe33xf3B50fsc/giphy.gif

16- you can now add more plugins for css, images, svg react compponents and more...

17- to add typescript, install the follwing packages:

```
npm install -D typescript @types/react @types/react-dom
```

18- npx tsc --init
