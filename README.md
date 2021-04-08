# 💻 React-Native-Navigation
### React-Native-Navigation 저장소

<br />

## 🎥

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

### 🏃 스타일 수정하기
- headerStyle: 헤더의 배경색 등을 수정하는 속성
- headerTitleStyle: 헤더의 타이틀 컴포넌트의 스타일을 수정하는 속성
- headerTitleAlign: 타이틀 정렬 하는 속성 center와 left만 가능
- headerTitle: headerTitle 속성에 컴포넌트를 반환하는 함수를 지정하면 타이틀 컴포넌트를 반환하는 컴포넌트로 변경할 수 있다. 
- headerTitle에 함수가 설정되면 해당 함수의 파라미터로 style과 tintColor 등이 포함된 객체가 전달된다. 그중, style은 headerTitleStyle에 설정된 값이고, tintColor는 headerTintColor에 지정된 값이 전달 된다.

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

### 🏃 버튼 수정하기
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