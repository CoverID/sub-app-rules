**ReactNative Dependency**
- "react": "16.9.0"
- "react-native": "^0.63.3"
- "typescript": "^3.7.3"

**ReactJs Dependency**
- "@types/react": "^17.0.3"
- "@types/react-dom": "^17.0.2"
- "@types/react-router-dom": "^5.1.7"
- "react-dom": "^17.0.2"
- "react": "^17.0.2"
- "react-router-dom": "^5.2.0"
- "react-scripts": "^3.4.3"

# 1. How to Access JWT Token?
## ReactNative
`npm install react-native-bm7-component`

*note: set up the .npmrc first to install this library*
```
import React from 'react';
import { Text, View } from 'react-native';
import { useSelector } from 'react-redux';
import { IAuthReducerState } from 'react-native-bm7-component/lib/typescript/redux/auth/auth.interface';

const ComponentA = () => {
  // get token
  const token = useSelector((state: { auth: IAuthReducerState }) => state.auth.res);
  // use this token to access the API
  return <View><Text>...render your view here</Text></View>
}

export default ComponentA
```
## ReactJs
`npm install react-js-bm7-component`

*note: set up the .npmrc first to install this library*
```
import React from 'react';
import { useSelector } from 'react-redux';
import { IUserFinalData } from 'react-js-bm7-component/lib/redux/auth/Auth.interfaces';

const ComponentA = () => {
  // get token
  const { token } = useSelector((state: { auth: { res: IUserFinalData } }) => state.auth.res);
  // use this token to access the API
  return <div>...render your view here</div>
}
```

# 2. How to Switch between Sub-App?
## ReactNative
`npm install react-native-bm7-component`

*note: set up the .npmrc first to install this library*
```
import React from 'react';
import { Text, TouchableOpacity, View } from 'react-native';
import { useSelector, useDispatch } from 'react-redux';
import { IProfileUser } from 'react-native-bm7-component/lib/typescript/redux/profile/profile.interfaces';
import { AppChild } from 'react-native-bm7-component/lib/typescript/interfaces';
import BM7Component from 'react-native-bm7-component';

const ComponentA = () => {
  const dispatch = useDispatch();
  // get token
  const { app } = useSelector((state: { home: { profile: { res: IProfileUser } } }) => state.home.profile.res);
  const appList = app.list.filter(item => item.appId !== app.active.appId)

  return <View>
    {appList.map((app: AppChild, index) => {
      return (
        <TouchableOpacity
          onPress={() => dispatch(BM7Component.Actions.profile.switchActiveApp(app))}
          key={index}
        >
          <Text>{app.appName}</Text>
        </TouchableOpacity>
      )
    })}
  </View>
}

export default ComponentA
```
## ReactJs
`npm install react-js-bm7-component`

*note: set up the .npmrc first to install this library*
```
import React from 'react';
import { useSelector } from 'react-redux';
import { IUserFinalData } from 'react-js-bm7-component/lib/redux/auth/Auth.interfaces';
import { AppChild } from 'react-js-bm7-component/lib/interface';

const ComponentA = () => {
  const dispatch = useDispatch();
  const { app } = useSelector((state: { auth: { res: IUserFinalData } }) => state.auth.res);
  //get the list of sub-apps
  const appList = app.list.filter((f: AppChild) => f.appId !== app.active.appId);
  
  return(
    appList.map((app: AppActive) => {
      ...render list of sub-apps, add default icon or something here...
      return (
        <Button onClick={() => dispatch(Actions.auth.superAppSetActive(app))}>Switch</Button>
      )
    })
  .......
```
