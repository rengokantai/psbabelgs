#### psbabelgs


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


