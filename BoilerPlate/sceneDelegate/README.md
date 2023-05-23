# SceneDelegate

<details><summary>코드로 최초 뷰컨트롤러 지정하기</summary>
  
- 현재 어플리케이션의 windowScene 객체를 가져와 window에 할당
- rootViewController를 설정
- 현재 window를 keyWindow로 설정 및 화면에 표시
- 관련 문법은 [window의 역할은 무엇인가?](https://github.com/Swift-Master/SwiftMaster17_Team13_Study/tree/main/iOS/14%EC%A3%BC%EC%B0%A8/UIWindow%20%EA%B0%9D%EC%B2%B4%EC%9D%98%20%EC%97%AD%ED%95%A0%EC%9D%80%20%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%3F/PAKA) 참고
 
### 코드
  ```swift
  func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {
    guard let windowScene = (scene as? UIWindowScene) else { return }
    window = UIWindow(windowScene: windowScene)
    window?.rootViewController = UINavigationController(rootViewController: ViewController())
    window?.makeKeyAndVisible()              
    }
  ```
  
  </details>
