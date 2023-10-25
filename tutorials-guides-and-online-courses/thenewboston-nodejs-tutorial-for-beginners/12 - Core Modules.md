# 12 - Core Modules

Week 32.5 | Friday, August 11, 2023 | 11:39 PM

Related : [thenewboston-nodejs-tutorial-for-beginners](thenewboston-nodejs-tutorial-for-beginners.md) - [08 - Modules](08%20-%20Modules.md)

Source : [Node.js Tutorial for Beginners - 12 - Core Modules](https://www.youtube.com/watch?v=_cnJcXwwQRA&list=PL6gx4Cwl9DGBMdkKFn3HasZnnAqVjzHn_&index=12)

Core modules are modules included in Node.js. They are the predefined, reserved, by the
framework.

## Core module: `fs` - the file system module

When using your own, user defined, custom modules you include the `./` (to denote current
directory)

When using core modules (e.g. `fs`) do not append `./`, so the frame work knows it's a core
module and not your own, defined, module

It's common practice to name your variable the same as the core module name

```js
// app.js
var fs = require("fs"); // A core module: the FILE SYSTEM module - CRUD files

fs.writeFileSync("trains.txt", "I like trains");
// > Creates a trains text document (trains.txt) with content "I like trains"

console.log(fs.readFileSync("trains.txt").toString());
// > "I like trains"
```

## Core module: `path` - allows you to work with file paths

The path module normalizes the file paths across different platforms (e.g. Widnows OS or
Mac OS)

It also corrects for path typos where a double slash `//` just needs to just be a single slash `/`

```js
// app.js
var path = require("path");
var websiteHome = "Desktop/matt//matt2ology/index.html";
var websiteAbout = "Desktop/matt//matt2ology/about.html";

console.log(path.normalize(websiteHome));
// WINDOWS OS  > Desktop\matt\matt2ology\index.html
// Linux/MacOS > Desktop/matt/matt2ology/index.html

console.log(path.normalize(websiteAbout));
// Windows OS  > Desktop\matt\matt2ology\about.html
// Linux/MacOS > Desktop/matt/matt2ology/about.html

console.log(path.dirname(websiteAbout));
// Windows OS  > Desktop\matt\matt2ology\
// Linux/MacOS > Desktop/matt/matt2ology/

console.log(path.basename(websiteAbout));
// Windows OS  > about.html
// Linux/MacOS > about.html

console.log(path.extname(websiteAbout));
// Windows OS  > .html
// Linux/MacOS > .html

console.log(__dirname);
// Windows OS  > c:\Users\Matt\Desktop\Node.js\Matt\public
// Linux/MacOS > c:/Users/Matt/Desktop/Node.js/Matt/public

console.log(__filename);
// Windows OS  > c:\Users\Matt\Desktop\Node.js\Matt\public\app.js
// Linux/MacOS > c:/Users/Matt/Desktop/Node.js/Matt/public/app.js
```
