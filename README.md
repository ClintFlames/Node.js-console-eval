# Node.js console eval
Allows eval in Node.js console.
If `exit` function exist enter `exit` for close console.

## Just copy what you need or <a href="#install">install</a>
#### TIPS
1. Optimazed version uses `process.stdout.write`.
2. Module version always use `process.stdout.write`.
```js
/**
 * Node.js console eval
 * Made by: ClintFlames
 * Reserved variables: $ - console input, _ - eval code
 * Optimized: yes
 * Includes exit command: yes
 */
require("readline").createInterface({input:process.stdin}).on("line",($)=>{if($=="exit"){process.exit(1);}else{try{const _=eval($);if(typeof(_)!="string"){process.stdout.write(((_)=>{if(typeof(_)=="string"){return _.replace(/`/g,"`"+String.fromCharCode(8302)).replace(/@/g,"@"+String.fromCharCode(8203));}else{return _;}})(require("util").inspect(_))+"\n");}}catch(_){process.stdout.write(_.message+"\n");}}});
```

```js
/**
 * Node.js console eval
 * Made by: ClintFlames
 * Reserved variables: $ - console input, _ - eval code
 * Optimized: yes
 * Includes exit command: no
 */
require("readline").createInterface({input:process.stdin}).on("line",($)=>{try{const _=eval($);if(typeof(_)!="string"){process.stdout.write(((_)=>{if(typeof(_)=="string"){return _.replace(/`/g,"`"+String.fromCharCode(8302)).replace(/@/g,"@"+String.fromCharCode(8203));}else{return _;}})(require("util").inspect(_))+"\n");}}catch(_){process.stdout.write(_.message+"\n");}});
```

```js
/**
 * Node.js console eval
 * Made by: ClintFlames
 * Reserved variables: $ - console input, _ - eval code
 * Optimized: no
 * Includes exit command: yes
 */
require("readline").createInterface({input:process.stdin}).on("line",($)=>{if($=="exit"){process.exit(1);}else{try{const _=eval($);if(typeof(_)!="string"){console.log(((_)=>{if(typeof(_)=="string"){return _.replace(/`/g,"`"+String.fromCharCode(8302)).replace(/@/g,"@"+String.fromCharCode(8203));}else{return _;}})(require("util").inspect(_)));}}catch(_){console.log(_.message);}}});
```

```js
/**
 * Node.js console eval
 * Made by: ClintFlames
 * Reserved variables: $ - console input, _ - eval code
 * Optimized: no
 * Includes exit command: no
 */
require("readline").createInterface({input:process.stdin}).on("line",($)=>{try{const _=eval($);if(typeof(_)!="string"){console.log(((_)=>{if(typeof(_)=="string"){return _.replace(/`/g,"`"+String.fromCharCode(8302)).replace(/@/g,"@"+String.fromCharCode(8203));}else{return _;}})(require("util").inspect(_)));}}catch(_){console.log(_.message);}});
```
## <div id="install">Install</div>
```console
npm i node.js-console-eval
```
```js
// Initialization module
const console_eval = require("node.js-console-eval");
// Listen console for eval with command exit
// WARNING: Make it once or output will be twice
console_eval({
	includes_exit: true
});
```