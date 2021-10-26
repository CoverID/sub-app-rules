# Sub-App SuperApp

## Registration

### Data
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
5. `iOSDeeplinkUrl`: deeplink url for ios app (for `Native` app)
6. `androidDeeplinkUrl`: deeplink url for android app (for `Native` app)
7. `appUrl`: application url (for `SPA` app)

### Icon
- 64x64 pixel
- Size below 50kb

## Publishing (`React-Native or React Library`)
1. Request personal access token (PAT) for npm authentication `(Azure Artifacs)`
2. Set up .npmrc `(Azure Artifacs)`
3. Create CI/CD and publish to Private DevOps SuperApp
4. Request SuperApp to set up the instalation Library

## For Application Type: `SPA`
* Web App wil be automatically linked
* Mobile App should request SuperApp to set up the instalation link
