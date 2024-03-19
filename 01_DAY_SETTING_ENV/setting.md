Environment Setup

Need install: NodeJS, NPM

Install Node Using .pkg Installer (<https://nodejs.org/en/download>)
step 1: Download the .pkg installer
step 2: Run Node.js Installer
step 3: Verify Node.js install

    node -v

step 4: Update NPM version

    sudo npm install npm --global

Set NODE HOME in environment variable
    run command

    export PATH=/usr/local/bin:$PATH

Install Node using Homebrew
step 1: Install Node.js and NPM

    brew install node

step 2: Verify Node.js and NPM Installation
for Node:

    node -v

for NPM:

    npm -v

Homebrew will update the version of Node and NPM you have installed. Make sure that your Homebrew has the latest version of the Node package. If not, then run the given command to update the Homebrew.

    brew update

Run given the command to update version of node:
    brew upgrade node
It will update Node and NPM to the latest version.

After successfully installing NodeJS, we can start installing React upon it using npm. You can install  ReactJS in two ways

    Using webpack and babel.
    Using the create-react-app command.

Installing ReactJS using webpack and babel

Webpack is a module bundler (manages and loads independent modules). It takes dependent modules and compiles them to a single (file) bundle. You can use this bundle while developing apps using command line or, by configuring it using webpack.config file.

Babel is a JavaScript compiler and transpiler. It is used to convert one source code to other. Using this you will be able to use the new ES6 features in your code where, babel converts it into plain old ES5 which can be run on all browsers.

Step 1 - Create the Root Folder

    mkdir reactApp
    cd reactApp
    npm init

Step 2 - install React and react dom

    npm install react --save
    npm install react-dom --save

Step 3 - Install webpack

    npm install webpack webpack-dev-server webpack-cli --save

Step 4 - Install babel

    npm install babel-core babel-loader babel-preset-env babel-preset-react html-webpack-plugin --save-dev

Step 5 - Create the Files
    To complete the installation, we need to create certain files namely, index.html, App.js, main.js, webpack.config.js and, .babelrc.

Step 6 - Set Compiler, Server and Loaders
Open webpack-config.js file and add the following code. We are setting webpack entry point to be main.js. Output path is the place where bundled app will be served. We are also setting the development server to 8001 port. You can choose any port you want.

    webpack.config.js

    const path = require('path');
    const HtmlWebpackPlugin = require('html-webpack-plugin');

    module.exports = {
    entry: './main.js',
    output: {
        path: path.join(__dirname, '/bundle'),
        filename: 'index_bundle.js'
    },
    devServer: {
        inline: true,
        port: 8001
    },
    module: {
        rules: [
            {
                test: /\.jsx?$/,
                exclude: /node_modules/,
                loader: 'babel-loader',
                query: {
                presets: ['es2015', 'react']
                }
            }
        ]
    },
    plugins:[
        new HtmlWebpackPlugin({
            template: './index.html'
        })
    ]
    }
    Open the package.json and delete "test" "echo \"Error: no test specified\" && exit 1" inside "scripts" object. We are deleting this line since we will not do any testing in this tutorial. Let's add the start and build commands instead.

    "start": "webpack-dev-server --mode development --open --hot",
    "build": "webpack --mode production"

Step 7 - index.html
    This is just regular HTML. We are setting div id = "app" as a root element for our app and adding index_bundle.js script, which is our bundled app file.

    <!DOCTYPE html>
    <html lang = "en">
    <head>
        <meta charset = "UTF-8">
        <title>React App</title>
    </head>
    <body>
        <div id = "app"></div>
        <script src = 'index_bundle.js'></script>
    </body>
    </html>

Step 8 − App.jsx and main.js
    This is the first React component. We will explain React components in depth in a subsequent chapter. This component will render Hello World.

    App.js

    import React, { Component } from 'react';
    class App extends Component{
    render(){
        return(
            <div>
                <h1>Hello World</h1>
            </div>
        );
    }
    }
    export default App;

We need to import this component and render it to our root App element, so we can see it in the browser.

    main.js

    import React from 'react';
    import ReactDOM from 'react-dom';
    import App from './App.js';

    ReactDOM.render(<App />, document.getElementById('app'));
    Note − Whenever you want to use something, you need to import it first. If you want to make the component usable in other parts of the app, you need to export it after creation and import it in the file where you want to use it.

    Create a file with name .babelrc and copy the following content to it.

    {
    "presets":["env", "react"]
    }

Step 9 - Running the Server
    The setup is complete and we can start the server by running the following command.

    npm start

Step 10 - Generating the bundle
    Finally, to generate the bundle you need to run the build command in the command prompt as
        npm run build

Using the create-react-app command

Step 1 - install create-react-app

    npx create-react-app my-app

Step 2 - Delete all the source files

    cd my-app/src
    my-app\src>del *
    my-app\src\*, Are you sure (Y/N)? y

Step 3 - Add files
Add files with names index.css and index.js in the src folder as −

    type nul > index.css
    type nul > index.js
In the index.js file add the following code

    import React from 'react';
    import ReactDOM from 'react-dom';
    import './index.css';

Step 4 - Run the project

    npm start
