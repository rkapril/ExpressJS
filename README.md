# ExpressJS
## Creating an Express Server

1. Create directory (mkdir)
2. Create index.js file (touch)
3. Initialise NPM (npm init -y) 
4. Install the Express package (npm i express)
5. Write Server application in index.js
```
import express from "express";
const app = express();
const port = 3000;

app.listen(port, () => {
  console.log(`Server running on port ${port}.`);
});
```
7. Start server (node index.js)
