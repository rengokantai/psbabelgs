#### psbabelgs

- 2
as of babel6, we must specify language preset.
```
npm install babel-preset-es2015 --save-dev
```
now run it:
```
babel src --presets es2015 --out-dir dist  // --out-dir = -d
```

or, create .babelrc, add content without --presets
```
{ "presets":["es2015"]}
```

bundle:
```
babel src --presets es2015 --out-file dist/bundle.js // --out-file = -o
```


other flags:
```
babel src --presets es2015 --out-file dist/bundle.js -s   //add sourcemap
```

add content in .babelrc:
```
"sourceMaps":true
```

-w //watch  


amd module transpile:
```
npm install babel-plugin-transform-es2015-modules-amd --save-dev
```
donot forget to change .babelrc.



- 3
shim:performs interception of an API call and provides a layer of abstraction

- 4
to use es6 syntax in gulpfile  
1.rename gulpfile.js to gulpfile.babel.js  
2.install babel-core  

==

using webpack  
install babel-core, babel-loader

using browserify
```
browserify --entry src/app.js --outfile dist/bundle.js   // = -e ,-o
```
install babelify
```
npm install babelify --save-dev
```

now use transformer:
```
browserify --entry src/app.js --outfile dist/bundle.js -t babelify
```


 - 5
babelhook: babel-register
```
npm install babel-register --save-dev
npm install babel-polyfill --save-dev
```
add polyfill:
```
require("babel-polyfill");
```

```
babel srcdir --out-dir destdir
```

runtime
```
npm install babel-runtime --save
npm install babel-plugin-transform-runtime --save-dev
```

add in .babelrc:
```
"plugins":["transform-runtime"],
```


using jasmine.
```
jasmine init
jasmine examples    //see tutorial
```

allow jasmine to test es6 code:  
in spec/support/jasmine.json, add 
```
"helpers":[
"../node_modules/babel-register/lib/node.js"
]
```

using mocha and chai  
review:  
by default, mocha uses `test` as test dir, if you change dir use
```
mocha newdict
```

should syntax
```
var should = require('chai').should();
[1,2].indexOf(3).should.equal(-1);
```

use es6 with mocha:
change import:
```
import chai from 'chai';
const should = chai.should();
```

install prereq:
```
npm install babel-core babel-register babel-preset-es2015
```

add content in .babelrc:
```
{
"presets":["es2015"]
}
```

add content in package.json~scripts:
```
"test":"mocha --compilers js:babel-register"
```


