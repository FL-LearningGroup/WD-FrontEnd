With ES2015 (ES6), with get built-in support for modules in JavaScript. Like with CommonJS, each file is its own module. To make objects, functions, classes or variables available to the outside world it’s as simple as exporting them and then importing them where needed in other files. Angular 2 makes heavy use of ES6 modules, so the syntax will be very familiar to those who’ve worked in Angular. The syntax is pretty straightforward:

# Exporting
You can export members one by one. What’s not exported won’t be available directly outside the module:

```js
export const myNumbers = [1, 2, 3, 4];
const animals = ['Panda', 'Bear', 'Eagle']; // Not available directly outside the module

export function myLogger() {
  console.log(myNumbers, animals);
}

export class Alligator {
   constructor() {
     // ...
   }
}
 ```
Or you can export desired members in a single statement at the end of the module:

```js
export { myNumbers, myLogger, Alligator };
```

# Exporting with alias
You can also give an aliases to exported members with the as keyword:

```js
export { myNumbers, myLogger as Logger, Alligator }
```

# Default export
You can define a default export with the default keyword:

```js
export const myNumbers = [1, 2, 3, 4];
const animals = ['Panda', 'Bear', 'Eagle'];

export default function myLogger() {
  console.log(myNumbers, pets);
}

export class Alligator {
  constructor() {
    // ...
  }
}
```

# Importing
Importing is also very straightforward, with the import keyword, members to be imported in curly brackets and then the location of the module relative to the current file:

```js
import { myLogger, Alligator } from 'app.js';
```

# Importing with alias
You can also alias members at import time:

```js
import myLogger as Logger from 'app.js';
```

# Importing all exported members
You can import everything that’s imported by a module like this:

```js
import * as Utils from 'app.js';
```

This allows you access to members with the dot notation:

```js
Utils.myLogger();
```

# Importing a module with a default member
You import the default member by giving it a name of your choice. In the following example Logger is the name given to the imported default member:

```js
import Logger from 'app.js';
```

And here’s how you would import non-default members on top of the default one:

```js
import Logger, { Alligator, myNumbers } from 'app.js';
```
