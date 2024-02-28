# `npx` doesn’t seem to consider globally installed namespaced packages

## Installation

I installed this package via `sudo npm link` (without publishing it to the registry).

Result:

```
% npm ls -g
/usr/local/lib
├── @rauschma/hello@1.0.0 -> ./../../../Users/rauschma/tmp/hello
├── corepack@0.24.0
├── npm@10.2.4
└── typescript@5.3.3
```

## Interaction

I’m unable to use `npx @rauschma/hello`:

```
% cd $HOME

% hello
Hello!

% npx hello
Hello!

% npx @rauschma/hello
npm ERR! code E404
npm ERR! 404 Not Found - GET https://registry.npmjs.org/@rauschma%2fhello - Not found
npm ERR! 404 
npm ERR! 404  '@rauschma/hello@*' is not in this registry.
npm ERR! 404 
npm ERR! 404 Note that you can also install from a
npm ERR! 404 tarball, folder, http url, or git url.

% npx --package @rauschma/hello hello   
npm ERR! code E404
npm ERR! 404 Not Found - GET https://registry.npmjs.org/@rauschma%2fhello - Not found
npm ERR! 404 
npm ERR! 404  '@rauschma/hello@*' is not in this registry.
npm ERR! 404 
npm ERR! 404 Note that you can also install from a
npm ERR! 404 tarball, folder, http url, or git url.
```
