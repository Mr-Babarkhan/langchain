<h1>LangChain with Typescript</h1>

<h4>1) Create and navigate to new directory</h4>

   &nbsp;mkdir 01-Guidelines
  &nbsp; cd 01-Guidelines

<h4>2) Initiate a node project in the directory</h4>
    &nbsp; npm init -y
   
<h4>3) Install required packages</h4>

    npm install -S langchain
    npm i dotenv
    npm i --save-dev @types/node


<h4>4)  Initiate typescript in the project</h4>

    tsc --init
    
<h4>5) Update tsconfig.json by changing properties as follows</h4>

&nbsp;{
 &nbsp; "compilerOptions": {
   &nbsp;  ...
  &nbsp;  "target": "ES2020", // or higher
    &nbsp;"module": "nodenext"
  }
}
<h4>6) Update package.json and following to it before scripts</h4>

"type": "module",
<h4>7) Create API key from open AI</h4>
<ul><li>
&nbsp;Login to Open AI
&nbsp;Navigate to API page
&nbsp;Click your profile on the top right corner
&nbsp;Check your free limit from Usage tab, if limit expired buy credits or use some different account
&nbsp;Click View API Keys
&nbsp;From the left sidebar open Api Keys
&nbsp;Create new secret key
&nbsp;Save your generated key

</li></ul>
<h4>8) Create .env file </h4>
&nbsp;OPENAI_API_KEY="<OPEN_KEYS_PASTE_HERE>"
<h4>9) Create .gitignore file</h4>

&nbsp;node_modules
&nbsp;.env
<h4>10) Create app.ts file</h4>

&nbsp;import { OpenAI } from "langchain/llms/openai";
&nbsp;import "dotenv/config";
&nbsp;const llm = new OpenAI({
&nbsp;  openAIApiKey: process.env.OPENAI_API_KEY,
 &nbsp; temperature: 0.9,
&nbsp;});
&nbsp;async function main() {
&nbsp;  const result = await llm.predict(
 &nbsp;   `What would be a good company name for a company that makes colorful socks?`
 &nbsp; );
&nbsp;  console.log(result);
&nbsp;}
&nbsp;main();
10) Transforms TypeScript code into JavaScript code

&nbsp;tsc
<h4>11) Run the app</h4>

&nbsp;node app.js
&nbsp;Running this code will respond with some answer. In my case I got the following response

&nbsp;Socktastik.
