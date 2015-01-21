# meteor-reactivity-bug

Meteor does not recognize all NPM modules. E.g.`require('react/addons')` is a valid syntax for Node, but not for Meteor. :(

```
$ meteor
[[[[[ ~/tmp/myapp ]]]]]                       

=> Started proxy.                             
mypackage: updating npm dependencies -- react...
=> Started MongoDB.                           
W20150121-23:31:31.067(0)? (STDERR)           
W20150121-23:31:31.068(0)? (STDERR) /Users/hipertracker/.meteor/packages/meteor-tool/.1.0.40.joq2z8++os.osx.x86_64+web.browser+web.cordova/meteor-tool-os.osx.x86_64/dev_bundle/server-lib/node_modules/fibers/future.js:173
W20150121-23:31:31.068(0)? (STDERR) 						throw(ex);
W20150121-23:31:31.068(0)? (STDERR) 						      ^
W20150121-23:31:31.068(0)? (STDERR) Error: Can't find npm module 'react/addons'. Did you forget to call 'Npm.depends' in package.js within the 'mypackage' package?
W20150121-23:31:31.068(0)? (STDERR)     at Object.Npm.require (/Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/boot.js:147:17)
W20150121-23:31:31.068(0)? (STDERR)     at Package (packages/mypackage/mypackage.js:1:1)
W20150121-23:31:31.068(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/packages/mypackage.js:22:4
W20150121-23:31:31.068(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/packages/mypackage.js:29:3
W20150121-23:31:31.069(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/boot.js:205:10
W20150121-23:31:31.069(0)? (STDERR)     at Array.forEach (native)
W20150121-23:31:31.069(0)? (STDERR)     at Function._.each._.forEach (/Users/hipertracker/.meteor/packages/meteor-tool/.1.0.40.joq2z8++os.osx.x86_64+web.browser+web.cordova/meteor-tool-os.osx.x86_64/dev_bundle/server-lib/node_modules/underscore/underscore.js:79:11)
W20150121-23:31:31.069(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/boot.js:116:5
=> Exited with code: 8

```
$ meteor
[[[[[ ~/tmp/myapp ]]]]]

=> Started proxy.
=> Started MongoDB.
W20150121-22:53:39.192(0)? (STDERR)
W20150121-22:53:39.193(0)? (STDERR) /Users/hipertracker/.meteor/packages/meteor-tool/.1.0.40.joq2z8++os.osx.x86_64+web.browser+web.cordova/meteor-tool-os.osx.x86_64/dev_bundle/server-lib/node_modules/fibers/future.js:173
W20150121-22:53:39.193(0)? (STDERR) 						throw(ex);
W20150121-22:53:39.193(0)? (STDERR) 						      ^
W20150121-22:53:39.193(0)? (STDERR) Error: Can't find npm module 'react/addons'. Did you forget to call 'Npm.depends' in package.js within the 'mypackage' package?
W20150121-22:53:39.193(0)? (STDERR)     at Object.Npm.require (/Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/boot.js:147:17)
W20150121-22:53:39.193(0)? (STDERR)     at Package (packages/mypackage/mypackage.js:2:1)
W20150121-22:53:39.193(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/packages/mypackage.js:19:4
W20150121-22:53:39.193(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/packages/mypackage.js:26:3
W20150121-22:53:39.193(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/boot.js:205:10
W20150121-22:53:39.194(0)? (STDERR)     at Array.forEach (native)
W20150121-22:53:39.194(0)? (STDERR)     at Function._.each._.forEach (/Users/hipertracker/.meteor/packages/meteor-tool/.1.0.40.joq2z8++os.osx.x86_64+web.browser+web.cordova/meteor-tool-os.osx.x86_64/dev_bundle/server-lib/node_modules/underscore/underscore.js:79:11)
W20150121-22:53:39.194(0)? (STDERR)     at /Users/hipertracker/tmp/myapp/.meteor/local/build/programs/server/boot.js:116:5
=> Exited with code: 8
```
