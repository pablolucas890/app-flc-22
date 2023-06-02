# Appp do Forro da Lua Cheia

## Configure Ambient

### All Ambientes:

- NodeJs Version: `16.20.0`

## Android:

- Create `local.properties` file on `android/` with that content:
```
sdk.dir = /home/$USER/Android/Sdk/
cmake.dir = /home/$USER/Android/Sdk/cmake/$CMAKE_VERSION
```
- Install adb: `sudo apt install android-tools-adb android-tools-fastboot`

---

## Development

### All Ambientes:
- Go to ambient branch:
  `git checkout android|ios`
- Edit files an see editions with fast rebuild on browser:
  `npm run serve`
- Build content files to generate apps (android and ios):
  `npm run build`
- Generate splash screen and ic_laucher to android and ios
  `npm run generate-splash`
- If you have the app installed before the build, uninstall it, because the app save on storage the old images and you needs remove to edit
- Remove all images from the builds folders to app update with your images editions
  - On android its localizated o `android/app/src/main/assets/public` so run `sudo rm -r android/app/src/main/assets/public`
  - On ios its localizated o `ios/App/App/public` so run `sudo rm -r ios/App/App/public`

### Android

- Build apk and install on emulator device:
  - Start emulator
  - Note the emulator name with: `adb devices | grep -v '^$' | tail -n 1 | awk '{print $2}'`
  - Change the emulator-5554 name on package.json to emulator name noted
  - Run `npm run android`
(If have some error, open the Android Studio with (`npx ionic cap open android`) and build app with IDE)

### IOS

- Run `npx ionic cap open ios`
- On Xcode, build app
(If Xcode build return some error, comment the lines with careful to don't remove important things and build again)