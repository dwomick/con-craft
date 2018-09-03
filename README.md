[![Built with pwa–starter–kit](https://img.shields.io/badge/built_with-pwa–starter–kit_-blue.svg)](https://github.com/Polymer/pwa-starter-kit "Built with pwa–starter–kit")
[![Build status](https://api.travis-ci.com/notwaldorf/flash-cards.svg?branch=master)](https://travis-ci.com/notwaldorf/flash-cards)
## Setup

```
git clone https://github.com/dwomick/con-craft
cd con-craft
npm install
npm start
```

To run the tests, you can run `npm run test`.

## Build and deploy (notwaldorf's original notes)

To build the app, run `npm run build`. This will create a `build` folder that has all the minified 
bundles and assets you need to deploy. If you want to test that the build output works, you can run

```
npm run serve
```

For deployment, I used [Netlify](https://www.netlify.com/)'s 
pretty much out-of-the-box setup. These are my deploy settings (so that the app is rebuilt and
the bundled app is redeployed every time there's a new commit to master):
<img width="400" alt="screenshot of netlify deploy settings" src="https://user-images.githubusercontent.com/1369170/40515314-27b427a2-5f61-11e8-83de-dd99701d79fe.png">

Since this app is structured as an `app-shell` (the `index.html` knows how to display the correct route based on the URL, but each URL does not correspond to a standalone view you can just load), I've also added a [`_redirects file`](https://github.com/notwaldorf/flash-cards/blob/master/_redirects) used by the Netlify server tohandle these redirects (read more about that [here](https://www.netlify.com/docs/redirects/#history-pushstate-and-single-page-apps))

### Supported browsers
This app uses the `es5-bundled` bundle, so that it works on browsers up to IE11, as well as Googlebot (so that it can get indexed).

