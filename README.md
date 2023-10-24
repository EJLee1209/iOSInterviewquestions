# iOSInterviewquestions

iOS개발자들에게 필요한 자료들을 정리하고 있는 중입니다.

면접때 받은 질문이나 공부한내용들

수정해야할 내용이나 추가해야할 내용은 언제든지 PR날려주세요!

```
답이 적혀있지 않은 이유는 해당 내용을 암기식으로 외우기 보다 찾아보고 공부하면서 습득 하시는게 좋기때문입니다.
해당내용을 찾아보면서 관련된 내용들 까지 같이 공부하시면서 해당 내용을 본인의 것으로 얻으시기 바랍니다.
```

모두의 힘을 모아봅시다 👯‍♀️👯‍♂️
감사합니다:)

# Required

아래 내용들은 최대한 많이 공부해놓는것이 좋습니다 📝

- 면접시기가 wwdc이후 (7월~11월)이라면 해당년도 wwdc세션들을 봐 두시면 매우매우매우 좋습니다.

[Apple All Videos](https://developer.apple.com/videos/all-videos/)

## iOS

- Bounds 와 Frame 의 차이점을 설명하시오.

  > Bounds는 상위뷰와 상관없이 자기 자신만의 좌표 시스템에서 View의 위치와 크기를 나타내고, Frame은 상위뷰를 기준으로 View의 위치와 크기를 나타냅니다.

- 실제 디바이스가 없을 경우 개발 환경에서 할 수 있는 것과 없는 것을 설명하시오.

  > 실제 디바이스가 없을 경우에는 시뮬레이터를 사용해서 앱을 실제 기기에서 테스트하기 전에 빠르게 프로토 타이핑 및 개발을 할 수 있습니다. UI가 화면상에 어떻게 보이는지 확인할 수 있고, 네트워크 통신과 같은 동작들을 디버깅해볼 수 있습니다. 하지만, 시뮬레이터를 사용하면 실제 디바이스 환경이 아닌 Mac 환경에서 실행되는 것이기 때문에 CPU, 메모리 같은 리소스는 컴퓨터의 리소스이기 때문에 정확한 앱의 성능이나 메모리 사용량, 네트워크 속도를 가늠할 수 없습니다.

- 앱의 콘텐츠나 데이터 자체를 저장/보관하는 특별한 객체를 무엇이라고 하는가?

  > DataBase 라고 생각합니다. iOS에서는 앱의 데이터를 저장하기 위해 UserDefaults, CoreData, SQLite, Realm 등을 사용할 수 있습니다. 저는 이 중에서 UserDefaults와 CoreData를 사용해봤습니다. UserDefaults는 데이터를 Key - Value 쌍으로 저장하는데, 사용자 기본 설정과 같은 단일 데이터 저장에 적합합니다.
  > CoreData는 복잡한 데이터 모델 및 관계를 쉽게 작성할 수 있도록 도와주고, 영구적인 데이터 저장을 제공합니다.

- App thinning에 대해서 설명하시오.
  > 디바이스에 앱이 설치될 때, 앱스토어와 운영체제가 디바이스에 맞게 설치되도록 하는 설치 최적화 기술을 의미합니다. App Thining을 사용하면 최소한의 디스크 사용과 빠른 다운로드가 가능합니다.

###

- 앱이 시작할 때 main.c 에 있는 UIApplicationMain 함수에 의해서 생성되는 객체는 무엇인가?

  > UIApplication 인스턴스(객체)가 생성됩니다. UIApplication은 iOS에서 실행되는 앱들의 관리와 협력의 중심점 역할을 합니다. 해당 객체가 생성되고 나서야 개발자가 작성한 코드대로 이벤트 처리 등의 동작을 제어할 수 있습니다.

- @Main에 대해서 설명하시오.

  > 앱의 Entry Point(진입 지점)를 지정하기 위한 Swift의 기능입니다.

- 앱이 foreground에 있을 때와 background에 있을 때 어떤 제약사항이 있나요?
  > 앱이 Foreground에 있을 때, 메모리 및 기타 시스템 리소스에 높은 우선순위를 가지며, 시스템은 충분한 리소스 확보를 위해 필요에 따라 Background 상태의 앱을 종료합니다. Background에 있을 때, 가능한 적은 메모리 공간을 사용해야합니다. 따라서 사용자 이벤트를 받기 어렵고, 메모리가 부족한 상황이라면, 운영체제에 의해서 Background 상태의 앱이 종료될 수 있습니다.
- 앱이 In-Active 상태가 되는 시나리오를 설명하시오.

  > 앱이 실행 중일 때, 멀티 태스킹 윈도우로 진입하거나 전화, 알림 등에 의해 앱이 일시 중단되는 경우 In-Active 상태로 진입합니다.

- scene delegate에 대해 설명하시오.

  > SceneDelegate는 애플리케이션이 화면에 표시되는 방식과 생명주기를 담당합니다. iOS12 까지는 대부분 하나의 앱에 하나의 window였지만, iOS13부터 window의 개념이 scene으로 대체되고 하나의 앱에서 여러 개의 Scene을 가질 수 있게되었습니다. 그로 인해 원래 AppDelegate의 역할이었던 UILifeCycle에 대한 부분을 SceneDelegate가 하게 되었고, AppDelegate에는 Scene Session이 생성되거나 삭제되는 것을 관리하는 Session LifeCycle에 대한 역할이 추가되었습니다.

- UIApplication 객체의 컨트롤러 역할은 어디에 구현해야 하는가?

  > ?.?

- App의 Not running, Inactive, Active, Background, Suspended에 대해 설명하시오.
  > Not running은 앱이 실행되지 않았거나, 완전히 종료된 상태를 말합니다. In-Active는 앱이 실행 중이긴 하지만, 멀티 태스킹 윈도우로 진입하거나 전화, 알림 등에 의해 앱이 일시 중단된 상태이고, 사용자와 상호작용 할 수 없는 상태를 말합니다. Active는 앱이 실행 중이고, 사용자 이벤트를 처리할 수 있는 상태를 말합니다. Background는 홈 화면으로 나가거나, 다른 앱으로 전환되어 앱이 실질적으로 동작하지 않는 상태입니다. Suspended는 앱을 다시 실행했을 때, 최근 작업을 빠르게 로드하기 위해 메모리에 관련 데이터만 저장되어 있는 상태입니다. 앱이 백그라운드 상태에 진입했을 때, 다른 작업을 하지 않으면 Suspended 상태로 진입합니다. Suspended 상태의 앱은 메모리가 부족해지면, 가장 먼저 메모리에서 해제됩니다.

###

- iOS 앱을 만들고, User Interface를 구성하는 데 필수적인 프레임워크 이름은 무엇인가?
  > UIKit 또는 SwiftUI 입니다.

- Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.
  > FoundationKit은 Cocoa Touch Framework에 포함되어 있는 프레임워크 중 하나로 기본 데이터 타입과 컬렉션 타입 및 운영체제 서비스를 사용해 앱의 기본적인 기능을 관리하는 프레임워크 입니다. Iterator, jsonEncoder, jsonDecoder와 같은 데이터 관련 클래스가 정의되어있습니다.

- Delegate란 무엇인지 설명하고, retain 되는지 안되는지 그 이유를 함께 설명하시오.
  > Delegate는 iOS 프레임워크에서 자주 사용하는 디자인 패턴으로, 서로 다른 인스턴스 간에 자신의 일을 다른 인스턴스에게 위임할 때 사용합니다. 서로 다른 인스턴스가 서로를 참조하기 때문에 강한 참조를 하는 경우 Retain Cycle이 발생해 memory leak이 발생할 수 있습니다. Swift에서는 이러한 문제를 해결하기 위해 약한 참조를 사용할 수 있습니다.

- NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.
  > 특정 객체가 NotificationCenter에 이벤트를 발송하고, 해당 이벤트를 구독하고 있는 Observer들은 이벤트를 전달 받아 특정한 로직을 처리할 수 있습니다. 활용 방안으로 키보드가 올라오거나 내려갈 때, View를 재배치하기 위해서 키보드의 상태를 구독하는 Observer를 등록할 때, NotificationCenter를 활용할 수 있습니다.

- UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?
  > Main Thread 입니다. 메인 스레드가 아닌 다른 스레드에서 UI를 조작하면, UI요소들이 충돌하거나 Side Effect가 발생할 수 있습니다. 따라서 UI의 안정성과 일관성을 유지하기 위해 Main Thread에서만 UI에 접근해야합니다.

- App Bundle의 구조와 역할에 대해 설명하시오.
  > 

- 모든 View Controller 객체의 상위 클래스는 무엇이고 그 역할은 무엇인가?
- 자신만의 Custom View를 만들려면 어떻게 해야하는지 설명하시오.
- View 객체에 대해 설명하시오.
- UIView 에서 Layer 객체는 무엇이고 어떤 역할을 담당하는지 설명하시오.
- iOS에서 뷰(View)와 레이어(Layer)의 개념과 차이점에 대해 설명해보세요.
- UIWindow 객체의 역할은 무엇인가?
- UINavigationController 의 역할이 무엇인지 설명하시오.
- TableView를 동작 방식과 화면에 Cell을 출력하기 위해 최소한 구현해야 하는 DataSource 메서드를 설명하시오.
- 하나의 View Controller 코드에서 여러 TableView Controller 역할을 해야 할 경우 어떻게 구분해서 구현해야 하는지 설명하시오.
- setNeedsLayout와 setNeedsDisplay의 차이에 대해 설명하시오.
- stackView의 장점과 단점에 대해서 설명하시오.

###

- NSCache와 딕셔너리로 캐시를 구성했을때의 차이를 설명하시오.
- URLSession에 대해서 설명하시오.
- prepareForReuse에 대해서 설명하시오.
- 다크모드를 지원하는 방법에 대해 설명하시오.
- ViewController의 생명주기를 설명하시오.
- TableView와 CollectionView의 차이점을 설명하시오.
- Dynamic Library와 Static Library의 차이점에 대해 설명해보세요.

## Autolayout

- 오토레이아웃을 코드로 작성하는 방법은 무엇인가? (3가지)
- hugging, resistance에 대해서 설명하시오.
- Intrinsic Size에 대해서 설명하시오.
- 스토리보드를 이용했을때의 장단점을 설명하시오.
- Safearea에 대해서 설명하시오.
- Left Constraint 와 Leading Constraint 의 차이점을 설명하시오.
- Auto Layout과 Frame-based Layout의 차이점은 무엇인가요?
- 성능 향상을 위해 어떤 디버깅 도구를 사용할 수 있나요? 각각의 디버깅 도구는 어떤 상황에서 사용하는 것이 좋나요?

## Swift

- struct와 class와 enum의 차이를 설명하시오.
- class의 성능을 향상 시킬수 있는 방법들을 나열해보시오.
- Copy On Write는 어떤 방식으로 동작하는지 설명하시오.
- Convenience init에 대해 설명하시오.
- AnyObject에 대해 설명하시오.
- Optional 이란 무엇인지 설명하시오.
- Struct 가 무엇이고 어떻게 사용하는지 설명하시오.
- Subscripts에 대해 설명하시오.
- String은 왜 subscript로 접근이 안되는지 설명하시오.
- instance 메서드와 class 메서드의 차이점을 설명하시오.
- class 메서드와 static 메서드의 차이점을 설명하시오.
- Delegate 패턴을 활용하는 경우를 예를 들어 설명하시오.
- Singleton 패턴을 활용하는 경우를 예를 들어 설명하시오.
- KVO 동작 방식에 대해 설명하시오.
- Delegates와 Notification 방식의 차이점에 대해 설명하시오.
- 멀티 쓰레드로 동작하는 앱을 작성하고 싶을 때 고려할 수 있는 방식들을 설명하시오.
- MVC 구조에 대해 블록 그림을 그리고, 각 역할과 흐름을 설명하시오.
- 프로토콜이란 무엇인지 설명하시오.
- Protocol Oriented Programming과 Object Oriented Programming의 차이점을 설명하시오.
- Hashable이 무엇이고, Equatable을 왜 상속해야 하는지 설명하시오.
- mutating 키워드에 대해 설명하시오.
- 탈출 클로저에 대하여 설명하시오.
- Extension에 대해 설명하시오.
- Extension 내부에서 함수를 override할 수 있는지 설명하시오.
- 접근 제어자의 종류엔 어떤게 있는지 설명하시오.
- defer란 무엇인지 설명하시오.
- defer가 호출되는 순서는 어떻게 되고, defer가 호출되지 않는 경우를 설명하시오.
- property wrapper에 대해서 설명하시오.
- Generic에 대해 설명하시오.
- some 키워드에 대해 설명하시오.
- Result타입에 대해 설명하시오.
- Codable에 대하여 설명하시오.
- Closure에 대하여 설명하시오.
- Closure와 함수와의 관계에 대해 설명하시오.
- Optional Chaining과 nil-coalescing operator(??)의 차이점과 사용 시 주의사항은 무엇인가요?
- Swift에서 Async/Await 기능이 도입되기 전에, 비동기(Asynchronous) 작업을 처리하는 방법에는 어떤 것들이 있나요?
- 타입 변환(Type Casting)과 다형성(Polymorphism)에 대해 설명해보세요.
- Swift에서 타입 안전성(type safety)은 어떤 방식으로 보장되나요?

## ARC

- ARC란 무엇인지 설명하시오.
- Retain Count 방식에 대해 설명하시오.
- Strong 과 Weak 참조 방식에 대해 설명하시오.
- 순환 참조에 대하여 설명하시오.
- 강한 순환 참조 (Strong Reference Cycle) 는 어떤 경우에 발생하는지 설명하시오.

## Functional Programming

- 순수함수란 무엇인지 설명하시오.
- 함수형 프로그래밍이 무엇인지 설명하시오.
- 고차 함수가 무엇인지 설명하시오.
- Swift Standard Library의 map, filter, reduce, compactMap, flatMap에 대하여 설명하시오.
- Either type이란?

## Architecture

- MVVM, MVI, Ribs, VIP 등 자신이 알고있는 아키텍쳐를 설명하시오.
- 의존성 주입에 대하여 설명하시오.

## SwiftUI

- @State가 어떻게 동작하는지 설명하시오.

## Combine

- PassthroughSubject에 대해서 설명하시오
- @Published에 대해서 설명하시오
- AnyCancellable에 대해서 설명하시오
- sink에 대해서 설명하시오
- throttle과 debounce의 차이점을 설명하시오.
- Data를 Binding 하는 방법에 대해서 설명하시오.

## Concurrency

### GCD, NSOperation

- NSOperationQueue 와 GCD Queue 의 차이점을 설명하시오.
- GCD API 동작 방식과 필요성에 대해 설명하시오.
- Global DispatchQueue 의 Qos 에는 어떤 종류가 있는지, 각각 어떤 의미인지 설명하시오.

### Swift Concurrency

- @MainActor는 언제 이용하는가?
- task동작 방식과 gcd, nsoperation과의 차이점을 설명하시오.

# Optional

아래부터는 추가로 공부를 하면 좋을 내용들입니다.

Objective-c나 rx는 회사, 팀마다 사용하는곳이 차이가있고 신입이나 주니어기준으로 필수라고 여겨지지않기에 옵셔널에 추가하였습니다.

## Rx

- Reactive Programming이 무엇인지 설명하시오.
- RxSwift를 왜 사용하는지 설명하시오.
- RxSwift의 단점을 설명하시오.
- RxSwift에서 Hot Observable과 Cold Observable의 차이를 설명하시오.
- Subject의 종류와 차이점에 대해 설명하시오.
- Subject와 Driver의 차이를 설명하시오.
- Single, Completable, Maybe의 차이점에 대해 설명하고, 언제 적용하면 좋을지 설명하시오.

## MRC

- ARC 대신 Manual Reference Count 방식으로 구현할 때 꼭 사용해야 하는 메서드들을 쓰고 역할을 설명하시오.
- retain 과 assign 의 차이점을 설명하시오.
- 특정 객체를 autorelease 하기 위해 필요한 사항과 과정을 설명하시오.
- Autorelease Pool을 사용해야 하는 상황을 두 가지 이상 예로 들어 설명하시오.
- 다음 코드를 실행하면 어떤 일이 발생할까 추측해서 설명하시오.
  Ball \*ball = [[[[Ball alloc] init] autorelease] autorelease];

## Advanced

- method swizzling이 무엇이고, 어떨 때 사용하는지 설명하시오.
- NSCoder 클래스는 어떤 상황에서 어떻게 써야 하는지 설명하시오.
- Responder Chain 구조에 대해 설명하고, First Responder 역할에 대해 설명하시오.
- NSObject부터 UIButton 까지 상속 과정의 계층과 역할을 설명하시오.
- shallow copy와 deep copy의 차이점을 설명하시오.
- Push Notification 방식에 대해 설명하시오.
- Foundation 과 Core Foundation 프레임워크의 차이점을 설명하시오.
- NSURLConnection 에서 사용하는 Delegate 메서드들에 대해 설명하시오.
- Synchronous 방식과 Asynchronous 방식으로 URL Connection을 처리할 경우의 장단점을 비교하시오.
- Plist 파일 구조와 Plist 파일에 저장된 데이터를 다루기 적합한 클래스를 설명하시오.
- Core Data와 Sqlite 같은 데이터 베이스의 차이점을 설명하시오.
- JSON 데이터를 처리하는 방식과 파서, 객체 변환 방식에 대해 설명하시오.
- 웹 서버와 HTTP 연결을 사용해서 데이터를 주거나 받으려면 사용해야 하는 클래스와 동작을 설명하시오.
- Protocol에서는 왜 var만 되는지 설명하시요.
- DispatchQueue.main.sync를 사용하는 상황을 설명하시오.
- Run Loops에 대해 설명하시오.

## Objective-C

- Swift의 클로저와 Objective-C의 블록은 어떤 차이가 있는가?
- Mutable 객체과 Immutable 객체는 어떤것이 있는지 예를 들고, 차이점을 설명하시오.
- dynamic과 property 의미와 차이를 설명하시오.
- @property로 선언한 NSString\* title 의 getter/setter 메서드를 구현해보시오.
- @property에서 atomic과 nonatomic 차이점을 설명하고, 어떤것이 안전한지, 어느것이 기본인지 설명하시오.
- @property로 선언한다는 것의 의미를 설명하고, .h에 넣을 경우와 .m에 넣을 경우 차이점을 설명하시오.
- -performSelector:withObject:afterDelay: 메시지를 보내면 인자값의 객체는 retain되는가? 그 이유를 함께 설명하시오.
- Objective-C 에서 캡슐화된 데이터를 접근하기 위한 방법들을 설명하시오.
- Fast Enumeration 이란 무엇인지 설명하시오.
- unnamed category 방식에 대해 설명하시오.
- Category 확장과 Subclass 확장의 차이점을 설명하시오.
- Category 방식에 대해 설명하시오.
- Objective-C 에서 Protocol 이란 무엇인지 설명하시오.
- Objective-C++ 방식이 무엇인지 설명하고, 어떤 경우 사용해야 하는지 설명하시오.
