Installation

React privides CLI Tools, React CLI tools depends on the Node.js. If Nodejs is not installed, you can download and install by visiting <https://nodejs.org/en/download/>

Toolchain
    React toolchain helps to create, build, run and deploy the React application. Popular toolchain to develop React application are
        Create React App − SPA oriented toolchain
        Next.js − server-side rendering oriented toolchain
        Gatsby − Static content oriented toolchain
    Tools required to develop a React application are
        The serve, a static server to serve our application during development
        Babel compiler
        Create React App CLI

How to install

Serve static server
    npm install serve -g
        Create a simple static site and serve the application using serve app.
            1. cd /go/to/your/workspace
            2. Create a new folder, static_site and change directory to newly created folder.
                mkdir static_site
                cd static_site
            3. create a index.html
                <!DOCTYPE html>
                    <html>
                    <head>
                        <meta charset="UTF-8" />
                        <title>Static website</title>
                    </head>
                    <body>
                        <div><h1>Hello!</h1></div>
                    </body>
                </html>
            4. Run the serve command
                serve .
Babel compiler
    Babel is a JavaScript compiler which compiles many variant (es2015, es6, etc.,) of JavaScript into standard JavaScript code supported by all browsers. React uses JSX, an extension of JavaScript to design the user interface code. Babel is used to compile the JSX code into JavaScript code.

    To install Babel and it's React companion, run the below command −
    
    npm install babel-cli@6 babel-preset-react-app@3 -g

Create React App toolchain
    Create React App is a modern CLI tool to create single page React application. It handles babel compiler as well.
    Install Create React App in local system.
        npm install -g create-react-app

Updating the toolchain
    React Create App toolchain uses the react-scripts package to build and run the application.
        npm install react-scripts@latest
