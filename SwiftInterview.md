

### 질문들 

1. Cocoapods? Carthage? 차이
    - https://baked-corn.tistory.com/109

2. life cycle에 대해서 설명해주세요.
    - https://medium.com/ios-development-with-swift/%EC%95%B1-%EC%83%9D%EB%AA%85%EC%A3%BC%EA%B8%B0-app-lifecycle-vs-%EB%B7%B0-%EC%83%9D%EB%AA%85%EC%A3%BC%EA%B8%B0-view-lifecycle-in-ios-336ae00d1855
    - background, foreground,
    - UIApplication - > @UIApplicationMain -> AppDelegate -> Main Event Loop ( touch, text input )

        - UIApplication - 싱글톤, 이벤트를 감지하여 AppDelegate에 전달
    - ViewDidLoad
    - viewWillAppear, viewDidAppear
    - viewWillDisappear, viewDidDisappear

3. swift에서 Access Level 차이
    - Open, public, Internal, fileprivate, private


4. Tuple이란?
    - Tuple = Dictionary(can be created on the fly) + Struct (hold very specific types of data)

### Questions

1. What is the difference between Cocoapods and Carthage?
2. Tell me about Lifecycle ViewController and app
3. What are the different Access Levels in swift?

### 유용한 사이트

https://medium.com/@anios4991/ios-interview-questions-swift-part-1-a3e8402f85bd

