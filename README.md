# Crypto-Vue

This project is a very basic boilerplate for using [Staticrypt](https://github.com/robinmoisson/staticrypt) for Vue as a Single Page Application. Staticrypt is based on [crypto-js](https://github.com/brix/crypto-js). The goal of this is to create a "passphrase-protected-website". Because a Vue project builds a single index.html file, this does a good job at encrypting the entire site. 

There are some security vulnerabilities with this, namely that the content is technically inside the `.js` files which are not encrypted, but knowing the names of those files is difficult. Staticrypt also mentions that their weakness is brute force, so make sure the passphrase is not `asdf`, like this project boilerplate. One good place to check your passphrase security is https://howsecureismypassword.net/. This is a good solution for static websites that need basic authentication with little setup. If you are aiming for top-notch security, look elsewhere. 

## Project setup

First thing, install the node packages with `npm install`. To serve the Vue project with hot reloading, run `npm run serve`. At this point, the encryption process has not done anything.

One note about the setup is that this project has [Vue Auto Routing](https://github.com/ktsn/vue-cli-plugin-auto-routing) set up, so the routes are based on the file path in the `pages` directory. Otherwise, it is a pretty standard Vue 2 starter project.

### Compiles, minifies, and encrypts for production

To compile and encrypt the SPA, run `npm run build`. This is a chained command that compiles the SPA and afterwards encrypts it with the boilerplate that we chose. The boilerplate is called `pwd-template.html`. Feel free to edit this to your hearts content. If you want to change any of the encryption options, edit the command in the `package.json` file under `scripts`.

One special thing that the `pwd-template.html` does that was not included in Staticrypt's example, is that the user can choose to remember the password, saving thier input in their localstorage. Then, if they return to the site, they do not need to put in the passphrase and can continue using the app. If they clear their localstorage or use a different browser, they will need to re-enter the passphrase.

## Disclaimer!!!

This is not thoroughly tested, and I am not a web-security expert, so take this as-is.
