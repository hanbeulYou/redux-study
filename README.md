# redux-study
<br>

# 생활코딩-redux

## HTML, CSS와 Redux 만으로 간단한 어플리케이션 만들기

<br>

### Redux 개념 학습

![redux-structure](./redux_structure.png)

<br>

1. store에는 정보가 저장됨

  * state : 실제 정보가 저장됨(절대로 직접 접속 X)
  * reducer : 현재 상태를 변화시킬 함수
  * dispatch : 전송된 action에 반응 -> reducer를 호출해 state를 변경 / subscribe를 호출해 render 호출
  * subscribe : state가 변동될 때마다 render 함수 호출
  * getState : store의 값을 가져올 수 있게 함

<br>

2. store 밖의 구성 요소
  * render : UI를 만들어주는 코드
  * action : 객체를 전송

<br>

### Dispatch의 동작 구조

1. dispatch가 reducer를 호출할 때 2개의 값을 전달
  
  * 현재의 state 값
  * action data
  * reducer은 state값을 입력 받고 action을 참조하여 새로운 state 값을 return (state 가공)

<br>

2. state값이 변경되면 dispatch render 호출
  * subscribe에 등록되어 있는 모든 구독자들을 호출
  * 각 구독자마다 render 시행

<br>

### Redux가 좋은 이유

1. 상호작용이 많은 컴포넌트의 수가 늘어날 수록 Redux 없이 코드를 관리하기 어려움
2. 변경된 상태를 기록하여 과거의 상태를 참조할 수 있음