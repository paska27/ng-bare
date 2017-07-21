## Rationale
Angular's [QuickStart](https://angular.io/guide/quickstart) is good to fastly start a new ng app and play around to understand  
if it worth using angular for particular needs.

Although when choise is made and starting a new ng app, quick start doesn't seem to be a good option,  
because it comes with whole lot of stuff which is definitelly not needed on the very born of the app,  
and possibly not even in the future.

Also, setting up a "bare" boilerplate will help to learn and understand why particular part is needed,  
along the way of the app evolution.

Unfortunatelly a little documentation on the matter of setting up an angular app from blank as well as  
about some core packages is in the wild.

This repo serves two goals:
- set up a bare minimum to start ng app
- hold some description about each of the parts

## Installation
```bash
git clone https://github.com/paska27/ng-bare my-ng-app && cd my-ng-app
npm install @angular/cli -g && npm install
ng-build
# or ng-serve for JIT compiler
```
## Description
- Basic @angular packages can be found [here](https://github.com/angular/angular/tree/master/packages).
- [/.angular-cli.json](https://github.com/paska27/ng-bare/blob/master/.angular-cli.json)  
Instructions for ng cli according to [schema](https://github.com/paska27/ng-bare/blob/master/.angular-cli.json).  
Some of bare settings are not obvious:  
  - `root`. actually equiualent for `ng new --source-dir` which how it should be called in `.angular-cli.json` :question:
  - `tsconfig`. actually src ts config and should be relative to "root" and _has_ to be present :confused:
  - `polyfills`. seems like optional from first glance, but app won't run without the minimum (see polyfills section below)
- [/tsconfig.json](https://github.com/paska27/ng-bare/blob/master/tsconfig.json)  
Type script to java script compiltion rules. Well described [here](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html). And also [/src/tsconfig.app.json](https://github.com/paska27/ng-bare/blob/master/src/tsconfig.app.json) which has to be there,  
but not really used on the first stage.
- [polyfills.ts](https://github.com/paska27/ng-bare/blob/master/src/polyfills.ts)  
The file itself gives a good explanation. Though not really clear why not to include `zone.js` into main angular package itself (e.g. core) :question:.
- The rest is describe in [quick start](https://angular.io/guide/quickstart) [bootstrapping](https://angular.io/guide/bootstrapping) sections.
