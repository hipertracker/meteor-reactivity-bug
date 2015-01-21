# meteor-reactivity-bug

Meteor does not recognize all NPM packages. E.g.`require('react/addons')` is a valid syntax for Node, but not for Meteor. 

```
$ meteor
[[[[[ ~/tmp/meteor-reactivity-bug ]]]]]       

=> Started proxy.                             
mypackage: updating npm dependencies -- react...
=> Started MongoDB.                           
W20150121-23:47:35.885(0)? (STDERR)           
W20150121-23:47:35.886(0)? (STDERR) /Users/hipertracker/.meteor/packages/meteor-tool/.1.0.40.joq2z8++os.osx.x86_64+web.browser+web.cordova/meteor-tool-os.osx.x86_64/dev_bundle/server-lib/node_modules/fibers/future.js:173
W20150121-23:47:35.886(0)? (STDERR) 						throw(ex);
W20150121-23:47:35.886(0)? (STDERR) 						      ^
W20150121-23:47:35.886(0)? (STDERR) Error: Can't find npm module 'react/addons'. Did you forget to call 'Npm.depends' in package.js within the 'mypackage' package?
W20150121-23:47:35.886(0)? (STDERR)     at Object.Npm.require (/Users/hipertracker/tmp/meteor-reactivity-bug/.meteor/local/build/programs/server/boot.js:147:17)
W20150121-23:47:35.886(0)? (STDERR)     at Package (packages/mypackage/mypackage.js:1:1)
W20150121-23:47:35.886(0)? (STDERR)     at /Users/hipertracker/tmp/meteor-reactivity-bug/.meteor/local/build/programs/server/packages/mypackage.js:28:4
W20150121-23:47:35.887(0)? (STDERR)     at /Users/hipertracker/tmp/meteor-reactivity-bug/.meteor/local/build/programs/server/packages/mypackage.js:35:3
W20150121-23:47:35.887(0)? (STDERR)     at /Users/hipertracker/tmp/meteor-reactivity-bug/.meteor/local/build/programs/server/boot.js:205:10
W20150121-23:47:35.887(0)? (STDERR)     at Array.forEach (native)
W20150121-23:47:35.887(0)? (STDERR)     at Function._.each._.forEach (/Users/hipertracker/.meteor/packages/meteor-tool/.1.0.40.joq2z8++os.osx.x86_64+web.browser+web.cordova/meteor-tool-os.osx.x86_64/dev_bundle/server-lib/node_modules/underscore/underscore.js:79:11)
W20150121-23:47:35.887(0)? (STDERR)     at /Users/hipertracker/tmp/meteor-reactivity-bug/.meteor/local/build/programs/server/boot.js:116:5
=> Exited with code: 8
```

In that particular case, there is a workaround thanks to'react-addons' package.
```
React = require('react');
React.addons = require('react-addons');
```



