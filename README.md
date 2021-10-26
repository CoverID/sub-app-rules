# Sub-App Rules
## Register
1. `applicationId`: e.g. bundle identifier or some unique app id
2. `applicationName`: Name of the app
3. `developmentType`: `Mobile` or `Web`
4. `applicationType`:
> for `Mobile` development type
- `ReactNative` if the app built as `React-Native Library`, user access the app inside SuperApp
- `Native` if the app built with native framework or other framework than React-Native, SuperApp trigger to launch the app
- `SPA` user access the app with system browser like a website ***you need to handle authenticated method from SuperApp**
> for `Web` development type
- `React` if the app built as `React Library`, user access the app inside SuperApp
- `SPA` SuperApp trigger to open URL in a new tab  ***you need to handle authenticated method from SuperApp**

## Icon
- 64x64 pixel
- Size below 50kb
