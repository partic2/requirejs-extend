

requirejs extend to support more platform and support custom resource(script) provider.

about requirejs: https://requirejs.org/

## feature:

resource provider:

```javascript

requirejs.config({
    resourceProvider:async (modName:string,url:string)=>{
        if(modName='test/requirejs/resourceProvider'){
            return `define(['require','exports'],function(require,exports){
                console.log('hello amd');
                exports.hello='amd'
            })`;
        }
        return null;
    }
})

```

## TODO:
import hook
