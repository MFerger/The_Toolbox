//Install Babel in terminal
$ npm install --save-dev babel babel-cli babel-preset-es2015

//Where the files are located
$ ./node_modules/.bin/babel js/app.js

//Add a few things to package.json for it to run
//npm start, npm build
$ echo '{ "presets": ["es2015"] }' > .babelrc package.json >> "scripts": { "start": "http-server -c-0 -o", "build": "babel js --out-file dist/main.js --watch" },
