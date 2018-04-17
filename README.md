# micro-fps

![Node](https://img.shields.io/node/v/micro-fps.svg?style=flat-square)
[![NPM](https://img.shields.io/npm/v/micro-fps.svg?style=flat-square)](https://www.npmjs.com/package/micro-fps)
[![Travis](https://img.shields.io/travis/victornpb/micro-fps/master.svg?style=flat-square)](https://travis-ci.org/victornpb/micro-fps)
[![David](https://img.shields.io/david/victornpb/micro-fps.svg?style=flat-square)](https://david-dm.org/victornpb/micro-fps)
[![Coverage Status](https://img.shields.io/coveralls/victornpb/micro-fps.svg?style=flat-square)](https://coveralls.io/github/victornpb/micro-fps)
[![NPM](https://img.shields.io/npm/dt/micro-fps.svg?style=flat-square)](https://www.npmjs.com/package/micro-fps)

> A super lightweight fps meter, with near zero overhead

*createFpsMeter* is a function factory, it returns a new meter.  
But why not a class? Last time I checked, accessing instance properties was slower than accessing variables on a near closure.

### Usage

JS fiddle Example: https://jsfiddle.net/Victornpb/g8pra2a6/

```js
import microFps from 'micro-fps';

```

    const REFRESH_RATE = 2; //update twice a second
    
    const fpsTick = createFpsMeter(info=>{
	    fps_div.innerHTML = info.fps.toFixed(2);
	    console.log(info);
    }, REFRESH_RATE);
    
    
Then call the returned function on every frame of your loop    
    
    //game loop
    setInterval(function loop(){
        fpsTick();
        
        //do stuff
    
    }, 1000/60);
    
 
Callback info object

| property | type    | description                                           |
|----------|---------|-------------------------------------------------------|
| fps      | float   | The calculated frames per second                      |
| jitter   | float   | The absolute difference since the last calculated fps |
| elapsed  | float   | Milliseconds ellapsed since the last computation      |
| frames   | integer | Number of frames since the last computation           |
| trigger  | float   | Next computation will happen at this amount of frames |


### Installation

Install via [yarn](https://github.com/yarnpkg/yarn)

	yarn add micro-fps (--dev)

or npm

	npm install micro-fps (--save-dev)


### configuration

You can pass in extra options as a configuration object (➕ required, ➖ optional, ✏️ default).

```js
import microFps from 'micro-fps';

```

➖ **property** ( type ) ` ✏️ default `
<br/> 📝 description
<br/> ❗️ warning
<br/> ℹ️ info
<br/> 💡 example

### methods

#### #name

```js
microFps

```

### Examples

See [`example`](example/script.js) folder or the [runkit](https://runkit.com/victornpb/micro-fps) example.

### Builds

If you don't use a package manager, you can [access `micro-fps` via unpkg (CDN)](https://unpkg.com/micro-fps/), download the source, or point your package manager to the url.

`micro-fps` is compiled as a collection of [CommonJS](http://webpack.github.io/docs/commonjs.html) modules & [ES2015 modules](http://www.2ality.com/2014/0
  -9/es6-modules-final.html) for bundlers that support the `jsnext:main` or `module` field in package.json (Rollup, Webpack 2)

The `micro-fps` package includes precompiled production and development [UMD](https://github.com/umdjs/umd) builds in the [`dist/umd` folder](https://unpkg.com/micro-fps/dist/umd/). They can be used directly without a bundler and are thus compatible with many popular JavaScript module loaders and environments. You can drop a UMD build as a [`<script>` tag](https://unpkg.com/micro-fps) on your page. The UMD builds make `micro-fps` available as a `window.microFps` global variable.

### License

The code is available under the [MIT](LICENSE) license.

### Contributing

We are open to contributions, see [CONTRIBUTING.md](CONTRIBUTING.md) for more info.

### Misc

This module was created using [generator-module-boilerplate](https://github.com/duivvv/generator-module-boilerplate).
