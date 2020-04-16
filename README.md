# Patching FirebaseUI With A Localized Build

Building a custom FirebaseUI is a tedious process, first and foremost because the build process is utterly complex and [broken on OSX](https://github.com/firebase/firebaseui-web/issues/679).

This repo contains a stripped-down version of the build, which e.g. skips all CSS, SASS, and testing artifact generation.

It is a good basis if you just want to **override all text in your language of choice**. 

_Note: Examples are given for the 'de' locale, but any of the [supported locales](https://github.com/firebase/firebaseui-web/blob/master/LANGUAGES.md) will work_

## Installing Dependencies
```
npm install
```

## Building Artifacts

### firebase.js
```
npm run build build-js-de
cp dist/firebaseui__de.js <path-to-your-project>/node_modules/firebaseui/dist/firebaseui.js
```

### npm.js
```
npm run build build-npm-de
cp dist/npm__de.js <path-to-your-project>/node_modules/firebaseui/dist/npm.js
```

## ems.js
```
npm run build build-esm-de
cp dist/esm__de.js <path-to-your-project>/node_modules/firebaseui/dist/esm.js
```

## Usage In Your Project

Once you patched the `firebase.js`, `npm.js`, and `esm.js` files in your project's `node_modules/firebaseui`
as described above, use [patch-package](https://www.npmjs.com/package/patch-package) to cleanly maintain
the patches and keep them under version control.

# ! DISCLAIMER – USE AT YOUR OWN RISK !