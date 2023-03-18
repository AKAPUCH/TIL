# TIL
- ios를 학습하며 생기게 된 의문점에 대해서 고민해보고, 알게 된 리빙포인트들을 기록합니다!
- 출처들은 즉시 업데이트되지 않을 수 있고, 부정확한 내용이 있다면 PR 부탁드립니다!

## 의문
- [반환값이 Optional인 클로저는 왜 명시적으로 @escaping을 표기하지 않아도 escaping closure로 취급하는 것일까?]()
- [아래 코드는 `Assigning non-escaping parameter 'closure' to an @escaping closure`이라는 에러가 발생하는데 클로저의 기본 선언 타입은 non-escaping closure이 맞는 걸까?]()
  <details><summary>코드</summary>

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
  </details>
  
