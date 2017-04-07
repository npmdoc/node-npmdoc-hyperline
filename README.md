# api documentation for  [hyperline (v0.6.1)](https://github.com/NickTikhonov/hyperterm-hyperline#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-hyperline.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-hyperline) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-hyperline.svg)](https://travis-ci.org/npmdoc/node-npmdoc-hyperline)
#### Handy status line for Hyper.app

[![NPM](https://nodei.co/npm/hyperline.png?downloads=true)](https://www.npmjs.com/package/hyperline)

[![apidoc](https://npmdoc.github.io/node-npmdoc-hyperline/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-hyperline_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-hyperline/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-hyperline/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-hyperline/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Nick Tikhonov"
    },
    "babel": {
        "presets": [
            "es2015"
        ]
    },
    "bugs": {
        "url": "https://github.com/NickTikhonov/hyperterm-hyperline/issues"
    },
    "dependencies": {
        "color": "^0.11.3",
        "json-loader": "^0.5.4",
        "systeminformation": "^3.4.1"
    },
    "description": "Handy status line for Hyper.app",
    "devDependencies": {
        "babel-core": "^6.11.4",
        "babel-loader": "^6.2.4",
        "babel-preset-es2015": "^6.9.0",
        "babel-preset-react": "^6.11.1",
        "eslint": "^3.3.0",
        "eslint-config-idiomatic": "^2.1.0",
        "eslint-loader": "^1.5.0",
        "eslint-plugin-react": "^6.1.1",
        "webpack": "^1.13.1",
        "webpack-node-externals": "^1.3.3"
    },
    "directories": {},
    "dist": {
        "shasum": "109e05a32478ae7ca939c279f92e0d09324cc4f8",
        "tarball": "https://registry.npmjs.org/hyperline/-/hyperline-0.6.1.tgz"
    },
    "gitHead": "09cfcec4de388c8c934214935925d6ba070c1436",
    "homepage": "https://github.com/NickTikhonov/hyperterm-hyperline#readme",
    "keywords": [
        "hyper.app",
        "hyper",
        "hyperterm"
    ],
    "license": "MIT",
    "main": "dist/hyperline.js",
    "maintainers": [
        {
            "name": "nicktikhonov",
            "email": "nt34@st-andrews.ac.uk"
        }
    ],
    "name": "hyperline",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/NickTikhonov/hyperterm-hyperline.git"
    },
    "scripts": {
        "build": "NODE_ENV=production webpack",
        "dev": "webpack --watch"
    },
    "version": "0.6.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module hyperline](#apidoc.module.hyperline)
1.  [function <span class="apidocSignatureSpan">hyperline.</span>decorateHyper (Hyper, _ref4)](#apidoc.element.hyperline.decorateHyper)
1.  [function <span class="apidocSignatureSpan">hyperline.</span>mapHyperState (_ref3, map)](#apidoc.element.hyperline.mapHyperState)
1.  [function <span class="apidocSignatureSpan">hyperline.</span>reduceUI (state, _ref2)](#apidoc.element.hyperline.reduceUI)



# <a name="apidoc.module.hyperline"></a>[module hyperline](#apidoc.module.hyperline)

#### <a name="apidoc.element.hyperline.decorateHyper"></a>[function <span class="apidocSignatureSpan">hyperline.</span>decorateHyper (Hyper, _ref4)](#apidoc.element.hyperline.decorateHyper)
- description and source-code
```javascript
function decorateHyper(Hyper, _ref4) {
	  var React = _ref4.React;
	  var notify = _ref4.notify;
	  var Component = React.Component;
	  var PropTypes = React.PropTypes;

	  var HyperLine = (0, _hyperline.hyperlineFactory)(React);

	  return function (_Component) {
	    _inherits(_class, _Component);

	    _createClass(_class, null, [{
	      key: 'displayName',
	      value: function displayName() {
	        return 'Hyper';
	      }
	    }, {
	      key: 'propTypes',
	      value: function propTypes() {
	        return {
	          colors: PropTypes.oneOfType([PropTypes.object, PropTypes.array]),
	          fontFamily: PropTypes.string,
	          style: PropTypes.object,
	          hyperline: PropTypes.object
	        };
	      }
	    }]);

	    function _class(props, context) {
	      _classCallCheck(this, _class);

	      var _this = _possibleConstructorReturn(this, Object.getPrototypeOf(_class).call(this, props, context));

	      _this.colors = (0, _colors.getColorList)(props.colors);

	      var defaultConfig = (0, _config.getDefaultConfig)(_plugins2.default);
	      var mergedConfig = (0, _config.mergeConfigs)(defaultConfig, props.hyperline, notify);

	      _this.plugins = mapConfigToPluginProp(mergedConfig);
	      return _this;
	    }

	    _createClass(_class, [{
	      key: 'render',
	      value: function render() {
	        return React.createElement(Hyper, _extends({}, this.props, { customChildren: React.createElement(HyperLine, {
	            fontFamily: this.props.fontFamily,
	            colors: this.colors,
	            plugins: this.plugins
	          }) }));
	      }
	    }]);

	    return _class;
	  }(Component);
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.hyperline.mapHyperState"></a>[function <span class="apidocSignatureSpan">hyperline.</span>mapHyperState (_ref3, map)](#apidoc.element.hyperline.mapHyperState)
- description and source-code
```javascript
function mapHyperState(_ref3, map) {
	  var _ref3$ui = _ref3.ui;
	  var colors = _ref3$ui.colors;
	  var fontFamily = _ref3$ui.fontFamily;
	  var hyperline = _ref3$ui.hyperline;

	  return Object.assign({}, map, {
	    colors: colors,
	    fontFamily: fontFamily,
	    hyperline: hyperline
	  });
	}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.hyperline.reduceUI"></a>[function <span class="apidocSignatureSpan">hyperline.</span>reduceUI (state, _ref2)](#apidoc.element.hyperline.reduceUI)
- description and source-code
```javascript
function reduceUI(state, _ref2) {
	  var type = _ref2.type;
	  var config = _ref2.config;

	  switch (type) {
	    case 'CONFIG_LOAD':
	    case 'CONFIG_RELOAD':
	      {
	        return state.set('hyperline', config.hyperline);
	      }
	  }

	  return state;
	}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
