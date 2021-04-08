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
- 스택 내비게이션은 가장 기본적인 내비게이션으로, 현재 화면 위에 다른 화면을 쌓으면서 화면을 이동하는 것이 특징이다.
- 스택 내비게이션은 화면 위에 새로운 화면을 쌓으면서(push) 이동하기 때문에 이전 화면을 계속 유지해야한다. 이런 구조 때문에 가장 위에 있는 화면을 들어내면(pop) 이전 화면으로 돌아갈 수 있다는 특징이 있다.

![3](https://user-images.githubusercontent.com/64779472/113979463-38233780-9880-11eb-9c9f-6b665bbe6442.PNG)

```javascript
    //install
    yarn add @react-navigation/stack

    //1. 스택 내비게이션 생성
    const Stack = createStackNavigator();

    //2. 화면을 구성하는 Screen, Screen을 관리하는 Navigator 컴포넌트
    return (
        <Stack.Navigator>
            <Stack.Screen name="Home" component={Home} />
            <Stack.Screen name="List" component={List} />
            <Stack.Screen name="Item" component={Item} />
        </Stack.Navigator>
    );
```

- 스택 내비게이션에서 첫 번째 화면으로 나오는 화면은 Navigator 컴포넌트의 첫 번째 자식 Screen 컴포넌트입니다. 만약 순서를 변경한다면 첫 화면으로 나타나는 화면이 달라집니다.
- 컴포넌트 순서를 변경하는 방법 외에도 initalRouteName 속성을 이용해 첫 번째 화면을 지정하는 방법이 있습니다.

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


### 🏃 
```javascript
    
```

<br />
