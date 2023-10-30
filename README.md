# ExpressJS
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
2. Authentication
3. Logging (morgan)
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
