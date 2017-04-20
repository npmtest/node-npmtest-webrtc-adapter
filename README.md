# npmtest-webrtc-adapter

#### basic test coverage for  webrtc-adapter (v3.3.3)  [![npm package](https://img.shields.io/npm/v/npmtest-webrtc-adapter.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-webrtc-adapter) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-webrtc-adapter.svg)](https://travis-ci.org/npmtest/node-npmtest-webrtc-adapter)

#### A shim to insulate apps from WebRTC spec changes and browser prefix differences

[![NPM](https://nodei.co/npm/webrtc-adapter.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/webrtc-adapter)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-webrtc-adapter/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-webrtc-adapter/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-webrtc-adapter/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-webrtc-adapter/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-webrtc-adapter/build/test-report.html](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-webrtc-adapter/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-webrtc-adapter/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-webrtc-adapter/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-webrtc-adapter/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-webrtc-adapter/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "webrtc-adapter",
    "version": "3.3.3",
    "description": "A shim to insulate apps from WebRTC spec changes and browser prefix differences",
    "license": "BSD-3-Clause",
    "main": "./src/js/adapter_core.js",
    "repository": {
        "type": "git",
        "url": "https://github.com/webrtc/adapter.git"
    },
    "authors": [
        "The WebRTC project authors (https://www.webrtc.org/)"
    ],
    "scripts": {
        "preversion": "git stash && git checkout master && git pull && npm test | faucet && git checkout -B bumpVersion && grunt build && grunt copyForPublish && git add package.json release/* && git commit -m 'Add adapter artifacts' --allow-empty",
        "version": "",
        "postversion": "export GITTAG=\"echo $(git describe --abbrev=0 --tags | sed 's/^v//')\" && git push --force --set-upstream origin bumpVersion --follow-tags && git checkout gh-pages && git pull && cp out/adapter.js adapter.js && cp adapter.js adapter-'$GITTAG'.js && rm adapter-latest.js && ln -s adapter-'$GITTAG'.js adapter-latest.js && mkdir -p adapter-'$GITTAG'-variants && cp out/adapter.js adapter-'$GITTAG'-variants/ && cp out/adapter_*.js adapter-'$GITTAG'-variants/ && git add adapter.js adapter-latest.js adapter-'$GITTAG'.js adapter-'$GITTAG'-variants && git commit -m '$GITTAG' && git push --set-upstream origin gh-pages && git checkout master",
        "prepublish": "grunt build",
        "test": "grunt && mocha test/unit && node test/run-tests.js"
    },
    "dependencies": {
        "sdp": "^1.5.0"
    },
    "engines": {
        "npm": ">=3.10.0",
        "node": ">=6.0.0"
    },
    "devDependencies": {
        "chai": "^3.5.0",
        "chromedriver": "2.28.0",
        "eslint-config-webrtc": "^1.0.0",
        "faucet": "0.0.1",
        "geckodriver": "1.4.0",
        "grunt": "^0.4.5",
        "grunt-browserify": "^4.0.1",
        "grunt-cli": ">=0.1.9",
        "grunt-contrib-clean": "^1.0.0",
        "grunt-contrib-copy": "^1.0.0",
        "grunt-eslint": "^17.2.0",
        "grunt-githooks": "^0.3.1",
        "mocha": "^3.2.0",
        "selenium-webdriver": "^3.3.0",
        "tape": "^4.0.0",
        "travis-multirunner": "^3.0.1"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
