// Install from terminal
$ npm install --save cors

//Require in app.js
var express = require('express');
var cors = require('cors');
var app = express();

//Pass every route through it
app.use(cors());
