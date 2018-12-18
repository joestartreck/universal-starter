# universal-starter
There is added code to reproduce error which occurs  during rendering angular webcomponents.

# Background context
We would like to create webcomponents by using @angular/elements and run server side rendering. However now it is not possible due to the  error "ReferenceError: Element is not defined"


# How to reproduce error: 
```
yarn install;
npm run build:ssr && npm run serve:ssr
```

# Result: 

```
> ng-universal-demo@0.0.0 build:ssr /home/jozef/Desktop/persistent/toDelete/universal-starter
> npm run build:client-and-server-bundles && npm run compile:server


> ng-universal-demo@0.0.0 build:client-and-server-bundles /home/jozef/Desktop/persistent/toDelete/universal-starter
> ng build --prod && ng run ng-universal-demo:server:production

                                                                                         
Date: 2018-12-18T16:11:01.106Z
Hash: e01a311989d44af3d81b
Time: 17859ms
chunk {0} runtime.ec2944dd8b20ec099bf3.js (runtime) 1.41 kB [entry] [rendered]
chunk {1} main.b38916b37ee067070589.js (main) 187 kB [initial] [rendered]
chunk {2} polyfills.cbd68c5d44260a2c2a8e.js (polyfills) 76.1 kB [initial] [rendered]
chunk {3} styles.3ff695c00d717f2d2a11.css (styles) 0 bytes [initial] [rendered]
chunk {scripts} scripts.e84e36a0841a046b4d25.js (scripts) 13.3 kB  [rendered]
                                                                                       
Date: 2018-12-18T16:11:07.377Z
Hash: ae6883b955070fee5414
Time: 4111ms
chunk {main} main.js, main.js.map (main) 23.5 kB [entry] [rendered]

> ng-universal-demo@0.0.0 compile:server /home/jozef/Desktop/persistent/toDelete/universal-starter
> tsc -p server.tsconfig.json


> ng-universal-demo@0.0.0 serve:ssr /home/jozef/Desktop/persistent/toDelete/universal-starter
> node dist/server

/home/jozef/Desktop/persistent/toDelete/universal-starter/node_modules/@angular/elements/bundles/elements.umd.js:72
    var elProto = Element.prototype;
                  ^

ReferenceError: Element is not defined
    at /home/jozef/Desktop/persistent/toDelete/universal-starter/node_modules/@angular/elements/bundles/elements.umd.js:72:19
    at extendStatics (/home/jozef/Desktop/persistent/toDelete/universal-starter/node_modules/@angular/elements/bundles/elements.umd.js:8:68)
    at Object.<anonymous> (/home/jozef/Desktop/persistent/toDelete/universal-starter/node_modules/@angular/elements/bundles/elements.umd.js:11:2)
    at Module._compile (internal/modules/cjs/loader.js:688:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:699:10)
    at Module.load (internal/modules/cjs/loader.js:598:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:537:12)
    at Function.Module._load (internal/modules/cjs/loader.js:529:3)
    at Module.require (internal/modules/cjs/loader.js:636:17)
    at require (internal/modules/cjs/helpers.js:20:18)
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! ng-universal-demo@0.0.0 serve:ssr: `node dist/server`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the ng-universal-demo@0.0.0 serve:ssr script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/jozef/.npm/_logs/2018-12-18T16_11_10_615Z-debug.log


```
