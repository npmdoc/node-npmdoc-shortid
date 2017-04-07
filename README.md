# api documentation for  [shortid (v2.2.8)](https://github.com/dylang/shortid)  [![npm package](https://img.shields.io/npm/v/npmdoc-shortid.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-shortid) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-shortid.svg)](https://travis-ci.org/npmdoc/node-npmdoc-shortid)
#### Amazingly short non-sequential url-friendly unique id generator.

[![NPM](https://nodei.co/npm/shortid.png?downloads=true)](https://www.npmjs.com/package/shortid)

[![apidoc](https://npmdoc.github.io/node-npmdoc-shortid/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-shortid_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-shortid/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-shortid/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-shortid/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Dylan Greene",
        "email": "dylang@gmail.com"
    },
    "browser": {
        "./lib/util/cluster-worker-id.js": "./lib/util/cluster-worker-id-browser.js",
        "./lib/random/random-byte.js": "./lib/random/random-byte-browser.js"
    },
    "bugs": {
        "url": "https://github.com/dylang/shortid/issues"
    },
    "dependencies": {},
    "description": "Amazingly short non-sequential url-friendly unique id generator.",
    "devDependencies": {
        "chai": "^3.3.0",
        "envify": "^3.4.0",
        "grunt": "^0.4.5",
        "grunt-browserify": "^3.6.0",
        "grunt-cli": "^0.1.13",
        "grunt-contrib-concat": "^0.5.1",
        "grunt-contrib-jshint": "^0.11.3",
        "grunt-contrib-uglify": "^0.9.2",
        "grunt-mocha-test": "^0.12.7",
        "grunt-notify": "^0.4.1",
        "grunt-open": "^0.2.3",
        "grunt-release": "^0.13.0",
        "grunt-templates-dylang": "^1.0.10",
        "load-grunt-tasks": "^3.3.0",
        "mocha": "^2.3.3",
        "time-grunt": "^1.2.1"
    },
    "directories": {},
    "dist": {
        "shasum": "033b117d6a2e975804f6f0969dbe7d3d0b355131",
        "tarball": "https://registry.npmjs.org/shortid/-/shortid-2.2.8.tgz"
    },
    "gitHead": "7bad247e7179e95ef3071d18669cd76ab7ae7077",
    "homepage": "https://github.com/dylang/shortid",
    "keywords": [
        "short",
        "tiny",
        "id",
        "uuid",
        "bitly",
        "shorten",
        "mongoid",
        "shortid",
        "tinyid"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "ai",
            "email": "andrey@sitnik.ru"
        },
        {
            "name": "dylang",
            "email": "dylang@gmail.com"
        }
    ],
    "name": "shortid",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/dylang/shortid.git"
    },
    "scripts": {
        "build": "grunt build",
        "readme": "grunt repos readme",
        "test": "grunt test"
    },
    "version": "2.2.8"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module shortid](#apidoc.module.shortid)
1.  [function <span class="apidocSignatureSpan">shortid.</span>characters (newCharacters)](#apidoc.element.shortid.characters)
1.  [function <span class="apidocSignatureSpan">shortid.</span>decode (id)](#apidoc.element.shortid.decode)
1.  [function <span class="apidocSignatureSpan">shortid.</span>generate ()](#apidoc.element.shortid.generate)
1.  [function <span class="apidocSignatureSpan">shortid.</span>isValid (id)](#apidoc.element.shortid.isValid)
1.  [function <span class="apidocSignatureSpan">shortid.</span>seed (seedValue)](#apidoc.element.shortid.seed)
1.  [function <span class="apidocSignatureSpan">shortid.</span>worker (workerId)](#apidoc.element.shortid.worker)
1.  object <span class="apidocSignatureSpan">shortid.</span>alphabet

#### [module shortid.alphabet](#apidoc.module.shortid.alphabet)
1.  [function <span class="apidocSignatureSpan">shortid.alphabet.</span>characters (_alphabet_)](#apidoc.element.shortid.alphabet.characters)
1.  [function <span class="apidocSignatureSpan">shortid.alphabet.</span>lookup (index)](#apidoc.element.shortid.alphabet.lookup)
1.  [function <span class="apidocSignatureSpan">shortid.alphabet.</span>seed (seed)](#apidoc.element.shortid.alphabet.seed)
1.  [function <span class="apidocSignatureSpan">shortid.alphabet.</span>shuffled ()](#apidoc.element.shortid.alphabet.shuffled)



# <a name="apidoc.module.shortid"></a>[module shortid](#apidoc.module.shortid)

#### <a name="apidoc.element.shortid.characters"></a>[function <span class="apidocSignatureSpan">shortid.</span>characters (newCharacters)](#apidoc.element.shortid.characters)
- description and source-code
```javascript
function characters(newCharacters) {
    if (newCharacters !== undefined) {
        alphabet.characters(newCharacters);
    }

    return alphabet.shuffled();
}
```
- example usage
```shell
...

The default characters provided were selected because they are url safe.

__Example__

'''js
// use $ and @ instead of - and _
shortid.characters('0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ$@');
'''

'''js
// any 64 unicode characters work, but I wouldn't recommend this.
shortid.characters('ⒶⒷⒸⒹⒺⒻⒼⒽⒾⒿⓀⓁⓂⓃⓄⓅⓆⓇⓈⓉⓊⓋⓌⓍⓎⓏⓐⓑⓒⓓⓔⓕⓖⓗⓘⓙⓚⓛⓜⓝⓞⓟⓠⓡⓢⓣⓤⓥⓦⓧⓨⓩ①②③④⑤⑥⑦⑧⑨⑩⑪⑫');
'''
...
```

#### <a name="apidoc.element.shortid.decode"></a>[function <span class="apidocSignatureSpan">shortid.</span>decode (id)](#apidoc.element.shortid.decode)
- description and source-code
```javascript
function decode(id) {
    var characters = alphabet.shuffled();
    return {
        version: characters.indexOf(id.substr(0, 1)) & 0x0f,
        worker: characters.indexOf(id.substr(1, 1)) & 0x0f
    };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.shortid.generate"></a>[function <span class="apidocSignatureSpan">shortid.</span>generate ()](#apidoc.element.shortid.generate)
- description and source-code
```javascript
function generate() {
  return build(clusterWorkerId);
}
```
- example usage
```shell
...


### Usage

'''js
var shortid = require('shortid');

console.log(shortid.generate());
//PPBqWA9
'''

Mongoose Unique Id
'''js
_id: {
type: String,
...
```

#### <a name="apidoc.element.shortid.isValid"></a>[function <span class="apidocSignatureSpan">shortid.</span>isValid (id)](#apidoc.element.shortid.isValid)
- description and source-code
```javascript
function isShortId(id) {
    if (!id || typeof id !== 'string' || id.length < 6 ) {
        return false;
    }

    var characters = alphabet.characters();
    var len = id.length;
    for(var i = 0; i < len;i++) {
        if (characters.indexOf(id[i]) === -1) {
            return false;
        }
    }
    return true;
}
```
- example usage
```shell
...
__Returns__ 'boolean'

Check to see if an id is a valid 'shortid'. Note: This only means the id _could_ have been generated by 'shortid', it doesn't guarantee
 it.

__Example__

'''js
shortid.isValid('41XTDbE');
// true
'''

'''js
shortid.isValid('i have spaces');
// false
'''
...
```

#### <a name="apidoc.element.shortid.seed"></a>[function <span class="apidocSignatureSpan">shortid.</span>seed (seedValue)](#apidoc.element.shortid.seed)
- description and source-code
```javascript
function seed(seedValue) {
    alphabet.seed(seedValue);
    return module.exports;
}
```
- example usage
```shell
...

'''js
shortid.worker(1);
'''

---------------------------------------

#### 'shortid.seed(integer)'

__Default:__ '1'

__Recommendation:__ You typically won't want to change this.

__Optional__
...
```

#### <a name="apidoc.element.shortid.worker"></a>[function <span class="apidocSignatureSpan">shortid.</span>worker (workerId)](#apidoc.element.shortid.worker)
- description and source-code
```javascript
function worker(workerId) {
    clusterWorkerId = workerId;
    return module.exports;
}
```
- example usage
```shell
...
'''js
shortid.isValid('i have spaces');
// false
'''

---------------------------------------

#### 'shortid.worker(integer)'

__Default:__ 'process.env.NODE_UNIQUE_ID || 0'

__Recommendation:__ You typically won't want to change this.

__Optional__
...
```



# <a name="apidoc.module.shortid.alphabet"></a>[module shortid.alphabet](#apidoc.module.shortid.alphabet)

#### <a name="apidoc.element.shortid.alphabet.characters"></a>[function <span class="apidocSignatureSpan">shortid.alphabet.</span>characters (_alphabet_)](#apidoc.element.shortid.alphabet.characters)
- description and source-code
```javascript
function characters(_alphabet_) {
    setCharacters(_alphabet_);
    return alphabet;
}
```
- example usage
```shell
...

The default characters provided were selected because they are url safe.

__Example__

'''js
// use $ and @ instead of - and _
shortid.characters('0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ$@');
'''

'''js
// any 64 unicode characters work, but I wouldn't recommend this.
shortid.characters('ⒶⒷⒸⒹⒺⒻⒼⒽⒾⒿⓀⓁⓂⓃⓄⓅⓆⓇⓈⓉⓊⓋⓌⓍⓎⓏⓐⓑⓒⓓⓔⓕⓖⓗⓘⓙⓚⓛⓜⓝⓞⓟⓠⓡⓢⓣⓤⓥⓦⓧⓨⓩ①②③④⑤⑥⑦⑧⑨⑩⑪⑫');
'''
...
```

#### <a name="apidoc.element.shortid.alphabet.lookup"></a>[function <span class="apidocSignatureSpan">shortid.alphabet.</span>lookup (index)](#apidoc.element.shortid.alphabet.lookup)
- description and source-code
```javascript
function lookup(index) {
    var alphabetShuffled = getShuffled();
    return alphabetShuffled[index];
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.shortid.alphabet.seed"></a>[function <span class="apidocSignatureSpan">shortid.alphabet.</span>seed (seed)](#apidoc.element.shortid.alphabet.seed)
- description and source-code
```javascript
function setSeed(seed) {
    randomFromSeed.seed(seed);
    if (previousSeed !== seed) {
        reset();
        previousSeed = seed;
    }
}
```
- example usage
```shell
...

'''js
shortid.worker(1);
'''

---------------------------------------

#### 'shortid.seed(integer)'

__Default:__ '1'

__Recommendation:__ You typically won't want to change this.

__Optional__
...
```

#### <a name="apidoc.element.shortid.alphabet.shuffled"></a>[function <span class="apidocSignatureSpan">shortid.alphabet.</span>shuffled ()](#apidoc.element.shortid.alphabet.shuffled)
- description and source-code
```javascript
function getShuffled() {
    if (shuffled) {
        return shuffled;
    }
    shuffled = shuffle();
    return shuffled;
}
```
- example usage
```shell
...

/**
 * Decode the id to get the version and worker
 * Mainly for debugging and testing.
 * @param id - the shortid-generated id.
 */
function decode(id) {
    var characters = alphabet.shuffled();
    return {
        version: characters.indexOf(id.substr(0, 1)) & 0x0f,
        worker: characters.indexOf(id.substr(1, 1)) & 0x0f
    };
}

module.exports = decode;
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
