![Tube Archivist Companion](assets/tube-archivist-companion-banner.png?raw=true "Tube Archivist Companion Banner")  

<h1 align="center">Browser Extension for Tube Archivist</h1>
<div align="center">
<a href="https://addons.mozilla.org/addon/tubearchivist-companion/" target="_blank"><img src="https://tiles.tilefy.me/t/tubearchivist-firefox.png" alt="tubearchivist-firefox" title="TA Companion Firefox users" height="50" width="190"/></a>
<a href="https://chrome.google.com/webstore/detail/tubearchivist-companion/jjnkmicfnfojkkgobdfeieblocadmcie" target="_blank"><img src="https://tiles.tilefy.me/t/tubearchivist-chrome.png" alt="tubearchivist-chrome" title="TA Companion Chrome users" height="50" width="190"/></a>
</div>

## Screenshots
![popup screenshot](assets/tac-screenshot.png?raw=true "Tube Archivist Companion Popup")
Popup to enter your connection details.
<br><br>

![video page](assets/screenshot-video.png?raw=true "Tube Archivist Companion Video Page")
Button injected on video page to download the video or subscribe to the channel.
<br><br>

![search page](assets/tac-screenshot-search.jpg?raw=true "Tube Archivist Companion Search Page")
Download button injected showing when hovering over the video title.
<br><br>

![channel page](assets/tac-screenshot-channel.jpg?raw=true "Tube Archivist Companion Channel Page")
Channel button injected to subscribe or download whole channel, video download button showing when hovering over the video title.
<br>

## Install
- Firefox: The addon is available on the [Extension store](https://addons.mozilla.org/addon/tubearchivist-companion/).
- Chrome: The addon is available on the [Chrome Web Store](https://chrome.google.com/webstore/detail/tubearchivist-companion/jjnkmicfnfojkkgobdfeieblocadmcie).

## Docs
User documentation is available on the official documentation page: [https://docs.tubearchivist.com/browser-extension/user-docs/](https://docs.tubearchivist.com/browser-extension/user-docs/).

This documentation is built from a separate repo at [tubearchivist/docs](https://github.com/tubearchivist/docs).

## Dev setup
Before continuing loading the temporary extension here, make sure to deactivate/delete the main extension first.

Symlink/copy the correct manifest file for your browser to the expected location, e.g. `ln -s manifest-firefox.json manifest.json`.

- Firefox
  - Open `about:debugging#/runtime/this-firefox`
  - Click on *Load Temporary Add-on*
  - Select the *manifest.json* file to load the addon.
  - You can *inspect* background.js by lunching the debug tools from there.
- Chrome / Chromium
  - Open `chrome://extensions/`
  - Toggle *Developer mode* on top right
  - Click on *Load unpacked*
  - Open the folder containing the *manifest.json* file.
  - Click on *Service Worker* to open the dev tools at background.js. 

Note:
- If you are running your TA dev setup outside of the container, you need to point the URL to the API backend and _not_ the frontend. E.g. localhost:8000 and not localhost:3000.

## Roadmap
Join us on [Discord](https://www.tubearchivist.com/discord) and help us improve and extend this project. This is a list of planned features, in no particular order:
- [ ] Implement download/subscribe button for playlists
- [ ] Add download buttons to the `/shorts/` pages
- [X] Get download and subscribe status from TA to show on the injected buttons
- [X] Implement download button for videos on the YouTube homepage over inline preview
- [X] Implement download button for videos on playlist
- [X] Error handling for connection errors
- [X] Dynamically inject buttons with mutation observer

## Making changes to the JavaScript
The JavaScript does not require any build step; you just edit the files directly. However, there is config for eslint and prettier (a linter and formatter respectively); their use is recommended but not required. To use them, install `node`, run `npm i` from the root directory of this repository to install dependencies, then run `npm run lint` and `npm run format` to run eslint and prettier respectively.

## Updating Artwork
Google listing is *very* picky. Screenshots need to be exactly **1280x800** in resolution and need to be in *jpg* or *png* without alpha channel.
