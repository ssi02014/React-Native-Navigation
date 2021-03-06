# ๐ป React-Native-Navigation
### React-Native-Navigation ์ ์ฅ์

<br />

## ๐ฅ App View
### ๐บ Stack Navigation
<p align='center'>
    <img src='https://user-images.githubusercontent.com/64779472/114034632-50637880-98b9-11eb-98d8-a2111e389a09.PNG' width="400" height="730">
</p>

<br />

### ๐บ Tab Navigation
<p align='center'>
    <img src='https://user-images.githubusercontent.com/64779472/114034024-c87d6e80-98b8-11eb-907a-86fe74ce34c2.PNG' width="400" height="730">
</p>

<br />

## ๐จ๐ปโ๐ป React Navigation
๐ https://reactnavigation.org/

- ๋ฆฌ์กํธ ๋ค์ดํฐ๋ธ์์๋ ๋ด๋น๊ฒ์ด์ ๊ธฐ๋ฅ์ ์ง์ํ์ง ์์ผ๋ฏ๋ก ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ด์ฉํด์ผ ํ๋ค.
- ๋ฆฌ์กํธ ๋ด๋น๊ฒ์ด์ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ๋ฆฌ์กํธ ๋ค์ดํฐ๋ธ ์ ํ๋ฆฌ์ผ์ด์์ ๋ด๋น๊ฒ์ด์์ ์ฝ๊ณ  ๊ฐ๋จํ๊ฒ ๊ด๋ฆฌํ  ์ ์๋๋ก ๋์์ค๋ค.
- ๋ด๋น๊ฒ์ด์ ์ข๋ฅ๋ก๋ ์คํ(stack), ํญ(tab), ๋๋ก์ด(drawer) ์ธ ์ข๋ฅ๊ฐ ์๋ค.

```javascript
    //install
    yarn add @react-navigation/native

    //๋ด๋น๊ฒ์ด์์์ ํ์ํ ์ข์์ฑ ์ค์น
    expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view
```
<br />

### ๐ ๋ด๋น๊ฒ์ด์ ๊ตฌ์กฐ

- ๋ฆฌ์กํธ ๋ด๋น๊ฒ์ด์์๋ NavigationContainer ์ปดํฌ๋ํธ, Navigation, Screen ์ปดํฌ๋ํธ๊ฐ ์๋ค.
- **Screen ์ปดํฌ๋ํธ**๋ ํ๋ฉด์ผ๋ก ์ฌ์ฉ๋๋ ์ปดํฌ๋ํธ์ด๋ค. name๊ณผ component ์์ฑ์ ์ง์ ํด์ผ ํ๋ค. name์ ํ๋ฉด ์ด๋ฆ์ผ๋ก ์ฌ์ฉ๋๋ฉฐ, component์๋ ํ๋ฉด์ผ๋ก ์ฌ์ฉ ๋  ์ปดํฌ๋ํธ๋ฅผ ์ ๋ฌํ๋ค.
- **Navigation ์ปดํฌ๋ํธ**๋ ํ๋ฉด์ ๊ด๋ฆฌํ๋ ์ค๊ฐ ๊ด๋ฆฌ์ ์ญํ ๋ก ๋ด๋น๊ฒ์ด์์ ๊ตฌ์ฑํ๋ฉฐ, ์ฌ๋ฌ ๊ฐ์ Screen ์ปดํฌ๋ํธ๋ฅผ ์์ ์ปดํฌ๋ํธ๋ก ๊ฐ๊ณ  ์๋ค.
- **NavigationContainer ์ปดํฌ๋ํธ**๋ ๋ด๋น๊ฒ์ด์์ ๊ณ์ธต ๊ตฌ์กฐ์ ์ํ๋ฅผ ๊ด๋ฆฌํ๋ ์ปจํ์ด๋ ์ญํ ์ ํ๋ฉฐ, ๋ชจ๋  ๋ด๋น๊ฒ์ด์ ๊ตฌ์ฑ ์์๋ฅผ ๊ฐ์ผ ์ต์์ ์ปดํฌ๋ํธ์ฌ์ผ ํ๋ค.

![1](https://user-images.githubusercontent.com/64779472/113977703-f1ccd900-987d-11eb-9cb0-5b3acca8302d.PNG)

<br />

### ๐ ์ค์  ์ฐ์  ์์

- ๋ฆฌ์กํธ ๋ด๋น๊ฒ์ด์์์ ์ค์ ํ  ์ ์๋ ๋ค์ํ ์์ฑ์ ์์ ํ๋ ๋ฐฉ๋ฒ
    1. Navigation ์ปดํฌ๋ํธ์ ์์ฑ์ผ๋ก ์์ ํ๋ ๋ฐฉ๋ฒ
    2. Screen ์ปดํฌ๋ํธ์ ์์ฑ์ผ๋ก ์์ ํ๋ ๋ฐฉ๋ฒ
    3. ํ๋ฉด์ผ๋ก ์ฌ์ฉ๋๋ ์ปดํฌ๋ํธ์ props๋ก ์ ๋ฌ๋๋ navigation์ ์ด์ฉํด์ ์์ ํ๋ ๋ฐฉ๋ฒ
- ์์ ๋ฐฉ๋ฒ ์ค 1๋ฒ์ ์์ ์ปดํฌ๋ํธ๋ก ์กด์ฌํ๋ ๋ชจ๋  ์ปดํฌ๋ํธ์ ์ ์ฉ๋๋ ํน์ง์ด ์๋ค. 2, 3๋ฒ์ ํด๋น ํ๋ฉด์๋ง ์ ์ฉ๋๋ค. ๊ทธ๋ ๊ธฐ์ ๊ณตํต์ ์ผ๋ก ์ ์ฉํ๊ณ  ์ถ์ ์์ฑ์ 1๋ฒ์ ์ ํํ๊ณ , ๊ฐ๋ณ ํ๋ฉด์๋ง ์ ์ฉ์ํค๊ณ  ์ถ์ ๊ฒฝ์ฐ์๋ 2, 3๋ฒ์ ์ฌ์ฉํ๋ค.
- ์์ ๋ฒ์์ ์ค์ ์ผ์๋ก ์ฐ์ ์์๊ฐ ๋์์ง๋ค. (๊ทธ๋ฆผ ์ฐธ๊ณ )

![2](https://user-images.githubusercontent.com/64779472/113978202-9cdd9280-987e-11eb-89ca-b02a1b1dcb7c.PNG)

<br />


## ๐จ๐ปโ๐ป ์คํ ๋ด๋น๊ฒ์ด์
### ๐ ํ๋ฉด ๊ตฌ์ฑ
- ์คํ ๋ด๋น๊ฒ์ด์์ ๊ฐ์ฅ ๊ธฐ๋ณธ์ ์ธ ๋ด๋น๊ฒ์ด์์ผ๋ก, ํ์ฌ ํ๋ฉด ์์ ๋ค๋ฅธ ํ๋ฉด์ ์์ผ๋ฉด์ ํ๋ฉด์ ์ด๋ํ๋ ๊ฒ์ด ํน์ง์ด๋ค.
- ์คํ ๋ด๋น๊ฒ์ด์์ ํ๋ฉด ์์ ์๋ก์ด ํ๋ฉด์ ์์ผ๋ฉด์(push) ์ด๋ํ๊ธฐ ๋๋ฌธ์ ์ด์  ํ๋ฉด์ ๊ณ์ ์ ์งํด์ผํ๋ค. ์ด๋ฐ ๊ตฌ์กฐ ๋๋ฌธ์ ๊ฐ์ฅ ์์ ์๋ ํ๋ฉด์ ๋ค์ด๋ด๋ฉด(pop) ์ด์  ํ๋ฉด์ผ๋ก ๋์๊ฐ ์ ์๋ค๋ ํน์ง์ด ์๋ค.

![3](https://user-images.githubusercontent.com/64779472/113979463-38233780-9880-11eb-9c9f-6b665bbe6442.PNG)

```javascript
    //install
    yarn add @react-navigation/stack

    //import 
    import {createStackNavigator} from '@react-navigation/stack';

    //component import
    import Home from '../screens/Home';
    import Item from '../screens/Item';
    import List from '../screens/List';

    // ์คํ ๋ด๋น๊ฒ์ด์ ์์ฑ
    const Stack = createStackNavigator();

    // ํ๋ฉด์ ๊ตฌ์ฑํ๋ Screen, Screen์ ๊ด๋ฆฌํ๋ Navigator ์ปดํฌ๋ํธ
    return (
        <Stack.Navigator>
            <Stack.Screen name="Home" component={Home} />
            <Stack.Screen name="List" component={List} />
            <Stack.Screen name="Item" component={Item} />
        </Stack.Navigator>
    );
```

<br />

- ์คํ ๋ด๋น๊ฒ์ด์์์ ์ฒซ ๋ฒ์งธ ํ๋ฉด์ผ๋ก ๋์ค๋ ํ๋ฉด์ Navigator ์ปดํฌ๋ํธ์ ์ฒซ ๋ฒ์งธ ์์ Screen ์ปดํฌ๋ํธ์๋๋ค. ๋ง์ฝ ์์๋ฅผ ๋ณ๊ฒฝํ๋ค๋ฉด ์ฒซ ํ๋ฉด์ผ๋ก ๋ํ๋๋ ํ๋ฉด์ด ๋ฌ๋ผ์ง๋๋ค.
- ์ปดํฌ๋ํธ ์์๋ฅผ ๋ณ๊ฒฝํ๋ ๋ฐฉ๋ฒ ์ธ์๋ **initalRouteName** ์์ฑ์ ์ด์ฉํด ์ฒซ ๋ฒ์งธ ํ๋ฉด์ ์ง์ ํ๋ ๋ฐฉ๋ฒ์ด ์์ต๋๋ค.

```javascript
    return (
        <Stack.Navigator initialRouteName="List">
            <Stack.Screen name="Home" component={Home} />
            <Stack.Screen name="List" component={List} />
            <Stack.Screen name="Item" component={Item} />
        </Stack.Navigator>
    );
```

<br />

### ๐ ํ๋ฉด ์ด๋
- Screen ์ปดํฌ๋ํธ์ component๋ก ์ง์ ๋ ์ปดํฌ๋ํธ๋ ํ๋ฉด์ผ๋ก ์ด์ฉ๋๊ณ  navigation์ด props๋ก ์ ๋ฌ๋ฉ๋๋ค.
- navigation์๋ ๋ค์ํ ๊ธฐ๋ฅ์ด ์กด์ฌํ๋๋ฐ ๊ทธ์ค navigate ํจ์๋ ์ํ๋ ํ๋ฉด์ผ๋ก ์ด๋ํ๋ ๋ฐ ์ฌ์ฉ๋๋ ํจ์์๋๋ค.

![4](https://user-images.githubusercontent.com/64779472/113983155-93572900-9884-11eb-9573-1072ad1aa087.PNG)

```javascript
    const Home = ({ navigation }) => {
    return(
        <Container>
            <StyledText>Home</StyledText>
            <Button
                title="go to the list screen"
                //navigate ํจ์๋ฅผ ์ด์ฉํด์ ์ํ๋ ํ๋ฉด์ ์ด๋ฆ์ ์ ๋ฌํ๋ฉด ํด๋น ํ๋ฉด์ผ๋ก ์ด๋ ๋ฉ๋๋ค.
                onPress={() => navigation.navigate('List')}
            />
        </Container>
    )
};
```

<br />

- ๋ง์ฝ ์ด๋ํ๋ ํ๋ฉด์ด ์ด์  ํ๋ฉด์ ์์ธ ํ๋ฉด์ด๋ผ๋ฉด, ์์ธ ํ๋ฉด์ ์ด๋ค ๋ด์ฉ์ ๋ ๋๋งํด์ผํ๋์ง ์ ๋ฌ ๋ฐ์์ผ ํฉ๋๋ค. navigate ํจ์๋ฅผ ์ด์ฉํ  ๋ **๋ ๋ฒ์งธ ํ๋ผ๋ฏธํฐ**์ ๊ฐ์ฒด๋ฅผ ์ ๋ฌํด์ ์ด๋ํ๋ ํ๋ฉด์ ํ์ํ ์ ๋ณด๋ฅผ ํจ๊ป ์ ๋ฌํ๋ ๊ธฐ๋ฅ์ด ์์ต๋๋ค.
- ์ ๋ฌ ๋ ๋ด์ฉ์ ์ปดํฌ๋ํธ์ props๋ก ์ ๋ฌ๋๋ route์ params๋ฅผ ํตํด ํ์ธํ  ์ ์์ต๋๋ค.

```javascript
    //๋ฐ์ดํฐ ์ ๋ฌ
    const _onPress = item => {
        navigation.navigate('Item', {id: item._id, name: item.name});
    };

    //๋ฐ์ดํฐ ํ์ธ
    const Item = ({ route }) => {
        return (
            <Container>
                <StyledText>Item</StyledText>
                <StyledText>ID: {route.params.id}</StyledText>
                <StyledText>Item: {route.params.name}</StyledText>
            </Container>
        )
    };
```

### ๐ ํ๋ฉด ๋ฐฐ๊ฒฝ์ ์์ ํ๊ธฐ
- ๋ฆฌ์กํธ ๋ด๋น๊ฒ์ด์์ cardStyle์ ์ด์ฉํ๋ฉด ์คํ ๋ด๋น๊ฒ์ด์์ ํ๋ฉด ๋ฐฐ๊ฒฝ์์ ์์ ํ  ์ ์์ต๋๋ค. 
- ํ๋ฉด์ ๋ฐฐ๊ฒฝ์์ ์ผ๋ฐ์ ์ผ๋ก ๋์ผํ๊ฒ ์ฌ์ฉํ๋ฏ๋ก, ํ๋ฉด๋ง๋ค ์ค์ ํ๊ธฐ๋ณด๋ค Navigator ์ปดํฌ๋ํธ์ screenOptions์ ์ค์ ํด์ ํ๋ฉด ์ ์ฒด์ ์ ์ฉ๋๋๋ก ํ๋ ๊ฒ์ด ํธํฉ๋๋ค.

```javascript
    <Stack.Navigator 
            initialRouteName="Home"
            screenOptions={{ cardStyle: { backgroundColor: '#ffffff' }}}
        >
        (...)
    </Stack.Navigator>
```

<br />

### ๐ ํค๋ ์์ ํ๊ธฐ
- ์คํ ๋ด๋น๊ฒ์ด์์ ํค๋๋ ๋ค๋ก ๊ฐ๊ธฐ ๋ฒํผ์ ์ ๊ณตํ๊ฑฐ๋ ํ์ดํ์ ํตํด ํ์ฌ ํ๋ฉด์ ์๋ ค์ฃผ๋ ์ญํ ์ ํฉ๋๋ค.
- ํค๋ ํ์ดํ์ Screen ์ปดํฌ๋ํธ์ name ์์ฑ์ ๊ธฐ๋ณธ๊ฐ์ ์ฌ์ฉํฉ๋๋ค.

<br />

- Screen ์ปดํฌ๋ํธ์ name ์์ฑ์ ๋ฐ๊พผ๋ค๋ฉด navigate ํจ์์ ์ ๋ฌํ๋ ์ฒซ ๋ฒ์งธ ํ๋ผ๋ฏธํฐ ๊ฐ๋ ๋ณ๊ฒฝ๋์ด์ผ ํฉ๋๋ค.
- name ์์ฑ์ ๋ณ๊ฒฝํ๋ ๊ฒ์ ๊ฐํธํ์ง๋ง, name ์์ฑ์ ์ด์ฉํ๋ ๊ณณ์ ์ฐพ์๋ค๋๋ฉฐ ๋ชจ๋ ์์ ํด์ผ ํ๋ค๋ ๋จ์ ์ด ์์ต๋๋ค. ์ด ๋จ์ ์ ํผํ๋ ๋ฐฉ๋ฒ์ผ๋ก headerTitle ์์ฑ์ ์ด์ฉํ๋ ๊ฒ์๋๋ค.

```javascript
    <Stack.Navigator>
        (...)
        <Stack.Screen 
            name="List" 
            component={List}
            options={{ headerTitle:'List Screen'}}
        />
    </Stack.Navigator>
```

<br />

### ๐ ํ์ดํ ์คํ์ผ ์์ ํ๊ธฐ
- headerStyle: ํค๋์ ๋ฐฐ๊ฒฝ์ ๋ฑ์ ์์ ํ๋ ์์ฑ
- headerTitleStyle: ํค๋์ ํ์ดํ ์ปดํฌ๋ํธ์ ์คํ์ผ์ ์์ ํ๋ ์์ฑ
- headerTitleAlign: ํ์ดํ ์ ๋ ฌ ํ๋ ์์ฑ center์ left๋ง ๊ฐ๋ฅ
- headerTitle: headerTitle ์์ฑ์ ์ปดํฌ๋ํธ๋ฅผ ๋ฐํํ๋ ํจ์๋ฅผ ์ง์ ํ๋ฉด ํ์ดํ ์ปดํฌ๋ํธ๋ฅผ ๋ฐํํ๋ ์ปดํฌ๋ํธ๋ก ๋ณ๊ฒฝํ  ์ ์๋ค. 
- headerTitle์ ํจ์๊ฐ ์ค์ ๋๋ฉด ํด๋น ํจ์์ ํ๋ผ๋ฏธํฐ๋ก style๊ณผ tintColor ๋ฑ์ด ํฌํจ๋ ๊ฐ์ฒด๊ฐ ์ ๋ฌ๋๋ค. 
    1. style์ headerTitleStyle์ ์ค์ ๋ ๊ฐ์ด๋ค.
    2. tintColor๋ headerTintColor์ ์ง์ ๋ ๊ฐ์ด ์ ๋ฌ ๋๋ค.

```javascript
    <Stack.Navigator 
        initialRouteName="Home"
        screenOptions={{ 
            cardStyle: { backgroundColor: '#ffffff' },
            headerStyle: {
                height: 110,
                backgroundColor: '#95a5a6',
                borderBottomWidth: 5,
                borderBottomColor: '#34495e',
            },
            headerTitleStyle: { color: '#ffffff', fontSize: 24},
            headerTitleAlign: 'center',
            headerTitle: ({ style }) => (
                <MaterialCommunityIcons name="react" style={style} />
            )
        }}
    >
        (...)
    </Stack.Navigator>
```

<br />

### ๐ ํ์ดํ ๋ฒํผ ์คํ์ผ ์์ ํ๊ธฐ
- headerBackTitleVisible: iOS, Android ๋ ํ๋ซํผ์ ๋ฒํผ ํ์ดํ ๋ ๋๋ง ์ฌ๋ถ๋ฅผ ๋์ผํ๊ฒ ์ค์ ํ  ์ ์๋ ์์ฑ. true๋ก ํ๋ฉด ๋ค๋ก๊ฐ๊ธฐ ๋ฒํผ + ํ์ดํ์ด ๋ณด์ธ๋ค.
- headerBackTitle: ์ด์  ํ๋ฉด์ ์ด๋ฆ์ด ์๋ ๋ค๋ฅธ ๊ฐ์ ์ด์ฉํ๊ณ  ์ถ์ ๊ฒฝ์ฐ headerBackTitle ์์ฑ์ ์ด์ฉํ๋ค.
- headerTintStyle: ๋ฒํผ์ ํ์ดํ๊ณผ ์ด๋ฏธ์ง์ ์์ ๋์ผํ๊ฒ ๋ณ๊ฒฝํ  ๋ ์ฌ์ฉํ๋ ์์ฑ
- headerBackTitleStyle: ๊ธ์์ ์๋ฟ๋ง ์๋๋ผ ๊ธ์ ํฌ๊ธฐ ๋ฑ ๋ค์ํ ์คํ์ผ์ ์ง์ ํ  ์ ์์ง๋ง ๋ฒํผ์ ํ์ดํ์๋ง ์ ์ฉ๋๋ค. 

![5](https://user-images.githubusercontent.com/64779472/113991099-17adaa00-988d-11eb-8dca-37fa441f236b.PNG)

```javascript
    <Stack.Screen 
        name="List" 
        component={List}
        options={{ 
            headerTitle:'List Screen',
            headerBackTitleVisible: true,
            headerBackTitle: 'Prev',
            headerTitleStyle: { fontSize: 24},
            headerTintColor: '#e74c3c',
        }}
    />
```
<br />

### ๐ ํ์ดํ ๋ฒํผ ์ปดํฌ๋ํธ ๋ณ๊ฒฝ
- iOS, Android์ ๋ค๋ก ๊ฐ๊ธฐ ๋ฒํผ ์์ด์ฝ์ ๋์ผํ ์์ด์ฝ์ด ๋ ๋๋ง๋๋๋ก ๋ณ๊ฒฝํ๋ ค๋ฉด headerBackImage์ ์ปดํฌ๋ํธ๋ฅผ ๋ฐํํ๋ ํจ์๋ฅผ ์ ๋ฌํด์ ๋ ํ๋ซํผ์ด ๋์ผํ ์ด๋ฏธ์ง๋ฅผ ๋ ๋๋งํ๋๋ก ๋ณ๊ฒฝํด์ผ ๋๋ค.
    1. style์ headerTitleStyle์ ์ค์ ๋ ๊ฐ์ด๋ค.
    2. tintColor๋ headerTintColor์ ์ง์ ๋ ๊ฐ์ด ์ ๋ฌ ๋๋ค.

```javascript
    <Stack.Screen 
        name="List" 
        component={List}
        options={{ 
            headerTitle:'List Screen',
            headerBackTitleVisible: true,
            headerBackTitle: 'Prev',
            headerTitleStyle: { fontSize: 24},
            headerTintColor: '#e74c3c',
            headerBackImage: ({ tintColor }) => {
            //๋ ํ๋ซํผ์ ๋ฒํผ ์์น๋ฅผ ๋์ผํ๊ฒ ํ๊ธฐ ์ํด
            //ํ๋ซํผ์ ๋ฐ๋ผ ์คํ์ผ์ ๋ค๋ฅด๊ฒ ์ ์ฉ
                const style = {
                    marginRight: 5,
                    marginLeft: Platform.OS === 'ios' ? 11 : 0,
                };

                return (
                    <MaterialCommunityIcons 
                        name='keyboard-backspace'
                        size={30}
                        color={tintColor}
                        style={style}
                    />
                );
            }
        }}
    />
```

<br />

- useLayoutEffect Hook์ useEffect์ ๊ฑฐ์ ๋์ผํ๋ฉฐ ๊ฑฐ์ ๊ฐ์ ๋ฐฉ์์ผ๋ก ๋์ํฉ๋๋ค. ์ฃผ์ ์ฐจ์ด์ ์ ์ปดํฌ๋ํธ๊ฐ ์๋ฐ์ดํธ๋ ์งํ ํ๋ฉด์ด ๋ ๋๋ง ๋๊ธฐ ์ ์ ์คํ๋ฉ๋๋ค. ์ด ํน์ง ๋๋ฌธ์ ํ๋ฉด์ ๋ ๋๋งํ๊ธฐ ์ ์ ๋ณ๊ฒฝํ  ๋ถ๋ถ์ด ์๊ฑฐ๋ ์์น ๋ฑ์ ์ธก์ ํด์ผ ํ๋ ์ํฉ์์ ๋ง์ด ์ฌ์ฉ๋ฉ๋๋ค.

<br />

- headerLeft์ headerRight์ ์ปดํฌ๋ํธ๋ฅผ ๋ฐํํ๋ ํจ์๋ฅผ ์ง์ ํ๋ฉด ํค๋์ ์ผ์ชฝ, ์ค๋ฅธ์ชฝ์ ์ํ๋ ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋งํ  ์ ์์ต๋๋ค.
- headerLeft ํ๋ผ๋ฏธํฐ์๋ ๋ค์ํ ๊ฐ๋ค์ด ์ ๋ฌ๋๋๋ฐ, ๊ทธ์ค onPress๋ ๋ค๋ก ๊ฐ๊ธฐ ๋ฒํผ ๊ธฐ๋ฅ์ด ์ ๋ฌ๋ฉ๋๋ค.
- headerRight ํ๋ผ๋ฏธํฐ์๋ tintColor๋ง ์ ๋ฌ๋๋ฏ๋ก, onPress์ ์ํ๋ ํ๋์ ์ ์ํด์ค์ผ ํฉ๋๋ค. navigation์์ ์ ๊ณตํ๋ ๋ค์ํ ํจ์ ์ค popToTop ํจ์๋ ํ์ฌ ์์ฌ ์๋ ๋ชจ๋  ํ๋ฉด์ ๋ด๋ณด๋ด๊ณ  ์ฒซ ํ๋ฉด์ผ๋ก ๋์๊ฐ๋ ๊ธฐ๋ฅ์๋๋ค.


```javascript
    import React, { useLayoutEffect } from 'react';

    const Item = ({ navigation, route }) => {

    useLayoutEffect(() => {
        navigation.setOptions({
            headerBackTitleVisible: false,
            headerTintColor: '#ffffff',
            headerLeft: ({ onPress, tintColor }) => {
                return (
                    <MaterialCommunityIcons 
                        name="keyboard-backspace"
                        size={30}
                        style={{ marginLeft: 11 }}
                        color={tintColor}
                        onPress={onPress}
                    />
                )
            },
            headerRight: ({ tintColor }) => {
                return (
                    <MaterialCommunityIcons 
                        name="home-variant"
                        size={30}
                        style={{ marginRight: 11 }}
                        color={tintColor}
                        onPress={() => navigation.popToTop()}
                    />
                )
            },
        });
    }, []);
```
<br />

### ๐ ํค๋ ๊ฐ์ถ๊ธฐ
- headerMods๋ Navigation์ปดํฌ๋ํธ์ ์์ฑ์ผ๋ก ํค๋๋ฅผ ๋ ๋๋งํ๋ ๋ฐฉ๋ฒ์ ์ค์ ํ๋ ์์ฑ์๋๋ค.
    1. float: ํค๋๊ฐ ์๋จ์ ์ ์ง๋๋ฉฐ ํ๋์ ํค๋๋ฅผ ์ฌ์ฉ
    2. screen: ๊ฐ ํ๋ฉด๋ง๋ค ํค๋๋ฅผ ๊ฐ์ง๋ฉฐ ํ๋ฉด ๋ณ๊ฒฝ๊ณผ ํจ๊ป ๋ํ๋๊ฑฐ๋ ์ฌ๋ผ์ง
    3. none: ํค๋๊ฐ ๋ ๋๋ง๋์ง ์์

<br />

- headerShown์ ํ๋ฉด ์ต์์ผ๋ก, Navigator ์ปดํฌ๋ํธ์ screenOptions์ ์ค์ ํ๋ฉด ์ ์ฒด ํ๋ฉด์ ํค๋๊ฐ ๋ณด์ด์ง ์๋๋ก ์ค์ ํ  ์ ์์ต๋๋ค.
- ํค๋๊ฐ ์ฌ๋ผ์ง๋ฉด ๋ธ์น ๋์์ธ ๋ฌธ์ ๋ก ํ๋ฉด์ ์ผ๋ถ๊ฐ ๊ฐ๋ ค์ง๋ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด SafeAreaView๋ฅผ ์ฌ์ฉํด์ผ ํฉ๋๋ค. (iOS)
- Android ๊ฐ์ ๊ฒฝ์ฐ ์ํ๋ฐ์ ๊ฐ๋ ค์ง๋ ๋ฌธ์ ๋ฅผ StatusBar๋ฅผ ํตํด ํด๊ฒฐ ๊ฐ๋ฅ

![6](https://user-images.githubusercontent.com/64779472/113995990-b63c0a00-9891-11eb-984e-dc432361779e.PNG)

```javascript
    //headerShown
    <Stack.Screen 
        name="Home" 
        component={Home}
        options={{ headerShown: false }}
    />

    //SageAreaView
    const Container = styled.SafeAreaView`
        flex: 1;
        justify-content: center;
        align-items: center;
    `;

    //StatusBar
    <StatusBar 
        barStyle="dark-content"
        backgroundColor="#ffffff"
    />
```

<br />

## ๐จ๐ปโ๐ป ํญ ๋ด๋น๊ฒ์ด์
- ํญ ๋ด๋น๊ฒ์ด์์ ๋ณดํต ํ๋ฉด ์๋ ์๋์ ์์นํ๋ฉฐ, ํญ ๋ฒํผ์ ๋๋ฅด๋ฉด ๋ฒํผ๊ณผ ์ฐ๊ฒฐ๋ ํ๋ฉด์ผ๋ก ์ด๋ํ๋ ๋ฐฉ์์ผ๋ก ๋์ํฉ๋๋ค. ex) ์นด์นด์คํก, ์ ํ๋ธ

![7](https://user-images.githubusercontent.com/64779472/114026037-be577200-98b0-11eb-9263-90dbaa15a0b2.PNG)

```javascript
    //install
    yarn add @react-navigation/bottom-tabs
```
<br />

### ๐ ํ๋ฉด๊ตฌ์ฑ
- createBottomTabNavigatorํจ์๋ฅผ ์ด์ฉํด ํญ ๋ด๋น๊ฒ์ด์์ ์์ฑ
- ํญ ๋ด๋น๊ฒ์ด์์๋ ์คํ ๋ด๋น๊ฒ์ด์๊ณผ ๋์ผํ๊ฒ Navigator ์ปดํฌ๋ํธ, Screen ์ปดํฌ๋ํธ๊ฐ ์๋ค. ์ญํ ์ ๋์ผํ๋ค.
- initalRouteName ์์ฑ์ ์ด์ฉํด ํญ ๋ฒํผ์ ์์๋ ๋ณ๊ฒฝํ์ง ์๊ณ  ๋ ๋๋ง ๋๋ ์ฒซ ๋ฒ์งธ ํ๋ฉด์ ๋ณ๊ฒฝํ  ์ ์๋ค.

```javascript
    import {createBottomTabNavigator} from '@react-navigation/bottom-tabs';
    const Tab = createBottomTabNavigator();

    const TabNavigation = () => {
        return (
            <Tab.Navigator initialRouteName="Settings">
                <Tab.Screen name="Mail" component={Mail} />
                <Tab.Screen name="Meet" component={Meet} />
                <Tab.Screen name="Settings" component={Settings} />
            </Tab.Navigator>
        )
    };
```

<br />

### ๐ ๋ฒํผ ์์ด์ฝ ์ค์ 
- ํญ ๋ฒํผ์ ์์ด์ฝ์ ๋ ๋๋งํ๋ ๋ฐฉ๋ฒ์ **tabBarIcon**์ ์ด์ฉํ๋ ๊ฒ์ด๋ค. ์คํ ๋ด๋น๊ฒ์ด์์ฒ๋ผ ์ปดํฌ๋ํธ๋ฅผ ๋ฐํํ๋ ํจ์๋ฅผ ์ง์ ํ๋ฉด ๋ฒํผ์ ์์ด์ฝ์ด ๋ค์ด๊ฐ ์๋ฆฌ์ ํด๋น ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋งํ๋ค.
    1. color
    2. size
    3. focused

```javascript
    import { MaterialCommunityIcons } from '@expo/vector-icons';

    const TabIcon = ({ name, size, color}) => {
        return (
            <MaterialCommunityIcons 
                name={name} 
                size={size} 
                color={color} 
            /> 
        );
    }

    <Tab.Navigator initialRouteName="Settings">
            <Tab.Screen 
                name="Mail" 
                component={Mail}
                options={{
                    tabBarIcon: props => TabIcon({ ...props, name: 'email'})
                }}
            />
            (...)
    </Tab.Navigator>

```
<br />

- ๋ง์ฝ Screen ์ปดํฌ๋ํธ๋ง๋คํญ ๋ฒํผ ์์ด์ฝ์ ์ง์ ํ์ง ์๊ณ  ํ๊ณณ์์ ๋ชจ๋  ๋ฒํผ์ ์์ด์ฝ์ ๊ด๋ฆฌํ๊ณ  ์ถ์ ๊ฒฝ์ฐ Navigator ์ปดํฌ๋ํธ์ screenOptions ์์ฑ์ ์ฌ์ฉํด์ ๊ด๋ฆฌํ  ์ ์๋ค.

```javascript
    <Tab.Navigator 
        initialRouteName="Settings"
        screenOptions={({ route }) ({
            tabBarIcon: props => {
                let name = '';
                if (route.name === 'Mail') name = 'email';
                else if (route.name === 'Meer') name = 'video';
                else name = 'account-settings';
                return TabIcon({ ...props, name });
            }
        })}
    >
        <Tab.Screen name="Mail" component={Mail}/>
    </Tab.Navigator>
```

### ๐ ๋ผ๋ฒจ ์์ ํ๊ธฐ
- ๋ฒํผ ์์ด์ฝ ์๋์ ๋ ๋๋ง๋๋ ๋ผ๋ฒจ(Label)์ Screen ์ปดํฌ๋ํธ์ name ๊ฐ์ ๊ธฐ๋ณธ๊ฐ์ผ๋ก ์ฌ์ฉํฉ๋๋ค. ํญ ๋ฒํผ์ ๋ผ๋ฒจ์ **tabBarLabel**์ ์ด์ฉํด์ ๋ณ๊ฒฝํ  ์ ์์ต๋๋ค.

```javascript
    <Tab.Navigator initialRouteName="Settings">
        <Tab.Screen 
            name="Mail" 
            component={Mail}
            options={{
                tabBarLabel: 'index',
                tabBarIcon: props => TabIcon({ ...props, name: 'email'})
            }}
        />
        (...)
    </Tab.Navigator>
```
<br />

- ๋ผ๋ฒจ์ ๋ฒํผ ์์ด์ฝ์ ์๋๊ฐ ์๋ ์์ด์ฝ ์์ ๋ ๋๋ง๋๋๋ก ๋ณ๊ฒฝํ๊ณ  ์ถ์ผ๋ฉด **tabBarOptions** ์์ฑ์ **labelPosition**์ ๊ฐ์ ๋ณ๊ฒฝํด์ ์กฐ์ ํ  ์ ์์ต๋๋ค.
    1. below-icon: ์์ด์ฝ ์๋์ ๋ผ๋ฒจ์ด ๋ ๋๋ง๋๋ค.
    2. beside-icon: ์์ด์ฝ ์ค๋ฅธ์ชฝ์ ๋ผ๋ฒจ์ด ๋ ๋๋ง๋๋ค.

![8](https://user-images.githubusercontent.com/64779472/114031078-f9a86f80-98b5-11eb-987c-e8b68d9426f3.PNG)

```javascript
    <Tab.Navigator 
        initialRouteName="Settings"
        tabBarOptions={{
            labelPosition: 'beside-icon',
        }}
    >
    (...)
    </Tab.Navigator>
```

<br />

- ๋ผ๋ฒจ์ ๋ ๋๋งํ์ง ์๊ณ  ์์ด์ฝ๋ง ์ฌ์ฉํ๋ ๊ฒฝ์ฐ์๋ **tabBarOptions** ์์ฑ์ **showLabel**์ ์ด์ฉํ๋ฉด ํญ ๋ฐ์์ ๋ผ๋ฒจ์ด ๋ ๋๋ง๋์ง ์๋๋ก ์ค์ ํ  ์ ์์ต๋๋ค.

![9](https://user-images.githubusercontent.com/64779472/114031080-fa410600-98b5-11eb-817e-83502b43291c.PNG)

```javascript
    <Tab.Navigator 
        initialRouteName="Settings"
        tabBarOptions={{
            labelPosition: 'beside-icon',
            showLabel: false,
        }}
    >
    (...)
    </Tab.Navigator>
```

<br />

### ๐ ์คํ์ผ ์์ ํ๊ธฐ
- ํญ ๋ฐ์ ์คํ์ผ์ ์์ ํ๋ ค๋ฉด **tabBarOptions** ์์ฑ์ style์ ๊ฐ์ผ๋ก ์คํ์ผ ๊ฐ์ฒด๋ฅผ ์ค์ ํ์ฌ ๋ณ๊ฒฝํ  ์ ์์ต๋๋ค.

![11](https://user-images.githubusercontent.com/64779472/114032446-450f4d80-98b7-11eb-81a7-2863dd72cb6d.PNG)

```javascript
    <Tab.Navigator 
        initialRouteName="Settings"
        tabBarOptions={{
            labelPosition: 'beside-icon',
            showLabel: false,
            style: {
                backgroundColor: '#54b7f9',
                borderTopColor: '#fff',
                borderTopWidth: 2,
            }
        }}
    >
    </Tab.Navigator>
```

<br />

- ํญ ๋ฒํผ์ ์์ด์ฝ์ ํ์ฑํ ๋ ์ํ์ ์์ **activeTintColor**, ๋นํ์ฑํ๋ ์ํ์ ์์ **inactiveTintColor**์ ์ด์ฉํด ์ค์ ํ  ์ ์์ต๋๋ค.

![10](https://user-images.githubusercontent.com/64779472/114032320-2ad56f80-98b7-11eb-8240-17bca13dceba.PNG)

```javascript
    <Tab.Navigator 
        initialRouteName="Settings"
        tabBarOptions={{
            labelPosition: 'beside-icon',
            showLabel: false,
            style: {
                backgroundColor: '#54b7f9',
                borderTopColor: '#fff',
                borderTopWidth: 2,
            },
            activeTintColor: '#fff',
            inactiveTintColor: '#0B92E9',
        }}
    >
    </Tab.Navigator>
```

<br />

- ๋ฒํผ์ ์์ด์ฝ์ ์ค์ ํ๊ธฐ ์ํด barTabIcon์ ์ค์ ํ ํจ์์๋ ํ๋ผ๋ฏธํฐ๋ก size, color, focused๋ฅผ ๊ฐ์ง ๊ฐ์ฒด๊ฐ ์ ๋ฌ๋๋๋ฐ. ์ด ๊ฐ ์ค focused๋ ๋ฒํผ์ ์ ํ๋๋ ์ํ๋ฅผ ๋ํ๋ด๋ ๊ฐ์ด๋ค. ์ด ๊ฐ์ ์ด์ฉํ๋ฉด ๋ฒํผ์ ํ์ฑํ ์ํ์ ๋ฐ๋ผ ๋ค๋ฅธ ๋ฒํผ์ ๋ ๋๋งํ๊ฑฐ๋ ์คํ์ผ์ ๋ณ๊ฒฝํ  ์ ์๋ค.

![12](https://user-images.githubusercontent.com/64779472/114033530-52790780-98b8-11eb-811c-de711381ca3c.PNG)

```javascript
    <Tab.Navigator 
        //(...)
    >
        <Tab.Screen 
            name="Mail" 
            component={Mail}
            options={{
                tabBarLabel: 'index',
                tabBarIcon: props => TabIcon({ 
                    ...props, 
                    name: props.focused ? 'email' : 'email-outline'
                }),
            }}
        />
        (...)
    </Tab.Navigator>
```
