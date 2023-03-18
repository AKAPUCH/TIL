
```swift
// 클로저를 담을 변수
var closureVariable: () -> () = {}

var printHelloClosure = {
  print("클로저 실행")
  print("Hello!")
}

func runNonEscapingClosure(closure: () -> Void) {
    closureVariable = closure // error!!
    print("함수 종료")
}
```
- 클로저는 기본적으로 non-escaping closure로 선언된다.
- 위 코드의 경우 `runNonEscapingClosure` 함수(이름이 있는 클로저) 내부에서 closureVariable에 매개변수 `closure`를 할당하면서 외부 변수 ClosureVariable에 대한 캡쳐가 발생할 것이다.
- 그로 인해 외부 변수에 클로저를 할당하게 되기 때문에 할당 후 `closureVariable`은 @escaping closure라고 타입을 추정하게 된다.
- 따라서 명시적으로 @escaping을 기재하지 않은 함수의 파라미터인 클로저를 외부 변수에 저장하려고 했기 때문에 에러가 발생했다.(단, 파라미터의 자체가 옵셔널로 선언된 클로저라면 에러가 발생하지않음.)
