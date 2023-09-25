<h1>LangChain with Typescript</h1>

<h4>1) Create and navigate to new directory</h4>

   mkdir 01-Guidelines<br>
   cd 01-Guidelines

<h4>2) Initiate a node project in the directory</h4>
     npm init -y
   
<h4>3) Install required packages</h4>

    npm install -S langchain
    npm i dotenv
    npm i --save-dev @types/node


<h4>4)  Initiate typescript in the project</h4>

    tsc --init
    
<h4>5) Update tsconfig.json by changing properties as follows</h4>

{<br>
  "compilerOptions": {<br>
    ...<br>
  "target": "ES2020", // or higher<br>
    "module": "nodenext"<br>
  }<br>
}<br>
<h4>6) Update package.json and following to it before scripts</h4>

"type": "module",
<h4>7) Create API key from open AI</h4>
<ul>
<li>Login to Open AI</li>
<li>Navigate to API page</li>
<li>Click your profile on the top right corner</li>
<li>Check your free limit from Usage tab, if limit expired buy credits or use some different account</li>
<li>Click View API Keys</li>
<li>From the left sidebar open Api Keys</li>
<li>Create new secret key</li>
<li>Save your generated key</li>

</ul>
<h4>8) Create .env file </h4>
OPENAI_API_KEY="<OPEN_KEYS_PASTE_HERE>"
<h4>9) Create .gitignore file</h4>

node_modules<br>
.env
<h4>10) Create app.ts file</h4>
import { OpenAI } from "langchain/llms/openai";
import "dotenv/config";
const llm = new OpenAI({
  openAIApiKey: process.env.OPENAI_API_KEY,
  temperature: 0.9,
});
async function main() {
  const result = await llm.predict(
    `What would be a good company name for a company that makes colorful socks?`
  );
  console.log(result);
}
main();

10) Transforms TypeScript code into JavaScript code

&nbsp;tsc
<h4>11) Run the app</h4>

&nbsp;node app.js<br>
&nbsp;Running this code will respond with some answer. In my case I got the following response<br>

&nbsp;Socktastik.
