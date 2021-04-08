# 💻 React-Native-Navigation
### React-Native-Navigation 저장소

<br />

## 🎥 App View
### 📺 Stack Navigation
<p align='center'>
    <img src='https://user-images.githubusercontent.com/64779472/114034632-50637880-98b9-11eb-98d8-a2111e389a09.PNG' width="400" height="730">
</p>

<br />

### 📺 Tab Navigation
<p align='center'>
    <img src='https://user-images.githubusercontent.com/64779472/114034024-c87d6e80-98b8-11eb-907a-86fe74ce34c2.PNG' width="400" height="730">
</p>

<br />

## 👨🏻‍💻 React Navigation
🔖 https://reactnavigation.org/

- 리액트 네이티브에서는 내비게이션 기능을 지원하지 않으므로 외부 라이브러리를 이용해야 한다.
- 리액트 내비게이션 라이브러리를 리액트 네이티브 애플리케이션의 내비게이션을 쉽고 간단하게 관리할 수 있도록 도와준다.
- 내비게이션 종류로는 스택(stack), 탭(tab), 드로어(drawer) 세 종류가 있다.

```javascript
    //install
    yarn add @react-navigation/native

    //내비게이션에서 필요한 종속성 설치
    expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view
```
<br />

### 🏃 내비게이션 구조

- 리액트 내비게이션에는 NavigationContainer 컴포넌트, Navigation, Screen 컴포넌트가 있다.
- **Screen 컴포넌트**는 화면으로 사용되는 컴포넌트이다. name과 component 속성을 지정해야 한다. name은 화면 이름으로 사용되며, component에는 화면으로 사용 될 컴포넌트를 전달한다.
- **Navigation 컴포넌트**는 화면을 관리하는 중간 관리자 역할로 내비게이션을 구성하며, 여러 개의 Screen 컴포넌트를 자식 컴포넌트로 갖고 있다.
- **NavigationContainer 컴포넌트**는 내비게이션의 계층 구조와 상태를 관리하는 컨테이너 역할을 하며, 모든 내비게이션 구성 요소를 감싼 최상위 컴포넌트여야 한다.

![1](https://user-images.githubusercontent.com/64779472/113977703-f1ccd900-987d-11eb-9cb0-5b3acca8302d.PNG)

<br />

### 🏃 설정 우선 순위

- 리액트 내비게이션에서 설정할 수 있는 다양한 속성을 수정하는 방법
    1. Navigation 컴포넌트의 속성으로 수정하는 방법
    2. Screen 컴포넌트의 속성으로 수정하는 방법
    3. 화면으로 사용되는 컴포넌트의 props로 전달되는 navigation을 이용해서 수정하는 방법
- 위에 방법 중 1번은 자식 컴포넌트로 존재하는 모든 컴포넌트에 적용되는 특징이 있다. 2, 3번은 해당 화면에만 적용된다. 그렇기에 공통적으로 적용하고 싶은 속성은 1번을 선택하고, 개별 화면에만 적용시키고 싶을 경우에는 2, 3번은 사용한다.
- 작은 범위의 설정일수록 우선순위가 높아진다. (그림 참고)

![2](https://user-images.githubusercontent.com/64779472/113978202-9cdd9280-987e-11eb-89ca-b02a1b1dcb7c.PNG)

<br />


## 👨🏻‍💻 스택 내비게이션
### 🏃 화면 구성
- 스택 내비게이션은 가장 기본적인 내비게이션으로, 현재 화면 위에 다른 화면을 쌓으면서 화면을 이동하는 것이 특징이다.
- 스택 내비게이션은 화면 위에 새로운 화면을 쌓으면서(push) 이동하기 때문에 이전 화면을 계속 유지해야한다. 이런 구조 때문에 가장 위에 있는 화면을 들어내면(pop) 이전 화면으로 돌아갈 수 있다는 특징이 있다.

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

    // 스택 내비게이션 생성
    const Stack = createStackNavigator();

    // 화면을 구성하는 Screen, Screen을 관리하는 Navigator 컴포넌트
    return (
        <Stack.Navigator>
            <Stack.Screen name="Home" component={Home} />
            <Stack.Screen name="List" component={List} />
            <Stack.Screen name="Item" component={Item} />
        </Stack.Navigator>
    );
```

<br />

- 스택 내비게이션에서 첫 번째 화면으로 나오는 화면은 Navigator 컴포넌트의 첫 번째 자식 Screen 컴포넌트입니다. 만약 순서를 변경한다면 첫 화면으로 나타나는 화면이 달라집니다.
- 컴포넌트 순서를 변경하는 방법 외에도 **initalRouteName** 속성을 이용해 첫 번째 화면을 지정하는 방법이 있습니다.

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

### 🏃 화면 이동
- Screen 컴포넌트의 component로 지정된 컴포넌트는 화면으로 이용되고 navigation이 props로 전달됩니다.
- navigation에는 다양한 기능이 존재하는데 그중 navigate 함수는 원하는 화면으로 이동하는 데 사용되는 함수입니다.

![4](https://user-images.githubusercontent.com/64779472/113983155-93572900-9884-11eb-9573-1072ad1aa087.PNG)

```javascript
    const Home = ({ navigation }) => {
    return(
        <Container>
            <StyledText>Home</StyledText>
            <Button
                title="go to the list screen"
                //navigate 함수를 이용해서 원하는 화면의 이름을 전달하면 해당 화면으로 이동 됩니다.
                onPress={() => navigation.navigate('List')}
            />
        </Container>
    )
};
```

<br />

- 만약 이동하는 화면이 이전 화면의 상세 화면이라면, 상세 화면은 어떤 내용을 렌더링해야하는지 전달 받아야 합니다. navigate 함수를 이용할 때 **두 번째 파라미터**에 객체를 전달해서 이동하는 화면에 필요한 정보를 함께 전달하는 기능이 있습니다.
- 전달 된 내용은 컴포넌트의 props로 전달되는 route의 params를 통해 확인할 수 있습니다.

```javascript
    //데이터 전달
    const _onPress = item => {
        navigation.navigate('Item', {id: item._id, name: item.name});
    };

    //데이터 확인
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

### 🏃 화면 배경색 수정하기
- 리액트 내비게이션의 cardStyle을 이용하면 스택 내비게이션의 화면 배경색을 수정할 수 있습니다. 
- 화면의 배경색은 일반적으로 동일하게 사용하므로, 화면마다 설정하기보다 Navigator 컴포넌트의 screenOptions에 설정해서 화면 전체에 적용되도록 하는 것이 편합니다.

```javascript
    <Stack.Navigator 
            initialRouteName="Home"
            screenOptions={{ cardStyle: { backgroundColor: '#ffffff' }}}
        >
        (...)
    </Stack.Navigator>
```

<br />

### 🏃 헤더 수정하기
- 스택 내비게이션의 헤더는 뒤로 가기 버튼을 제공하거나 타이틀을 통해 현재 화면을 알려주는 역할을 합니다.
- 헤더 타이틀은 Screen 컴포넌트의 name 속성을 기본값을 사용합니다.

<br />

- Screen 컴포넌트의 name 속성을 바꾼다면 navigate 함수에 전달하는 첫 번째 파라미터 값도 변경되어야 합니다.
- name 속성을 변경하는 것은 간편하지만, name 속성을 이용하는 곳을 찾아다니며 모두 수정해야 한다는 단점이 있습니다. 이 단점을 피하는 방법으로 headerTitle 속성을 이용하는 것입니다.

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

### 🏃 타이틀 스타일 수정하기
- headerStyle: 헤더의 배경색 등을 수정하는 속성
- headerTitleStyle: 헤더의 타이틀 컴포넌트의 스타일을 수정하는 속성
- headerTitleAlign: 타이틀 정렬 하는 속성 center와 left만 가능
- headerTitle: headerTitle 속성에 컴포넌트를 반환하는 함수를 지정하면 타이틀 컴포넌트를 반환하는 컴포넌트로 변경할 수 있다. 
- headerTitle에 함수가 설정되면 해당 함수의 파라미터로 style과 tintColor 등이 포함된 객체가 전달된다. 
    1. style은 headerTitleStyle에 설정된 값이다.
    2. tintColor는 headerTintColor에 지정된 값이 전달 된다.

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

### 🏃 타이틀 버튼 스타일 수정하기
- headerBackTitleVisible: iOS, Android 두 플랫폼의 버튼 타이틀 렌더링 여부를 동일하게 설정할 수 있는 속성. true로 하면 뒤로가기 버튼 + 타이틀이 보인다.
- headerBackTitle: 이전 화면의 이름이 아닌 다른 값을 이용하고 싶은 경우 headerBackTitle 속성을 이용한다.
- headerTintStyle: 버튼의 타이틀과 이미지의 색을 동일하게 변경할 때 사용하는 속성
- headerBackTitleStyle: 글자의 색뿐만 아니라 글자 크기 등 다양한 스타일을 지정할 수 있지만 버튼의 타이틀에만 적용된다. 

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

### 🏃 타이틀 버튼 컴포넌트 변경
- iOS, Android의 뒤로 가기 버튼 아이콘에 동일한 아이콘이 렌더링되도록 변경하려면 headerBackImage에 컴포넌트를 반환하는 함수를 전달해서 두 플랫폼이 동일한 이미지를 렌더링하도록 변경해야 된다.
    1. style은 headerTitleStyle에 설정된 값이다.
    2. tintColor는 headerTintColor에 지정된 값이 전달 된다.

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
            //두 플랫폼의 버튼 위치를 동일하게 하기 위해
            //플랫폼에 따라 스타일을 다르게 적용
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

- useLayoutEffect Hook은 useEffect와 거의 동일하며 거의 같은 방식으로 동작합니다. 주요 차이점은 컴포넌트가 업데이트된 직후 화면이 렌더링 되기 전에 실행됩니다. 이 특징 때문에 화면을 렌더링하기 전에 변경할 부분이 있거나 수치 등을 측정해야 하는 상황에서 많이 사용됩니다.

<br />

- headerLeft와 headerRight에 컴포넌트를 반환하는 함수를 지정하면 헤더의 왼쪽, 오른쪽에 원하는 컴포넌트를 렌더링할 수 있습니다.
- headerLeft 파라미터에는 다양한 값들이 전달되는데, 그중 onPress는 뒤로 가기 버튼 기능이 전달됩니다.
- headerRight 파라미터에는 tintColor만 전달되므로, onPress에 원하는 행동을 정의해줘야 합니다. navigation에서 제공하는 다양한 함수 중 popToTop 함수는 현재 쌓여 있는 모든 화면을 내보내고 첫 화면으로 돌아가는 기능입니다.


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

### 🏃 헤더 감추기
- headerMods는 Navigation컴포넌트의 속성으로 헤더를 렌더링하는 방법을 설정하는 속성입니다.
    1. float: 헤더가 상단에 유지되며 하나의 헤더를 사용
    2. screen: 각 화면마다 헤더를 가지며 화면 변경과 함께 나타나거나 사라짐
    3. none: 헤더가 렌더링되지 않음

<br />

- headerShown은 화면 옵션으로, Navigator 컴포넌트의 screenOptions에 설정하면 전체 화면의 헤더가 보이지 않도록 설정할 수 있습니다.
- 헤더가 사라지면 노치 디자인 문제로 화면의 일부가 가려지는 문제를 해결하기 위해 SafeAreaView를 사용해야 합니다. (iOS)
- Android 같은 경우 상태바에 가려지는 문제를 StatusBar를 통해 해결 가능

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

## 👨🏻‍💻 탭 내비게이션
- 탭 내비게이션은 보통 화면 위나 아래에 위치하며, 탭 버튼을 누르면 버튼과 연결된 화면으로 이동하는 방식으로 동작합니다. ex) 카카오톡, 유튜브

![7](https://user-images.githubusercontent.com/64779472/114026037-be577200-98b0-11eb-9263-90dbaa15a0b2.PNG)

```javascript
    //install
    yarn add @react-navigation/bottom-tabs
```
<br />

### 🏃 화면구성
- createBottomTabNavigator함수를 이용해 탭 내비게이션을 생성
- 탭 내비게이션에도 스택 내비게이션과 동일하게 Navigator 컴포넌트, Screen 컴포넌트가 있다. 역할은 동일하다.
- initalRouteName 속성을 이용해 탭 버튼의 순서는 변경하지 않고 렌더링 되는 첫 번째 화면을 변경할 수 있다.

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

### 🏃 버튼 아이콘 설정
- 탭 버튼에 아이콘을 렌더링하는 방법은 **tabBarIcon**을 이용하는 것이다. 스택 내비게이션처럼 컴포넌트를 반환하는 함수를 지정하면 버튼의 아이콘이 들어갈 자리에 해당 컴포넌트를 렌더링한다.
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

- 만약 Screen 컴포넌트마다탭 버튼 아이콘을 지정하지 않고 한곳에서 모든 버튼의 아이콘을 관리하고 싶은 경우 Navigator 컴포넌트의 screenOptions 속성을 사용해서 관리할 수 있다.

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

### 🏃 라벨 수정하기
- 버튼 아이콘 아래에 렌더링되는 라벨(Label)은 Screen 컴포넌트의 name 값을 기본값으로 사용합니다. 탭 버튼의 라벨은 **tabBarLabel**을 이용해서 변경할 수 있습니다.

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

- 라벨을 버튼 아이콘의 아래가 아닌 아이콘 옆에 렌더링되도록 변경하고 싶으면 **tabBarOptions** 속성에 **labelPosition**의 값을 변경해서 조정할 수 있습니다.
    1. below-icon: 아이콘 아래에 라벨이 렌더링된다.
    2. beside-icon: 아이콘 오른쪽에 라벨이 렌더링된다.

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

- 라벨을 렌더링하지 않고 아이콘만 사용하는 경우에는 **tabBarOptions** 속성에 **showLabel**을 이용하면 탭 바에서 라벨이 렌더링되지 않도록 설정할 수 있습니다.

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

### 🏃 스타일 수정하기
- 탭 바의 스타일을 수정하려면 **tabBarOptions** 속성에 style의 값으로 스타일 객체를 설정하여 변경할 수 있습니다.

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

- 탭 버튼의 아이콘은 활성화 된 상태의 색은 **activeTintColor**, 비활성화된 상태의 색은 **inactiveTintColor**을 이용해 설정할 수 있습니다.

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

- 버튼의 아이콘을 설정하기 위해 barTabIcon에 설정한 함수에는 파라미터로 size, color, focused를 가진 객체가 전달되는데. 이 값 중 focused는 버튼의 선택도니 상태를 나타내는 값이다. 이 값을 이용하면 버튼의 활성화 상태에 따라 다른 버튼을 렌더링하거나 스타일을 변경할 수 있다.

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
