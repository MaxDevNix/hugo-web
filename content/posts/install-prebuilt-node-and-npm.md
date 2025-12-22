+++
title = "Installing prebuilt Node and NPM"
date = "2025-11-01T19:05:19+01:00"
tags = ["Linux", "Dev", "Errors Fixes", ]
draft = true
featured_image = "/thumbs/{year-image.png}"
+++

<!--more-->
I have downloaded `node` and `npm` from [nodejs.org/en/download](https://nodejs.org/en/download)
by clicking on the green button `Standalone Binary (.xz)`
and extracted it with `tar xJvf ~/Download/node-<VERSION>-linux-x64.tar.xz -C ~/.local/bin/node-<VERSION>-linux-x64`

## Troubleshooting
### Error: When I run `npm ...` (any argument), it throws an error message:
```javascript
node:internal/modules/cjs/loader:1423
  throw err;
  ^

Error: Cannot find module '/path/to/node-<VERSION>-linux-x64/bin/node_modules/npm/bin/npm-prefix.js'
    at Module._resolveFilename (node:internal/modules/cjs/loader:1420:15)
    at defaultResolveImpl (node:internal/modules/cjs/loader:1058:19)
    at resolveForCJSWithHooks (node:internal/modules/cjs/loader:1063:22)
    at Module._load (node:internal/modules/cjs/loader:1226:37)
    at TracingChannel.traceSync (node:diagnostics_channel:328:14)
    at wrapModuleLoad (node:internal/modules/cjs/loader:244:24)
    at Module.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:154:5)
    at node:internal/main/run_main_module:33:47 {
  code: 'MODULE_NOT_FOUND',
  requireStack: []
}
Node.js <VERSION>
Could not determine Node.js install directory
```

### Fix/Solution
`$PATH` must contain `/path/to/node-<VERSION>-linux-x64/bin`, but not `/path/to/node-<VERSION>-linux-x64/bin/node_modules/npm/bin`

### Explanation


<!--end-->
