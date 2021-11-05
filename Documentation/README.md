# How to Access JWT Token?
`npm install react-native-bm7-component`

*note: set up the .npmrc first before install this library*
## React-Native
````
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
````
## ReactJs
````
import React from 'react';
import { useSelector } from 'react-redux';
import { IAuthReducerState } from 'react-native-bm7-component/lib/typescript/redux/auth/auth.interface';

const ComponentA = () => {
  // get token
  const token = useSelector((state: { auth: IAuthReducerState }) => state.auth.res);
  // use this token to access the API
  return <div>...render your view here</div>
}

export default ComponentA
````
