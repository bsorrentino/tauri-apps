# Transform URL to APP using [tauri]  

## Steps

1. create new application
```
npm create tauri-app@latest apps/<app name> --template vanilla
```
2. add `build` and `clean` scripts to package.json
open `apps/<app name>/package.json` and update scripts as follows:
```json
"scripts": {
    "build": "tauri build",
    "clean": "cargo clean --manifest-path src-tauri/Cargo.toml",
    "tauri": "tauri"
  }
```
3. Open `apps/<app name>/src-tauri/tauri.conf.json` and :
  * update `bundle/idenfifier` with an unique name
  * Optionally update `windows/title` with the app display name
  * add `url` attribute with the initial url to open on launch:

4. Optionally update the application icon replacing the icon file with yours in `apps/<app name>/src-tauri/icons` folder

5. Build the App

From root folder run 
```
npx lerna run build --scope=<app name>
```  

[tauri]: https://tauri.app