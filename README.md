

requirejs extend to support more platform and support custom resource(script) provider.

about requirejs: https://requirejs.org/

## feature:

1. Add resource provider, to custom url processor.

```javascript

requirejs.config({
    resourceProvider:async (modName:string,url:string)=>{
        if(modName='test/requirejs/resourceProvider'){
            return `define(['require','exports'],function(require,exports){
                console.log('hello amd');
                exports.hello='amd'
            })`;
        }else if(modName='test/requirejs/resourceProvider2'){
            return define(['require','exports'],function(require,exports){
                return {hello:'amd'}
            });
        }
        return null;
    }
})

```

2. Remove commonjs convertor, to avoid unexpected performance effect.

3. Save IIFE call to make it easier and faster to be used in Web Worker (experiment)

## TODO:
import hook
