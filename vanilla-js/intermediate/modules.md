# Modules and External Libraries in JavaScript

In JavaScript, when loading the files using
```html
<script src="file1.js"></script>
<script src="file2.js"></script>
```

Since all files are loaded using script tag, multiple files cannot have a variable with the same name, since it causes conflict.

To solve this problem, modules are created.

If file2.js uses a variable inside file1.js, we can skip loading file1.js with script tag.
Instead, make file2.js a module and export the variable in file1.js

## Creating a Module
Modules are files which can access variables from other files

```html
<!-- <script src="file1.js"></script> Not needed now --> 
<script type="module" src="file2.js"></script>
```

>[!NOTE]
**Modules don't work on opening isolated HTML Files, Live Server needs to be used.**

### Export variables / objects
```js
export const name = value;
```
Exports variable name from a JavaScript file

### Import variables / objects
```js
import {name} from './file1.js';
```
Imports variable from another file ( only when the current file is loaded as a module )

>[!NOTE]
**All of the imports should be on top of the file.**

### External Libraries

External JavaScript files can also be loaded using the script tag, and their functions/variables can be used

```html
<script src="https://unpkg.com/supersimpledev@1.0.1/hello.js"></script>
<script src="main.js"></script>
```

Now inside main.js, the variables / functions of hello.js can be used directly

```js
hello();
```

>[!NOTE]
**Make sure that the scripts are loaded in correct order ( External Library first ). Loading hello.js after main.js won't work in this case.**