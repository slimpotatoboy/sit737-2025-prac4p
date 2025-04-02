# 4.1 Building a Microservice
## Create Node Project
we create a node project by running the following command.
```
npm init
```

## Install Express
Then we create a file named server.js and install express js.
```
npm install express
```


Main file: server.js

## Run app
```
node server.js
```
As our port given is 3000, it'll run on `http://localhost:3000`

## Install winston
We'll also install winston as following:
```
npm install winston
```
### Add winston code
We now add winston code as following:
```
// require winston
const winston = require("winston");
// initialize winston
const logger = winston.createLogger({
  level: "info",
  format: winston.format.json(),
  defaultMeta: { service: "calculator-microservice" },
  transports: [
    new winston.transports.Console({
      format: winston.format.simple(),
    }),
    new winston.transports.File({ filename: "logs/error.log", level: "error" }),
    new winston.transports.File({ filename: "logs/combined.log" }),
  ],
});

logger.log({ level: "error", message: `Invalid input ${n1} and ${n2}` });
```
