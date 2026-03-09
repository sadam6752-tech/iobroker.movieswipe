# WWW Directory

This directory should contain the built PWA files from `movieswipe-pwa/dist/`.

## How to populate this directory:

1. Build the PWA:
   ```bash
   cd movieswipe-pwa
   npm run build
   ```

2. Copy the dist files:
   ```bash
   cp -r movieswipe-pwa/dist/* iobroker-adapter-movieswipe/iobroker.movieswipe/www/
   ```

The web server will serve these static files when the adapter is running.
