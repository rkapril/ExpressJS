# ExpressJS
![image](https://github.com/rkapril/ExpressJS/assets/61505106/dba74789-b30e-45e5-a96a-f5135dff221e)

## Creating an Express Server

1. Create directory (mkdir)
2. Create index.js file (touch)
3. Initialise NPM (npm init -y)
   
Add this in package.json
```
"type": "module"
```
5. Install the Express package (npm i express)
6. Write Server application in index.js
```
import express from "express";
const app = express();
const port = 3000;

app.listen(port, () => {
  console.log(`Server running on port ${port}.`);
});
```
7. Start server (node index.js)

## Middleware
1. Pre-processing (body-parser)
```
import express from "express";
import bodyParser from "body-parser";
import { dirname } from "path";
import { fileURLToPath } from "url";
const __dirname = dirname(fileURLToPath(import.meta.url));

const app = express();
const port = 3000;

app.use(bodyParser.urlencoded({ extended: true }));

app.get("/", (req, res) => {
  res.sendFile(__dirname + "/public/index.html");
});

app.post("/submit", (req, res) => {
  console.log(req.body);
});

app.listen(port, () => {
  console.log(`Listening on port ${port}`);
});
```
3. Authentication
4. Logging (morgan)
```
import express from "express";
import morgan from "morgan";

const app = express();
const port = 3000;

app.use(morgan("tiny"));

app.get("/", (req, res) => {
  res.send("Hello");
});

app.listen(port, () => {
  console.log(`Listening on port ${port}`);
});
```
5. Error
6. Custom
```
import express from "express";

const app = express();
const port = 3000;

function logger(req, res, next) {
  console.log("Request Method: ", req.method);
  console.log("Request URL: ", req.url);
  next();
}

app.use(logger);

app.get("/", (req, res) => {
  res.send("Hello");
});

app.listen(port, () => {
  console.log(`Listening on port ${port}`);
});
```
## Connect with PostgreSQL
```
import Client from "pg";

const db = new Client({
   user: "username",
   host: "localhost",
   database: "mydatabase",
   password: "password",
   port: 5432,
});

db.connect();

db.query("SELECT * FROM users", (err, res) => {
   if (err) {
      console.error("Error executing query", err.stack);
   } else {
     console.log("User data:". res.rows);
   }

   db.end();
});
```
      
