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

# iOS

## Bounds 와 Frame 의 차이점을 설명하시오.

> Bounds는 상위뷰와 상관없이 `자기 자신만의 좌표 시스템`에서 View의 `위치`와 `크기`를 나타내고, Frame은 `상위뷰`를 기준으로 View의 위치와 크기를 나타냅니다.

## 실제 디바이스가 없을 경우 개발 환경에서 할 수 있는 것과 없는 것을 설명하시오.

> 실제 디바이스가 없을 경우에는 시뮬레이터를 사용해서 앱을 실제 기기에서 테스트하기 전에 빠르게 프로토 타이핑 및 개발을 할 수 있습니다. UI가 화면상에 어떻게 보이는지 확인할 수 있고, 네트워크 통신과 같은 동작들을 디버깅해볼 수 있습니다. 하지만, 시뮬레이터를 사용하면 실제 디바이스 환경이 아닌 Mac 환경에서 실행되는 것이기 때문에 CPU, 메모리 같은 리소스는 컴퓨터의 리소스입니다. 따라서 정확한 앱의 성능이나 메모리 사용량, 네트워크 속도를 가늠할 수 없습니다. 또한, 카메라, 마이크, 센서등을 사용할 수 없습니다.

## 앱의 콘텐츠나 데이터 자체를 저장/보관하는 특별한 객체를 무엇이라고 하는가?

> `DataBase` 라고 생각합니다. iOS에서는 앱의 데이터를 저장하기 위해 `UserDefaults, CoreData, SQLite, Realm` 등을 사용할 수 있습니다. 저는 이 중에서 UserDefaults와 CoreData를 사용해봤습니다. UserDefaults는 데이터를 `Key - Value` 쌍으로 저장하는데, 사용자 기본 설정과 같은 `단일 데이터 저장`에 적합합니다.
> `CoreData`는 복잡한 데이터 모델 및 관계를 쉽게 작성할 수 있도록 도와주고, `영구적인 데이터 저장`을 제공합니다.

## App thinning에 대해서 설명하시오.

> 앱시닝은 앱을 설치할 때, 운영체제와 앱스토어가 앱을 설치하는 `디바이스의 특성에 맞게` 앱 설치를 `최적화`하는 기술입니다. 앱시닝은 `슬라이싱`, `주문형 리소스`, `비트코드` 세가지로 구성됩니다.

## 슬라이싱, 주문형 리소스, 비트코드가 무엇인가요?

> 슬라이싱은 `앱을 구성하는 여러 버전의 실행 가능한 소스 코드와 리소스들 중` 앱을 설치할 `디바이스의 특성에 맞는` 버전들만 골라서 설치하는 것을 의미합니다.
> 주문형 리소스는 앱을 설치할 때, 모든 리소스를 다운로드 받지 않고, 일부는 앱스토어에 저장해두었다가 `나중에 필요할 때, 다운로드`하는 방식입니다.
> 비트코드는 앱을 업로드할 때, `기계어로 구성된 바이너리 파일이 아니라` 그 전 단계인 `비트코드로 업로드`하는 것을 의미합니다.

###

## 앱이 시작할 때 main.c 에 있는 UIApplicationMain 함수에 의해서 생성되는 객체는 무엇인가?

> `UIApplication` 인스턴스(객체)가 생성됩니다. 또한, AppDelegate와 SceneDelegate 객체도 생성합니다. 마지막으로 앱의 루트가 되는 window 객체를 생성하고, 루트 뷰 컨트롤러를 할당합니다.

## UIApplication 객체는 어떤 일을 하나요?

> UIApplication은 `UIApplicationMain`에서 만들어지는 `싱글톤 객체`입니다. UIApplication은 최초에 `런루프`를 만들고 AppDelegate에게 delegate를 위임합니다.

## AppDelegate는 무슨 일을 하나요?

> AppDelegate는 `UIApplicationDelegate` 프로토콜을 채택하여 앱의 생명주기와 관련된 메소드를 처리합니다.

## UIApplicationDelegate는 어떤 종류의 메서드들을 포함하고 있나요?

> 앱의 `생명주기`에 대응되는 메서드들을 가지고 있습니다.

## 앱 생명주기와 관련된 UIApplicationDelegate 메서드들을 자세히 말해보세요.

- `applicationDidBecomeAcive`: Active 상태가 되면, 호출됩니다.
- `applicationWillResignActive`: In-active 상태로 전환되기 직전에 호출됩니다.
- `applicationDidEnterBackgound`: Background 상태로 들어가면 호출됩니다.
- `applicationWillEnterForeground`: Foreground 상태로 전환되기 직전에 호출됩니다.
- `applicationWillTerminate`: 앱이 종료되기 직전에 호출됩니다.

## @main에 대해서 설명하시오.

> 앱의 `Entry Point`(진입 지점)를 지정하기 위한 Swift의 기능입니다.

## 앱이 In-Active 상태가 되는 시나리오를 설명하시오.

> 앱이 실행 중일 때, 멀티 태스킹 윈도우로 진입하거나 전화, 알림 등에 의해 앱이 `일시 중단되는 경우` In-Active 상태로 진입합니다.

## scene delegate에 대해 설명하시오.

> iOS 13부터 `멀티 윈도우`를 지원하기 시작했습니다. 이는 하나의 앱에서 여러개의 Scene을 가질 수 있는 것인데요, 이 때문에 `UI 생명주기`를 앱 전체에 대해 관리하는 것이 아니라 각 Scene마다 관리할 필요성이 생겼습니다. 이를 위해 SceneDelegate는 각 Scene마다 생성되어 원래는 AppDelegate에서 관리하던 UI 생명주기와 관련된 메서드들을 SceneDelegate에서 처리하게 되었습니다.

## App의 Not running, Inactive, Active, Background, Suspended에 대해 설명하시오.

> `Not running`은 실행 중이지 않은 상태, `Inactive`는 실행 중이지만, 이벤트를 받지 못하는 상태, `Active`는 실행 중이면서 이벤트를 받을 수 있는 상태, `Background`는 백그라운드에서 코드를 실행 중인 상태, `Suspended`는 백그라운드에서 코드를 실행하지 않는 상태를 의미합니다.

###

## iOS 앱을 만들고, User Interface를 구성하는 데 필수적인 프레임워크 이름은 무엇인가?

> `UIKit` 또는 `SwiftUI` 입니다.

## Foundation Kit은 무엇이고 포함되어 있는 클래스들은 어떤 것이 있는지 설명하시오.

> FoundationKit은 애플에서 제공하는 `프레임워크`로 다양한 기능을 제공합니다. 예를 들어 날짜와 시간을 다루기 위한 `Date`를 제공하고, URL을 처리하기 위한 `URL` 클래스와 메서드들을 제공합니다. 또한 JSON을 처리하기 위한 `JSONEncoder`, `JSONDecoder` 클래스를 제공합니다.

## Delegate란 무엇인지 설명하고, retain 되는지 안되는지 그 이유를 함께 설명하시오.

> Delegate는 iOS 개발에서 자주 사용하는 `디자인 패턴`으로, 한 객체가 다른 객체에게 특정 작업을 `위임`할 때 사용합니다. 서로 다른 객체가 서로를 참조하기 때문에 `강하게 참조하는 경우 retain됩니다.` 만약 서로를 강하게 참조하는 경우 `Retain Cycle`이 발생하기 때문에 일반적으로는 delegate 프로퍼티를 약한 참조로 선언해 Retain Cycle 문제를 예방합니다.

## NotificationCenter 동작 방식과 활용 방안에 대해 설명하시오.

> 특정 객체가 NotificationCenter에 `이벤트를 발송`하고, 해당 이벤트를 구독하고 있는 `Observer`들은 이벤트를 전달 받아 특정한 작업을 수행할 수 있습니다. 활용 방안으로 키보드가 올라오거나 내려갈 때를 알기위해 NotificationCenter를 활용할 수 있습니다.

## UIKit 클래스들을 다룰 때 꼭 처리해야하는 애플리케이션 쓰레드 이름은 무엇인가?

> `Main Thread` 입니다. UI 작업은 모두 메인 스레드에서 이루어져야 합니다.

## App Bundle의 구조와 역할에 대해 설명하시오.

> App Bundle은 `실행파일과 실행에 필요한 리소스 및 데이터 파일`을 하나로 묶어서 구성되어 있습니다. iOS 앱을 실행할 때, 필요한 파일들을 로드하기 위해 번들을 통해 로드하게 됩니다.

## 모든 View Controller 객체의 상위 클래스는 무엇이고 그 역할은 무엇인가?

> 모든 ViewController의 상위 클래스는 `UIViewController`입니다. UIViewController는 `View 업데이트, 이벤트 처리, 화면 전환` 등의 역할을 수행합니다.

## 자신만의 Custom View를 만들려면 어떻게 해야하는지 설명하시오.

> `UIView를 상속받는 클래스`를 만들고, 코드로만 UI를 구성하거나 Storyboard를 연결해서 커스텀 뷰를 만들 수 있습니다.

## View 객체에 대해 설명하시오.

> View는 화면에 `content를 표시`하고, 오토레이아웃, 제스쳐 등 화면에 관련한 것들을 담당하는 객체입니다.

## UIView 에서 Layer 객체는 무엇이고 어떤 역할을 담당하는지 설명하시오.

> `View가 생성될 때, 그에 대응하는 layer가 생성`됩니다. 이 때, layer의 타입은 `CALayer`입니다. CALayer는 `CoreAnimation 프레임워크`의 핵심 기능을 제공하는 클래스이며, `그래픽 콘텐츠`를 관리하고, `애니메이션`을 처리하는데 사용됩니다. CoreAnaimation 프레임워크를 사용하기 때문에 GPU를 사용해 렌더링을 가속화하고, 부드러운 애니메이션을 적용할 수 있습니다.

## iOS에서 뷰(View)와 레이어(Layer)의 개념과 차이점에 대해 설명해보세요.

> View는 `화면의 콘텐츠를 관리하는 객체`로써 콘텐츠의 위치와 크기를 정의하고, 사용자 이벤트를 처리할 수 있습니다. 반면에 Layer는 렌더링에 사용되는 `뷰의 핵심 애니메이션 객체`로써 View의 모서리, 그림자, 애니메이션과 같은 View의 시각적 요소를 변경하는데 사용됩니다.

## UIWindow 객체의 역할은 무엇인가?

> UIWindow는 앱의 UI를 담는 `컨테이너`이자, `뷰에 이벤트를 전달`하는 객체입니다.

## UINavigationController 의 역할이 무엇인지 설명하시오.

> UINavigationController는 ViewController들을 `네비게이션 스택`을 통해 `계층적으로` 관리하며, 앱 내부의 `화면 전환`과 관련된 작업을 처리합니다.

## TableView의 동작 방식과 화면에 Cell을 출력하기 위해 최소한 구현해야 하는 DataSource 메서드를 설명하시오.

> TableView는 DataSource 프로토콜을 채택하여 셀을 표시하기 위한 데이터를 전달받고, 화면에 표시될 각 셀을 생성하거나, `재사용 큐`로부터 셀을 재활용합니다. 최소한으로 구현해야 하는 DataSource 메서드는 특정 위치에 삽일할 셀을 반환하는 `cellForRowAt`이 있고, 지정된 섹션에 있는 행의 수를 반환하는 `numberOfRowInSection`이 있습니다.

## 하나의 View Controller 코드에서 여러 TableView의 Controller 역할을 해야 할 경우 어떻게 구분해서 구현해야 하는지 설명하시오.

> TableView의 DataSource 또는 Delegate 메소드를 구현할 때, TableView의 `프로퍼티 이름`으로 구분해서 TableView마다 서로 다른 동작을 구현할 수 있습니다.

## setNeedsLayout와 setNeedsDisplay의 차이에 대해 설명하시오.

> setNeedsLayout은 뷰의 위치와 크기를 업데이트하는 `layoutSubviews`를 다음 업데이트 사이클에 호출하도록 예약하는 메서드이고, setNeedsDisplay는 뷰의 내용을 그리는 `draw` 메서드를 다음 업데이트 사이클에 호출하도록 예약하는 메서드입니다.

## stackView의 장점과 단점에 대해서 설명하시오.

> 가로 또는 세로로 뷰를 `선형으로` 배치하는 경우 stackView를 사용하면 보다 더 편리하게 뷰를 배치할 수 있다는 장점이 있습니다. 하지만, 단순 선형 레이아웃이 아닌 복잡한 레이아웃은 stackView가 제한적일 수 있습니다.

###

## URLSession에 대해서 설명하시오.

> URLSession은 앱에서 서버와 `통신`을 통해 데이터를 주고 받을 수 있도록 API를 제공하는 클래스입니다.

## prepareForReuse에 대해서 설명하시오.

> prepareForReuse는 테이블 뷰나 컬렉션 뷰에서 `셀을 재사용할 때 `호출되는 메서드입니다. 이 메서드의 목적은 셀을 재사용하기 전에 셀의 속성을 `초기화`하기 위해서 사용합니다.

## 다크모드를 지원하는 방법에 대해 설명하시오.

> 다크모드를 지원하기 위해서는 라이트 모드와 다크 모드 각각에 대응하는 `Color Asset과 Image Asset`을 등록해서 대응할 수 있습니다.

## ViewController의 생명주기를 설명하시오.

> loadView, viewDidLoad, viewWillAppear, viewDidAppear, viewWillDisappear, viewDidDisappear 가 있습니다.

- `loadView`: View를 메모리에 로드합니다.
- `viewDidLoad`: View가 메모리에 로드된 후 호출됩니다.
- `viewWillAppear`: View가 화면에 나타나기 전에 호출됩니다.
- `viewDidAppear`: View가 화면에 나타난 후 호출됩니다.
- `viewWillDisappear`: View가 사라지기 전에 호출됩니다.
- `viewDidDisappear`: View가 사라진 후 호출됩니다.

## TableView와 CollectionView의 차이점을 설명하시오.

> 테이블 뷰는 `단일 열의 여러 행`으로 Cell이 나열된 형태인 반면에 컬렉션 뷰는 `다양한 행렬의 형태`로 표현할 수 있습니다.
>
> 또한 테이블 뷰는 기본 Cell의 스타일을 제공하지만, 컬렉션 뷰는 제공하지 않습니다.

## UIControl에 대해서 설명해주세요.

> UIControl은 UIView를 상속받는 객체로 `사용자 상호작용`에 대한 기능을 제공합니다. UIControl은 `addTarget`으로 객체에서 어떤 이벤트가 발생했을 때, 처리할 메소드를 지정할 수 있습니다.

## CollectionViewLayout을 커스텀하게 정의할 때, prepare 메서드가 언제 불리고 어떤 역할을 하는지

> prepare 메서드는 컬렉션 뷰가 컨텐츠를 처음 표시하거나 `뷰가 변경되어서 레이아웃이 무효화되면`, 호출됩니다. prepare 메서드가 호출되면, 레이아웃 객체에게 `레이아웃을 업데이트` 하도록 시키게 됩니다. 레이아웃이 업데이트 되기 시작하면 컬렉션 뷰가 이 메서드를 호출해서 정의한 레이아웃 객체가 레이아웃을 잡을 수 있게합니다.

## #selector의 역할이 무엇인지

> `Objective-C 런타임`으로 실행되는 메서드를 지정하기 위해서 사용합니다.

## super.viewDidLoad()를 제거하면 어떤 일이 일어나는지?

> 상위 클래스의 viewDidLoad를 호출하지 않아도 문제는 일어나지 않지만, UIKit의 viewDidLoad가 언제 구현이 바뀔지 모르고, 내부에 중요한 초기화 코드가 들어갈 수 있기 때문에 당장 영향이 없더라도 호출하는 것이 바람직하다고 생각합니다.

## UIResponder에 대해 설명해주세요.

> UIResponder는 `모든 UIView의 상위 객체`이면서 이벤트를 받고 처리하거나 다른 UIResponder 객체에게 전달하는 역할을 합니다. UIKit은 `first Responder`에게 발생한 이벤트를 전달하고, UIResponder는 해당 이벤트를 자신이 처리할 수 있다면 처리하고, 처리할 수 없다면 `next 프로퍼티`에 할당된 다음 Responder에게 전달합니다.

## UIResponder Chain을 설명해주세요.

> UIKit이 `모든 UIResponder를 엮어서 관리하는 체인`입니다. 각 리스폰더는 `next프로퍼티`로 자신의 다음 리스폰더를 참조하고 있습니다.

## 그럼 기본적으로 클래스별로 이벤트가 전달되는 순서가 어떻게 될까요?

> `UIView, UIViewController, UIWindow, UIApplication, UIApplicationDelegate` 순으로 이벤트가 전달됩니다. 만약 어떤 뷰나 뷰 컨트롤러가 상위뷰에 속해져있는 뷰라면 해당 뷰나 뷰 컨트롤러에 이벤트를 전달합니다.

## Responder Chain을 임의로 변경하려면 어떻게 해야할까요?

> 특정한 뷰의 next프로퍼티를 오버라이딩해서 다음 리스폰더에 지정할 수 있고, `becomeFirstResponder` 메서드를 사용해서 특정한 뷰를 firstResponder로 만들 수 있습니다. 이때는 이벤트가 firstResponder에게 전달됩니다.

## 그럼 이벤트는 어떤 형태로 전달되는지? 터치 이벤트는 다른게 있는지?

> 이벤트는 `UIEvent` 객체로 전달됩니다. 터치 이벤트는 `UITouch` 객체로 관리되고, UIEvent 객체를 통해 접근할 수 있습니다. 터치 이벤트 객체는 터치된 시간, 영역, 강도, 위치 등의 정보를 포함하고 있습니다.

## UIControl에서 이벤트가 발생하면 해당 이벤트를 처리하는 과정을 설명해보세요.

> UIControl은 `addTarget` 메서드로 이벤트 핸들러를 정의할 수 있습니다. 이때 `target`과 `action`을 인자로 전달할 수 있습니다. target은 어떤 객체이던지 들어갈 수 있지만, 일반적으로 이벤트를 처리할 뷰 컨트롤러를 지정합니다. 만약 target에 nil이 들어가면, UIControl은 이벤트 핸들러를 구현하고 있는 `리스폰더를 리스폰더 체인을 통해` 찾아냅니다.
>
> action에는 `이벤트를 처리할 메서드`를 지정합니다. 이벤트가 발생하면, UIControl 객체는 지정된 메서드를 호출하고 UIApplication이 호출 메시지를 받아 `리스폰더 체인을 통해 해당 메서드를 찾고 이벤트를 전달`합니다.

## UI 작업을 메인스레드에서 처리해야하는 이유는 무엇인가요?

> UI 업데이트는 즉각적으로 이루어지는 것이 아니라, `런루프의 한 사이클이 끝날 때` 업데이트 됩니다. 만약 여러 스레드에서 UI작업을 처리하게 되면, 각각 다른 `런루프`에서 처리하게 되고, 화면에 뷰가 그려지는 시점이 서로 달라지거나 레이아웃에 대한 계산이 의도했던 것과 다르게 될 수 있습니다. 그렇기 때문에 UI작업은 항상 메인 스레드에서만 처리되어야합니다.

## UIViewController의 상위 클래스들을 모두 말하고 설명해보세요.

> UIViewController는 `UIResponder`를 상속하고, UIResponder는 `NSObject`를 상속합니다.
>
> UIResponder는 이벤트를 받고 `리스폰더 체인`을 구성할 수 있게합니다. NSObject는 `Objective-C 런타임`에 대한 인터페이스나 기능을 사용할 수 있도록 합니다.

## 앱이 처음 시작되면 어떤 일들이 일어나는지 설명해주세요.

- `main`함수가 실행됩니다.
- main함수는 `UIApplicationMain`함수를 호출합니다.
- UIApplicationMain함수는 `UIApplication` 인스턴스를 생성합니다.
- 그리고 `Info.plist`에서 필요한 데이터를 로드합니다.
- UIApplication은 `AppDelegate` 인스턴스를 생성하고, UIApplication을 `위임`합니다.
- UIApplication은 `RunLoop`를 생성합니다.
- 준비가 완료되면, AppDelegate의 `didFinishLaunchingWithOptions` 를호출합니다.
- 세션에 대한 설정이 완료되면, `SceneDelegate의 willConnectToSession`이 호출됩니다.

<img src="https://user-images.githubusercontent.com/46087477/150353961-db9c84a8-2eb3-4d42-b108-690943f718de.png"/>

# Autolayout

## 오토레이아웃을 코드로 작성하는 방법은 무엇인가? (3가지)

> `NSLayoutConstraint`, `NSLayoutAnchor`, `Visual Format`으로 총 3가지 방법이 있습니다.
> NSLayoutConstraint는 `item`, `attribute`, `multiplier`, `constraint`를 지정해서 `두 객체간의 레이아웃 관계`를 정의하는 방법입니다.
> NSLayoutAnchor는 NSLayoutConstraint를 더 간단한 API로 만든 것으로 `Anchor`와 `constraint`를 통해 객체간의 레이아웃 관계를 정의할 수 있습니다.
> 비주얼 포맷은 `아스키 문자열`을 통해 레이아웃을 시각적으로 표현하여 레이아웃을 정의하는 방법입니다.

## hugging, resistance에 대해서 설명하시오.

> hugging은 `최대 크기에 대한 제한`이고, resistance는 `최소 크기에 대한 제한`입니다. 따라서 hugging의 우선순위가 높은 뷰는 `본연의 크기보다 더 커지지 않으려`하고, resistance의 우선순위가 높은 뷰는 `본연의 크기보다 더 작아지지 않으려하는` 성질을 갖습니다.

## Intrinsic Size에 대해서 설명하시오.

> `Intrinsic Content Size`는 UIImageView, UILabel과 같이 `컨텐츠를 포함하는` View의 경우에 컨텐츠에 따라 자동으로 계산되는 View의 `본질적인 크기`를 의미합니다.

## 스토리보드를 이용했을때의 장단점을 설명하시오.

> 스토리보드를 사용하면 뷰를 `시각적으로` 확인할 수 있기 때문에 오토레이아웃이나 뷰의 구성을 바로바로 확인하고 쉽게 수정할 수 있다는 장점이 있습니다. 하지만, 뷰의 `재사용`이 어렵고 화면이 많아지면, `프로젝트를 로드하는 속도가 느려진다`는 점, 그리고 협업시에 `충돌`이 발생할 수 있다는 단점이 있습니다.

## Safearea에 대해서 설명하시오.

> Safearea는 iOS 디바이스 중 `상단 노치 영역`과 `하단 홈 바 영역`을 말합니다. 기본적으로 앱이 이 영역들을 침범하지 못하도록 safearea를 기준으로 오토레이아웃을 설정합니다.

## Left Constraint 와 Leading Constraint 의 차이점을 설명하시오.

> 문자에 대한 제약을 설정할 때, Left는 항상 문자의 시작을 왼쪽에 두지만, Leading은 언어에 따라서 우측에서 좌측으로 읽는 언어는 시작을 오른쪽에, 좌측에서 우측으로 읽는 언어는 시작을 왼쪽에 둡니다.

## Auto Layout과 Frame-based Layout의 차이점은 무엇인가요?

> Auto Layout은 `View사이의 관계를 고려한 제약조건`을 추가하여 View의 위치와 크기가 정해집니다. 반면에 Frame-based Layout은 View마다 `frame`을 직접 설정하여 View의 위치와 크기를 지정하는 방식입니다. 이것은 성능상 이점이 있을 수 있지만, 모든 화면 크기에 대한 대응을 해야하기 때문에 유지/보수에 어려움이 있습니다.

## Swift

## struct가 무엇인가요?

> struct는 `사용자 정의 타입`을 만들기 위해 Swift에서 제공하는 기능입니다. 프로퍼티에 데이터를 저장하여 `인스턴스`를 생성하고 객체로 사용할 수 있습니다. struct는 클래스와 달리 `상속이 불가능`하지만, `프로토콜`을 채택할 수는 있습니다. 또한, `값 타입`이기 때문에 값을 전달할 때 복사하여 전달합니다. 이때, `Copy On Write`를 통해 메모리 사용을 최적화합니다.

## Copy-On-Write(COW)가 무엇인가요?

> Copy On Write는 값 타입의 `값이 실제로 변경되기 전까지 복사를 미뤄서 메모리를 최적화`하는 기법입니다. 예를들어 값 타입인 배열을 두 변수에 할당했을 때, 2개의 인스턴스가 생성되어 할당될 것으로 기대하지만, 실제로는 같은 인스턴스의 주소를 공유하다가 값이 변경되면, 새로운 인스턴스를 할당합니다. 이를 통해 변경되지 않는 인스턴스에 대한 복사본을 만들어 놓지 않기 때문에 메모리 사용을 최적화할 수 있습니다.

## mutating 키워드의 의미는 무엇인가요?

> struct는 `불변성`을 가지는 값 타입입니다. 즉, 다중 스레드 환경에서 `스레드 안정성`을 제공합니다. 따라서 구조체의 인스턴스 메서드로 프로퍼티의 값을 변경할 수 없습니다. 하지만, mutating 키워드를 통해 메서드를 구현하면, 해당 메서드로는 인스턴스의 프로퍼티를 수정할 수 있게됩니다.

## class가 무엇인가요?

> class는 `사용자 정의 타입`을 만들기 위해 Swift에서 제공하는 기능입니다. 프로퍼티에 데이터를 저장하여 `인스턴스`를 생성하고 객체로 사용할 수 있습니다. class는 struct와 `상속`이 가능하고, `프로토콜` 채택도 가능합니다. 또한 `참조` 타입이기 때문에 값을 전달할 때, 인스턴스의 참조값을 전달합니다.

## struct와 class의 공통점, 차이점은 무엇인가요?

> struct와 class는 프로퍼티에 값을 저장하고, `인스턴스`를 생성하여 객체로 사용할 수 있고, `프로토콜`을 채택할 수 있습니다.
> `class는 상속이 가능`하지만, `struct는 상속이 불가능`합니다.
> class는 `참조 타입`이고, struct는 `값 타입`입니다.
> class는 `힙 영역`에 인스턴스를 저장하고, 참조값을 `스택 영역`에 저장합니다. 반면에 struct는 인스턴스를 `스택 영역`에 저장합니다.

## 프로토콜과 클래스의 차이는 무엇인가요?

> 클래스는 `선언부와 구현부`를 모두 가지고 있는 반면에 프로토콜은 `선언부`만 갖습니다. 다만, `Extension`을 통해 프로토콜 또한 기본 구현을 할 수 있습니다.

## Extension은 무엇인가요?

> Extension은 클래스, 구조체, 열거형 타입에 새로운 메서드, 프로퍼티, 생성자를 추가적으로 정의하기위해 사용됩니다. 이때, 저장 프로퍼티는 Extension에 정의할 수 없고, 연산 프로퍼티만 정의할 수 있습니다. 또한, where를 사용하면, 특정 조건에 부합하는 타입에 대해서만 Extension을 적용할 수 있습니다.

## Extension 내부에서 함수를 override할 수 있을까요?

> Extension 내부에서는 함수를 override할 수 없습니다. 다만, 새로운 함수를 추가할 수는 있습니다.

## enum은 무엇인가요?

> enum은 열거형으로 연관된 항목들을 묶어서 표현할 수 있는 타입입니다. 따라서 제한된 선택지를 주고 싶을 때 유용합니다. 또한 열거형은 연산 프로퍼티와 메서드를 가질수 있고, 각 case는 raw value와 associated value를 가질 수 있습니다.

## enum에서 raw value와 associated value의 차이는 무엇인가요?

> raw value는 원시값으로 열거형의 모든 case는 동일한 타입의 원시값을 갖고, 1개만 가질 수 있습니다. 반면에 associated value는 튜플을 통해 각 case마다 다른 타입을 가질 수 있고, 여러 개의 연관값을 가질 수 있습니다.

## struct와 class와 enum의 차이를 설명하시오.

> struct와 class는 프로퍼티에 값을 저장하고, 인스턴스를 생성하여 객체로 사용할 수 있습니다. 반면에, 열거형은 연관된 항목들을 묶어서 표현할 수 있는 타입입니다. 따라서 제한된 선택지를 주고 싶을 때 유용합니다.
> struct와 enum은 값 타입이고, class는 참조 타입입니다. 값 타입은 값을 전달할 때, 인스턴스를 복사해서 전달하고, 참조 타입은 인스턴스의 참조를 전달합니다.
> 클래스는 상속이 가능하지만, 구조체와 열거형은 상속이 불가능합니다.
> 캡슐화한 값을 참조하는 것보다 복사하는 것이 합당하면, 구조체를 사용하고 그렇지 않다면 클래스를 사용하는 것이 좋습니다.

## Swift의 upcasting과 downcasting의 차이는 무엇인가요?

> 서로 상속 관계에 있는 클래스에서 자식 클래스를 부모 클래스로 타입 캐스팅하는 것을 업 캐스팅이라 하고, 반대로 부모 클래스를 자식 클래스로 타입 캐스팅하는 것을 다운 캐스팅이라고 합니다. 업 캐스팅은 컴파일 시점에 타입 캐스팅 가능 여부가 판별되기 때문에 컴파일이 되면 항상 성공하고, as 키워드를 통해 업 캐스팅을 할 수 있습니다.
> 반면에 다운 캐스팅은 실패할 가능성이 존재하기 때문에 as!와 as? 키워드를 통해 타입 캐스팅을 합니다. as!는 다운 캐스팅에 실패하면, 런타임 에러를 발생시키고, as?는 nil을 반환합니다.

## let과 var의 차이는 무엇인가요?

> let은 한번 할당하면 변경할 수 없는 상수를 선언할 때 사용하는 명령어이고, var은 변경 할 수 있는 변수를 선언할 때 사용하는 명령어입니다.

## function과 method의 차이는 무엇인가요?

> function은 재사용 가능한 코드 블럭을 의미하고, method는 클래스, 구조체, 열거형에 포함되는 function을 의미합니다.

## 커스텀 객체의 배열이 있을 때, 프로퍼티를 기준으로 배열을 어떻게 정렬할까요?

> 고차함수인 sorted 함수의 인자로 클로저를 전달하여 정렬할 수 있습니다.

## 고차함수가 무엇인가요?

> 고차함수는 함수의 인자로 함수를 전달하거나 함수를 반환할 수 있는 함수를 의미합니다.

## inout이 무엇이고 언제사용하면 좋을까요?

> inout 파라미터는 값타입의 변수가 저장된 주소값을 함수 안과 밖에서 동일하게 사용하기 위해 사용합니다. 즉, 함수 내부에서 적용된 변경사항이 외부에서도 동일하게 적용되어야 할 때 사용합니다. 예를들어, 두개의 값을 서로 교환할 때 사용하는 swap메서드를 직접 구현할 때, inout을 사용하면 간단하게 구현할 수 있습니다.

```swift
// https://stackoverflow.com/questions/62266178/swift-function-that-swaps-two-values
func swap<T>(a: inout T, b: inout T) {
    (a, b) = (b, a)
}
var a = 0, b = 1
swap(a: &a, b: &b)
```

## 메서드 안에서 언제 self를 사용해야할까요?

> 인스턴스 프로퍼티 이름과 메서드 파라미터 이름이 동일할 때, 인스턴스 프로퍼티임을 명시하기 위해 self를 사용합니다.

## Array, Set, Dictionary의 차이점은 무엇인가요?

> Array는 Random Access가 가능한 리스트 컬렉션으로 인덱스로 요소에 접근할 수 있는 자료구조입니다. Set은 Hashable 프로토콜을 채택하는 중복을 허용하지 않는 데이터를 관리하는 자료구조이고, 순서가 보장되지 않습니다. Dictionary는 Key-Value 쌍으로 데이터를 관리하는 자료구조입니다. Key의 값은 Hashable 프로토콜을 채택하고 중복된 키를 허용하지며, 순서를 보장하지 않습니다.

## Array보다 언제 Set을 사용하는 것이 좋을까요?

> 순서가 중요하지 않고, 중복을 허용하지 않는 경우 Set을 사용하는 것이 더 좋습니다. 특히 Set은 삭제, 삽입, 조회를 모두 시간 복잡도 O(1)으로 가능하기 때문에 순서가 중요하지 않으면서 삭제와 삽입 연산이 빈번할 때 Set이 더 좋을 수 있습니다.

## required 키워드는 무엇인가요?

> required 키워드가 붙은 생성자는 해당 클래스를 상속받는 클래스에서 해당 생성자를 반드시 구현하도록 강제합니다. required에는 override 키워드의 기능이 포함되어 있기 때문에 override를 생략하고 구현할 수 있습니다.

## self와 Self의 차이가 무엇인가요?

> self는 현재 인스턴스를 의미합니다. Self는 프로토콜의 경우 해당 프로토콜을 채택하는 타입을 의미하고, 클래스, 구조체, 열거형의 경우에는 실제 선언에 사용된 타입을 의미합니다.

## Trailing Closure가 무엇인가요?

> Trailing Closure는 함수의 인자로 클로저를 받을 때, 함수 호출 외부에 코드를 작성하는 방법입니다. 파라미터 레이블을 생략할 수 있으며, 파라미터가 클로저 뿐이라면, ()를 생략할 수도 있습니다.

## @objc는 언제 사용하나요?

> @objc는 Swift의 API를 Objective-C 런타임에 사용할 수 있도록 하기위해 사용합니다.

## deinit은 언제 사용할까요?

> deinit은 인스턴스가 메모리에서 해제되기 직전에 호출됩니다. 따라서 인스턴스가 메모리에서 해제되기 전에 선행되어야하는 작업이 있다면 deinit에 구현할 수 있습니다.

## defer에 대해 설명해보세요.

> defer는 함수가 종료되기 직전에 호출되는 코드 블럭을 의미합니다.

- defer가 여러 개 있다면, 역순으로 실행됩니다.

```swift
func deferTest() {
    print(1)
    defer {
        print("last1")
    }
    defer {
        print("last2")
    }
    defer {
        print("last3")
    }
    print(2)
}

deferTest()
// 1
// 2
// last3
// last2
// **last1**
```

- defer가 중첩되어 있다면, 바깥 defer부터 실행됩니다.

```swift
func deferTest() {
    print(1)
    defer {
        print("last1")
        defer {
            print("last2")
            defer {
                print("last3")
            }
        }
    }
    print(2)
}

deferTest()
// 1
// 2
// last1
// last2
// last3
```

## open과 public 키워드의 차이를 설명해보세요.

> open과 public 모두 외부 모듈에서의 접근까지 허용하는 접근 지정자입니다. open은 외부 모듈에서의 클래스 상속과 메소드 오버라이딩을 허용하지만, public은 외부 모듈에서의 클래스 상속과 메소드 오버라이딩을 허용하지 않습니다. 하지만, 같은 모듈 내에서의 클래스 상속과 오버라이딩은 허용합니다.

## Optional 이란 무엇인지 설명하시오.

> Optional은 값이 있을 수도 있고, 없을 수도 있음을 나타내는 열거형으로 구현된 Swift의 특별한 데이터 타입입니다. 값이 없는 경우에는 nil을 의미하고, 값이 있는 경우에는 연관값에 값이 Wrapping되어 있습니다.

## Convenience init에 대해 설명하시오.

> Convenience init은 클래스의 지정 생성자를 보다 더 간편하게 호출하기 위한 보조 생성자입니다. 지정 생성자는 클래스의 모든 프로퍼티가 적절한 기본값으로 설정되도록 보장하는 역할을 합니다. 반면에, Convenience init은 일부 프로퍼티 값만 입력받아 내부적으로 지정 생성자를 호출합니다.

## String은 왜 subscript로 접근이 안되는지 설명하시오.

> Swift의 문자열을 구성하는 각 문자는 여러 문자로 합성된 `Unicode Scalar` 로 이루어져 있습니다. 따라서 한 문자가 가변 크기를 갖기 때문에 subscript로 접근할 수 없습니다.

## class 메서드와 static 메서드의 차이점을 설명하시오.

> class 메서드와 static 메서드는 모두 `타입 메서드`이기 때문에 인스턴스를 생성하지 않고도 타입명으로 메서드를 호출할 수 있습니다.
> class 메서드는 `오버라이딩`을 허용하지만, static 메서드는 오버라이딩을 허용하지 않습니다.

## Delegate 패턴을 활용하는 경우를 예를 들어 설명하시오.

> Delegate 패턴은 `한 객체가 다른 객체에게 특정 작업을 위임하는 형태의 디자인 패턴`입니다. iOS의 UIKit 프레임워크에서 Delegate 패턴을 아주 많이 사용하고 있습니다. 예를들면, TextField의 text가 변경되었을 때, 해당 이벤트를 전달받아 처리하기 위해 Delegate 프로토콜을 채택하여 구현할 수 있습니다.

## fileprivate을 설명하고 언제 사용하면 좋을지 이야기해보세요.

> fileprivate은 같은 소스 파일 내에서의 접근만을 허용하는 접근 지정자입니다. 같은 파일 내부에서만 사용되는 클래스일 때, fileprivate으로 제한하면 유용하게 사용할 수 있습니다.

## fileprivate과 private의 차이를 설명해보세요.

> fileprivate은 같은 파일 내에 있다면 접근을 허용하지만, private은 같은 파일에 있더라도 private으로 선언한 대상의 구현부 내부, 그리고 같은 파일 내부에 있는 동일한 선언의 Extension 에서만 접근할 수 있습니다.

## function과 closure의 차이를 설명해보세요.

> function과 closure는 실행 가능한 코드 블럭을 의미합니다. function은 func 키워드를 통해 항상 함수의 이름을 가져야합니다. 반면에 closure는 이름을 가지지않아도 됩니다.

## Swift에서 추상 클래스를 만들려면 어떻게 해야하나요?

> Swift에서는 추상 클래스의 문법을 제공하지 않습니다. 하지만, 프로토콜을 통해 동일한 동작을 하도록 할 수 있습니다. 프로토콜에 프로퍼티와 메소드의 원형을 선언해두고, Extension을 통해 프로토콜의 메서드의 기본 구현체를 만들어주면, 추상 클래스와 동일한 개념의 구현이 가능합니다.

## Any와 AnyObject는 무엇이고 차이점은 무엇이죠?

> Any와 AnyObject는 여러 타입을 표현할 수 있는 범용 타입입니다. 하지만 AnyObject는 클래스 타입만 저장할 수 있도록 제한합니다.

## 언제 클래스 대신 구조체를 사용하면 좋을까요?

> 비교적 간단한 데이터 구조를 가지는 경우에 구조체를 사용하는 것이 적합합니다. 또한, 구조체는 불변성을 가지기 때문에 다중 스레드 환경에서 스레드 안정성을 제공합니다. 따라서 경쟁 조건이 발생하는 상황에 구조체를 사용하면 안전하게 데이터를 유지할 수 있습니다.

## 언제 구조체 대신 클래스를 사용하면 좋을까요?

> 비교적 복잡한 데이터 구조를 가지는 경우에 클래스를 사용하는 것이 적합합니다. 또한 클래스는 값을 전달할 때, 참조값을 전달하기 때문에 값을 전달할 때 같은 인스턴스를 공유하고 싶다면, 클래스를 사용하는 것이 좋습니다.

## static 변수와 class 변수에 대해 설명해보세요.

> static 변수와 class 변수 모두 타입 프로퍼티로 타입명으로 접근할 수 있습니다.
> class 변수로 선언된 타입 프로퍼티는 오버라이딩할 수 있지만, static 변수로 선언된 타입 프로퍼티는 오버라이딩이 불가능합니다.

## autoclosure attribute에 대해서 설명해보세요.

> autoclosure attribute는 클로저가 아닌 코드를 함수 인자로 받을 때, 클로저로 만들어주는 속성입니다. autoclosure의 목적은 코드의 실행을 지연시키기 위함입니다. 단순히 함수의 인자로 클로저를 전달함으로써 코드의 실행을 지연시킬 수 있지만, autoclosure를 사용하면, 함수를 호출하는 쪽의 코드 가독성이 좋아집니다.

## Hashable 프로토콜에 대해서 설명해보세요.

> Hashable 프로토콜을 채택하는 타입은 모두 값을 정수인 해시값으로 표현할 수 있습니다.
> 스위프트의 기본 타입 중 정수, 실수, 문자열, 불리언, 그리고 Set 콜렉션은 Hashable 프로토콜을 채택하고 있습니다.

## Hashable 프로토콜을 채택하는 커스텀 타입이 왜 Equatable도 채택해야하는지?

> 어떤 값에 대한 해시값은 고유하지만, 해시값을 생성하는 built-in 메서드인 hasher(\_:)가 서로 다른 값에 대한 동일한 해시값을 생성할 수 있기 때문입니다. 이것을 해시 충돌이라고 하고, 해시 충돌을 알기 위해서는 두 인스턴스의 값이 일치하는지 확인해야하기 때문에 Equatable 프로토콜을 채택해야합니다.

## 열거형도 Hashable을 채택했을 때, 자동으로 Hashable하게 만들 수 있나요?

> 네, 열거형도 Hashable을 채택하면, Hashable하게 사용할 수 있습니다. 다만, 연관값을 가지고 있다면, hash메서드를 구현해야합니다.

## init?()와 init()은 어떤 차이가 있나요?

> init?()은 실패가능한 생성자로 생성자 코드를 실행하던 중 문제가 발생하면 nil을 반환할 수 있습니다.

```swift
class A {
let a: String

init?(a: String) {
    guard !a.isEmpty else { return nil }
    self.a = a
}
}

print(A(a: ""))
print(A(a: "abc")?.a)
```

## Never 반환 타입에 대해 설명해보세요.

> Never 반환 타입은 비정상적인 종료에 대해 사용할 수 있는 반환 타입이며, 값을 가지지 않습니다.
> 단순히 에러를 Throw하는 것으로 해결할 수 없는 심각한 에러임을 알릴 때 사용할 수 있습니다.

## @escaping에 대해서 설명해보세요.

> @escaping은 함수의 인자로 전달받은 클로저를 함수가 종료된 이후에 실행될 수 있도록 하는 속성입니다.

## @objc와 dynamic에 대해서 설명해보세요.

> @objc는 Swift API를 Objective-C 런타임에 실행할 수 있도록 하는 속성입니다.

> dynamic 키워드를 통해 선언한 멤버 변수나 객체는 Objective-C 런타임에 사용되어 동적 디스패치됩니다. 동적 디스패치란 어떤 메소드가 호출되었을 때, 실제 실행할 메서드를 런타임에 결정하는 것을 말합니다.

## RunLoop에 대해서 설명해보세요.

> RunLoop는 파일, 소켓, 키보드, 마우스 등의 입력 소스를 처리하는 이벤트 처리 루프로써 스레드당 한개씩 생성되며, 스레드에 일이 있을 때는 처리하고, 없을 때는 대기시키는 객체입니다. 메인 스레드를 제외한 다른 스레드에서는 자동으로 실행되지 않으며, 개발자가 직접 코드로 실행시켜야 합니다.

## autoreleasepool에 대해서 설명해보세요.

> autorelease는 인스턴스의 참조 카운트 감소를 즉시 하는 것이 아니라 예약할 수 있게하는 키워드입니다. 등록된 release는 autoreleasepool에 등록되고, autoreleasepool 인스턴스가 메모리에서 해제되면, 등록된 모든 release가 실행됩니다. 만약 함수가 종료될 때, 메모리에서 해제되어야 하는 인스턴가 있다면, autoreleasepool을 통해 명시적으로 인스턴의 참조 카운트를 줄여줄 수 있습니다.

## final 키워드를 클래스 앞에 붙이면 어떤 효과가 있나요?

> 클래스의 메소드나 프로퍼티는 다른 자식 클래스로부터 override될 수 있기 때문에, 이런 override된 메소드는 호출되면, 실제로 실행할 메소드를 vtable을 한번 탐색한 후 결정합니다. 즉, 컴파일 타임에 결정되는 것이 아니라 런타임에 결정되는 것입니다. 이것을 동적 디스패치라고 합니다.
> final 키워드를 통해 클래스를 선언하면, 해당 클래스는 다른 클래스에 의해 상속되지 않는 클래스임을 컴파일러에게 명시하는 것이므로 컴파일 타임에 어떤 메소드를 사용할지 바로 결정할 수 있고, vtable을 거치지않기 때문에 성능상 더 좋은 퍼포먼스를 낼 수 있습니다.

## vtable은 무엇인가요?

> vtable은 클래스마다 존재하며, 메소드 구현체의 주소를 배열로 가지고 있는 가상 메소드 테이블입니다. 이것은 컴파일 타임에 생성되고, 메소드가 호출되었을 때, 사용할 구현체를 런타임에 특정할 수 있도록 해줍니다.

## 프로퍼티 옵저버에 대해 설명해보세요.

> 프로퍼티 옵저버는 저장 프로퍼티의 값이 변경되는 것을 관찰하고, 변경될 때마다 특정한 작업을 수행하기 위해서 사용합니다. didSet과 willSet을 사용해서 프로퍼티의 값이 변경될 때 수행할 작업을 구현할 수 있습니다.

## Property Wrapper에 대해 설명해보세요.

> 프로퍼티 래퍼는 여러 프로퍼티에 대해 반복되는 코드를 재사용하기 위해 사용합니다.
> @PropertyWrapper로 구조체를 정의하고, 내부에 프로퍼티에 대한 동작을 미리 정의해두면, 프로퍼티를 선언할 때, 프로퍼티 래퍼를 키워드로 붙여서 미리 정의한 동작을 재사용할 수 있습니다.

## 고차함수 중 flatMap과 compactMap의 차이를 설명해보세요.

> flatMap과 compactMap은 1차원 배열일 때, nil을 제거하고, 옵셔널 바인딩한 결과를 배열로 반환합니다. 반면에 flatMap은 2차원 배열이면서 옵셔널 타입이 아닐 때, 2차원 배열을 1차원 배열로 변환한 결과를 반환합니다. 이때, nil 제거와 옵셔널 바인딩을 따로 하지 않습니다.

## Optional은 내부적으로 어떻게 구현되어 있나요?

> Optional은 내부적으로 연관값을 가지는 열거형으로 구현되어있습니다. 값이 있을 때는 연관값으로 값이 Wrapping되어 있고, 값이 없으면 nil을 가지고 있습니다.

## Swift의 참조 타입을 말해보세요.

> Swift의 참조 타입은 클래스, 함수, 클로저가 있습니다.

## Subscription에 대해서 설명해주세요.

> subscription은 리스트, 배열 등의 콜렉션에 인덱스를 통해 요소에 접근할 수 있게 해주는 문법입니다. subscript가 없는 타입은 내부에 subscript 메서드를 구현해서 사용할 수 있습니다.

## String은 왜 subscript로 접근이 불가능한가요?

> Swift의 문자열을 이루는 각 문자들은 여러 문자가 합성된 Unicode Scalar로 이루어져있습니다. 즉, 문자들이 고정크기가 아닌 가변크기를 가집니다. 따라서 Swift의 문자열은 subscript로 접근이 불가능합니다.

## Result 타입에 대해서 설명해보세요.

> Result타입은 Success와 Failure case를 가지는 열거형 타입입니다. 이때, Failure는 연관값으로 Error 프로토콜을 채택하는 값을 가집니다. Result타입은 네트워크 통신과 같은 실패할 가능성이 있는 작업의 성공 여부와 결과를 표현하는데 사용할 수 있습니다.

## some 키워드에 대해서 설명해보세요.

> some은 불명확한 타입을 의미하고, 함수 내부에서 반환하는 타입을 외부에서 명확하게 알지 못하도록 제한할 때 사용합니다.

## KVC에 대해서 설명해보세요.

> KVC는 Key-Value Coding으로 객체의 값을 직접 사용하지 않고, KeyPath를 통해 객체를 간접적으로 사용하거나 수정하는 방법입니다.

## KVO 동작 방식에 대해 설명하시오.

> KVO는 `Key-Value Observing`으로 key에 등록된 변수의 값이 변경되는 것을 `관찰`하고, 변경될 때마다 특정한 작업을 수행하기 위해 사용합니다. Objective-C 런타임에 의존하기 때문에 `NSObject`를 채택해야하고, 관찰할 프로퍼티에 `@objc` 와 `dynamic` 키워드를 붙여야 합니다.

## typealias 가 무엇인가요?

> typealias는 기존타입에 별칭을 붙여서 사용하는 방법입니다. Swift의 기본 데이터 타입뿐만아니라 커스텀 타입, 클로저에도 사용할 수 있습니다.

## associatedType이 무엇인가요?

> associatedType은 프로토콜에 제네릭으로 타입을 정의하는 방법입니다. 해당 프로토콜을 채택하는 타입에서 인터페이스로 제공한 타입을 정의하여 사용합니다.

## Generic이 무엇인가요?

> Generic은 함수나 타입안에서 사용될 수 있고, 인자로 전달되는 타입을 일반화할 수 있는 방법입니다.

## Codable이 무엇인가요?

> Codable은 Encodable과 Decodable을 모두 채택하는 프로토콜입니다.

## Encodable과 Decoable은 무엇인가요?

> Encodable은 객체를 JSON 또는 바이너리 형태로 변환할 수 있도록 기능을 제공하는 프로토콜이고, 반대로 Decodable은 JSON 또는 바이너리 형태의 외부 데이터를 Swift 객체로 변환할 수 있도록 기능을 제공하는 프로토콜 입니다.

## @main에 대해서 설명해주세요.

> main 속성은 앱의 Entry Point를 나타냅니다. 이는 프로그램이 시작될 때 가장 먼저 실행되는 부분을 정의하는 역할을 합니다.

## ARC

## ARC가 무엇이죠?

> ARC는 Automatic Reference Counting으로 Swift에서는 앱의 메모리 사용량을 추적하고 관리하기 위해 ARC를 사용합니다. Retain과 Release를 컴파일러가 컴파일 시점에 자동으로 삽입하고, Reference Count를 통해 참조 타입의 인스턴스를 관리합니다. 참조 횟수가 0이 되면, 즉 더이상 해당 인스턴스를 참조하지 않으면, ARC는 인스턴스를 메모리에서 해제합니다. 컴파일 시점에 처리하기 때문에 성능상 이점이 존재하지만, 단순히 참조 횟수를 통해 인스턴스를 관리하기 때문에 Retain Cycle 문제가 발생할 가능성이 있습니다.

## 강한 참조는 무엇이고 왜 필요한가요?

> 강한 참조는 참조 타입 인스턴스를 변수에 할당하는 것을 의미하고, 인스턴스의 Reference Count를 1 증가시킵니다. 스위프트의 ARC는 Reference Count를 통해 인스턴스를 관리하고, 참조 카운트가 0이되면, 메모리에서 해제합니다. 따라서 강한참조는 인스턴스의 참조값을 증가시켜서 메모리에서 유지해야할 때, 사용합니다.

## Retain Count 방식에 대해 설명하시오.

> 참조 타입의 인스턴스가 생성되면, 해당 인스턴스의 참조 횟수를 계산하고, 참조 횟수가 0이면, 더 이상 사용되지않는 인스턴스로 판단해 메모리에서 해제됩니다.

## 순환 참조(Retain Cycle)가 무엇이고 해결방법은 무엇인가요?

> 서로 다른 인스턴스의 프로퍼티가 서로를 강하게 참조하는 경우 Retain Cycle이 발생합니다. Retain Cycle이 발생한 두 인스턴스는 참조횟수가 0에 도달하지 못하므로 메모리에서 해제되지 못하여 메모리 누수 문제로 이어집니다. 이 문제를 예방하기 위해 약한 참조, 미소유 참조를 사용할 수 있습니다.

## weak, unowned referenece(약한 참조, 미소유 참조)는 무엇이고 차이는 무엇인가요?

> 약한 참조와 미소유 참조는 모두 참조하는 인스턴스의 참조 횟수를 증가시키지 않기 때문에 Retain Cycle 문제를 예방할 수 있습니다. 약한 참조는 인스턴스가 메모리에서 해제되면 자동으로 nil이 할당되기 때문에 항상 Optional타입 입니다. 반면에 미소유 참조는 인스턴스가 메모리에서 해제되더라도 자동으로 nil이 할당되지 않기 때문에 참조하는 인스턴스가 메모리에 유지될 것이라는 확신이 있는 경우에만 미소유 참조를 사용해야합니다. 만약 인스턴스가 메모리에서 해제된 후 미소유 참조 프로퍼티를 재참조하는 경우 런타임에러가 발생합니다.

## strong, weak, unowned reference는 각각 언제 사용할까요?

> 강한 참조는 참조하는 인스턴스를 메모리에 유지시키기 위해서 사용할 수 있습니다. 참조의 방향이 단방향으로 이루어지면 항상 안전하지만, 그렇지 않은 경우에는 Retain Cycle 문제가 발생합니다. Retain Cycle 문제를 예방하기 위해 약한 참조, 미소유 참조를 사용할 수 있습니다. 약한 참조와 미소유 참조는 모두 참조하는 인스턴스의 참조 횟수를 증가시키지 않습니다. 약한 참조는 인스턴스가 메모리에서 해제되면 자동으로 nil이 할당되기 때문에 항상 Optional 타입입니다. 반면에 미소유 참조는 인스턴스가 메모리에서 해제되더라도 자동으로 nil을 할당하지 않습니다. 따라서 참조하는 인스턴스가 메모리에 유지될 것이라는 확신이 있는 경우에는 미소유 참조를 사용하고 그 외의 경우에는 약한 참조를 사용하는 것이 좋습니다.

## ARC와 GC는 어떤 차이가 있나요?

> ARC와 GC의 가장 큰 차이는 컴파일 타임에 처리되는지, 런타임에 처리되는지에 있습니다. ARC는 Retain과 Release를 컴파일러가 컴파일 시점에 자동으로 삽입해 참조횟수를 조절합니다. 반면에 GC는 가비지 컬렉터를 런타임에 별도로 실행시켜 메모리 상태를 감시합니다. ARC는 단순히 참조 횟수를 통해 인스턴스를 관리하기 때문에 순환참조의 위험성이 있습니다. 하지만, GC는 Mark-and-Sweep 방식을 통해 루트노드로부터 도달할 수 있는 인스턴스들을 모두 체크합니다. 따라서 순환참조가 발생하더라도 두 인스턴스를 참조하는 인스턴스가 메모리에서 해제되면, 루트노드로부터 순환참조가 발생한 인스턴스로 도달할 수 있는 경로가 없기 때문에 두 인스턴스를 모두 메모리에서 해제할 수 있습니다.

# Functional Programming

## 함수형 프로그래밍이 무엇인지 설명하시오.

> 함수형 프로그래밍은 순수함수를 기반으로하는 프로그래밍 패러다임입니다.

## 순수함수란 무엇인지 설명하시오.

> 순수함수는 동일한 입력에 대해 항상 동일한 출력을 제공하는 함수입니다. 즉, 사이드 이펙트가 없습니다.

## 사이드 이펙트는 무엇인가요?

> 사이드 이펙트는 함수를 통해 함수 외부의 상태값을 변화시키는 것을 의미합니다.

## 순수함수가 왜 필요하다고 생각하나요?

> 동일한 입력에 대해 항상 동일한 출력을 제공하는 순수함수는 테스트하기 용이합니다. 외부의 상태값에 영향을 받지 않기 때문에 해당 함수만 테스트할 수 있기 때문입니다. 그리고, 사이드 이펙트가 없기 때문에 순수함수를 포함하는 객체는 유지보수성이 좋습니다. 프로퍼티나 함수들이 다른 함수에 의존적이지 않기 때문에 쉽게 기능을 확장하고 수정할 수 있습니다.

## 1급 객체에 대해서 설명해보세요. Swift에는 어떤 1급 객체들이 있나요?

> 1급 객체는 상수나 변수에 할당할 수 있고, 함수의 인자로 전달되거나 반환값으로 사용할 수 있는 객체를 의미합니다.
> Swift의 1급 객체로 기본 타입, 함수, 클로저가 있습니다.

## 고차 함수가 무엇인지 설명하시오.

> 고차 함수는 함수의 파라미터로 함수를 전달할 수 있고, 함수를 반환할 수 있는 함수를 의미합니다.

## Swift Standard Library의 map, filter, reduce, compactMap, flatMap에 대하여 설명하시오.

>

# Architecture

## MVVM, MVI, Ribs, VIP 등 자신이 알고있는 아키텍쳐를 설명하시오.

### MVVM

> MVVM은 `Model-View-ViewModel`로 구성되어 있는 디자인 패턴입니다.
>
> Model은 데이터, 네트워크 로직, 비즈니스 로직등을 가지며, 데이터를 `캡슐화`하는 역할을 합니다.
>
> View는 `UI`와 관련된 로직을 담고있고, Model을 직접적으로 가지고 있으면 안됩니다.
>
> ViewModel은 View로부터 전달받는 요청을 처리할 로직을 담고있고, Model에 변화가 생기면, View에 변경사항을 전달합니다. 따라서 ViewModel은 `View와 Model 사이의 중재자 역할`을합니다.

### MVC

> MVC는 `Model-View-Controller`로 구성되어 있는 디자인 패턴입니다.
>
> Model은 `데이터와 비즈니스 로직`을 가지고 있습니다.
>
> View는 `UI`를 담당합니다.
>
> Controller는 `Model과 View의 중간다리 역할`로 View로부터 사용자 입력을 받아 Model에게 작업을 요청하거나, Model을 통해 View를 업데이트합니다.

## 의존성 주입에 대하여 설명하시오.

> 의존성 주입은 클래스가 자신의 `의존성`을 직접 관리하는 대신 `외부에서 이를 제공하는 방식`입니다. 예를 들어, 클래스 A가 클래스 B의 인스턴스를 필요로 하는 경우, 클래스 A의 내부에서 직접 생성하는 것이 아니라 `생성자나 메서드`를 통해 `외부에서 클래스 B의 인스턴스를 주입받는 것`을 의미합니다.

# SwiftUI

## @State가 어떻게 동작하는지 설명하시오.

> @State는 read/write 가능한 `property wrapper`타입입니다. state 값이 변경되면 SwiftUI는 해당 프로퍼티값을 통해 표시되는 `view 계층구조의 일부분을 자동으로 업데이트`합니다.

## @Binding이 무엇인가요?

> 자식 뷰에서 `부모 뷰의 State를 변경하기 위해` 사용되는 프로퍼티 래퍼입니다.

## @Published가 무엇인가요?

> @Published는 프로퍼티가 변경될 때마다 `publisher`를 통해 알림을 보내는 프로퍼티 래퍼입니다.

## ObservableObject가 무엇인가요?

> ObservableObject 프로토콜을 준수하는 객체는 `자신의 상태 변화`를 외부에 알릴 수 있습니다.

## ViewModifier가 무엇인가요?

> ViewModifier는 뷰의 모양, 동작 및 다른 특성을 수정하는 custom modifier를 만드는데 사용되는 프로토콜입니다. 이를 통해 뷰의 모양이나 동작을 쉽게 수정하고 재사용할 수 있어 코드를 간결하게 할 수 있습니다.

# Combine

## PassthroughSubject에 대해서 설명하시오
> PassthroughSubject는 send메서드를 통해 subject에 값을 전달할 수 있고, 해당 subject를 구독하는 구독자들에게 값을 전달합니다. PassthroughSubject는 버퍼링 기능을 제공하지 않습니다. 따라서 구독 이후부터 발행된 값을 전달 받을 수 있습니다.

## CurrentValueSubject에 대해서 설명하시오
> CurrentValueSubject는 send메서드를 통해 subject에 값을 전달할 수 있고, 해당 subject를 구독하는 구독자들에게 값을 전달합니다. CurrentValueSubject는 PassthroughSubject와 달리 초깃값을 가지며, 가장 최근에 발행된 값의 버퍼를 유지합니다.

## @Published에 대해서 설명하시오
> @Published는 프로퍼티가 변경될 때마다 publisher를 통해 알림을 보내는 프로퍼티 래퍼입니다.

## sink에 대해서 설명하시오
> sink는 publisher를 구독하는 메서드로 AnyCancellable 인스턴스를 반환합니다.

## AnyCancellable에 대해서 설명하시오
> AnyCancellable 인스턴스는 publisher에서 데이터를 구독할 때마다 생성되며, 이를 통해 구독을 관리하고 필요한 경우 구독을 취소할 수 있습니다. 메모리 누수를 방지하기 위해, AnyCancellable 인스턴스를 적절하게 저장해두는 것이 중요합니다. 일반적으로 이를 위해 Set 컬렉션에 AnyCancellable 인스턴스를 저장하여 관리합니다.

## throttle과 debounce의 차이점을 설명하시오.

## Data를 Binding 하는 방법에 대해서 설명하시오.

# GCD

## GCD가 무엇인가요?

> GCD는 멀티 코어, 멀티 프로세싱 환경에서 동시성 프로그래밍을 위한 애플이 개발한 라이브러리입니다. GCD를 사용하면 여러 작업을 동시에 처리하거나 작업의 실행 순서를 관리하는 등의 복잡한 작업을 쉽게 처리할 수 있습니다. GCD는 작업을 비동기적으로 실행하는 방법을 제공하며, 이를 위해 Dispatch Queue라는 개념을 사용합니다.

## Dispatch Queue는 무엇인가요?

> Dispatch Queue는 작업을 관리하는 큐로, 큐에 추가된 순서대로 실행되는 First-In-First-Out(FIFO)방식입니다. Dispatch Queue는 Serial Queue와 Concurrent Queue로 나뉩니다.

## DispatchQueue의 Serial Queue가 무엇인가요?

> Serial Queue는 직렬큐로 한번에 하나씩 작업을 처리하는 작업큐입니다. 스레드에 먼저 할당된 작업이 있다면, 해당 작업이 완료된 후 큐에 대기중인 다음 작업을 스레드에 할당합니다.

## DispatchQueue의 ConcurrentQueue 가 무엇인가요?

> Concurrent Queue는 동시에 여러 작업을 한번에 처리하는 작업큐입니다. 작업의 종료 여부와 상관없이 할당 가능한 스레드가 있다면 작업을 할당하여 처리합니다.

## 그렇다면, Serial과 Concurrent는 각각 어느 상황에 써야할까요?

> 작업의 순서가 중요한 경우 Serial Queue를 사용하고, 작업의 순서가 중요하지 않고, 오래 걸리는 작업을 효율적으로 처리하기 위해 Concurrent Queue를 사용합니다.

## 동기(Synchronous)와 비동기(Asynchronous)를 설명해보세요.

> 동기는 선행 작업의 완료를 대기하고, 완료된 후 순차적으로 다음 작업을 수행하는 것을 의미합니다. 반대로 비동기는 선행 작업의 완료 여부와 상관없이 곧바로 다음 작업을 수행하는 것을 의미합니다.

## DispatchQueue.main.async와 DispatchQueue.main.sync의 차이는 무엇인가요?

> 우선 두 방법 모두 DispatchQueue에 작업을 등록하고 메인 스레드에서 작업이 수행되도록 합니다. main.async는 async로 작업을 등록하기 때문에 등록한 작업의 완료를 대기하지 않고 곧바로 다음 코드를 수행합니다. 반면에 main.sync는 sync로 작업을 등록하기 때문에 등록한 작업이 완료될 때까지 스레드를 중단합니다.

## Concurrent와 Serial Queue가 async, sync와 함께 사용되는 상황에 대해 설명해보세요.

> Concurrent와 async는 DispatchQueue에 작업을 async로 등록하기 때문에 작업을 등록하는 스레드는 작업의 완료를 대기하지 않고, 곧바로 다음 코드를 수행합니다. DispatchQueue에 등록된 작업은 Concurrent하게 처리되기 때문에 작업의 종료여부와 상관없이 할당 가능한 스레드가 있다면 큐에 있는 작업을 스레드에 할당시켜 작업을 시작합니다.

> Concurrent와 sync는 DispatchQueue에 작업을 sync로 등록하기 때문에 작업을 등록하는 스레드는 작업이 완료될 때까지 중단됩니다. DispatchQueue에 등록된 작업은 Concurrent하게 처리되기 때문에 작업의 종료여부와 상관없이 할당 가능한 스레드가 있다면, 큐에 있는 작업을 스레드에 할당시켜 작업을 시작합니다.

> Serial과 async는 DispatchQueue에 작업을 async로 등록하기 때문에 작업을 등록하는 스레드는 작업의 완료를 대기하지 않고, 곧바로 다음 코드를 수행합니다. DispatchQueue에 등록된 작업은 Serial하게 처리되기 때문에 현재 작업이 완료되면 큐에 등록된 다음 작업을 스레드에 할당해 순차적으로 처리합니다.

> Serial과 sync는 DispatchQueue에 작업을 sync로 등록하기 때문에 작업을 등록하는 스레드는 작업이 완료될 때까지 중단됩니다. DispatchQueue에 등록된 작업은 Serial하게 처리되기 때문에 현재 작업이 완료되면 큐에 등록된 다음 작업을 스레드에 할당해 순차적으로 처리합니다.

## GCD의 QoS에 대해서 설명해보세요.

> QoS는 DispatchQueue에 등록하는 작업의 우선순위를 결정하는 것입니다.
> 우선 순위가 높은 작업은 우선 순위가 낮은 작업보다 먼저 처리될 수 있으며, 더 많은 리소스를 차지합니다.
> QoS 수준은 우선순위 순서대로 userInteractive, userInitiated, default, utility, background 가 있습니다.

## DispatchGroup에 대해 설명해보세요.

> DispatchGroup은 여러개의 스레드에 분산되어 있는 작업들을 하나의 Group으로 묶어서 동기적으로 관리하기 위해 사용합니다. 그룹에 작업을 추가할 때, enter 메서드를 통해 작업의 개수를 1 증가시키고, 작업이 끝나면 leave 메서드를 통해 작업의 개수를 1 감소시킵니다. 이때, 작업의 수가 0이 되면, notify 메서드가 호출되어 그룹의 모든 작업이 완료되었을 때, 함께 수행할 작업을 처리할 수 있습니다.

## DispatchWorkItem의 장점이 무엇인가요?

> DispatchWorkItem은 DispatchQueue에 등록할 작업을 캡슐화 할 수 있습니다. 또한, DispatchWorkItem에서 제공하는 cancel과 wait등의 메서드를 통해 작업의 동작을 쉽게 관리할 수 있습니다.

## GCD의 Barrier에 대해 설명해주세요.

> 배리어로 등록된 작업은 해당 작업이 끝나기 전까지 동시에 GCD에서 다른 작업이 수행되지 않도록합니다.
> 배리어 플래그를 가지는 작업이 등록되면, 큐에서 해당 작업 이전에 등록된 작업들을 모두 처리할 때까지 배리어와 배리어 이후에 등록된 작업의 실행을 지연시키고, 선행 작업들이 모두 끝났을 때, 배리어 작업을 단독으로 실행합니다.

## DispatchSemaphore를 사용하는 상황을 설명해주세요.

> DispatchSemaphore는 Lock의 기능을 구현할 수 있습니다. 특정한 공유 자원에 동시에 접근할 수 있는 스레드의 수를 제한할 때 사용합니다. wait메소드로 세마포어의 값을 줄이고, signal메소드로 세마포어의 값을 증가시킴으로써 Lock을 구현할 수 있습니다.

# Swift Concurrency

## @MainActor는 언제 이용하는가?

>

## task동작 방식과 gcd, nsoperation과의 차이점을 설명하시오.

>

# Optional

아래부터는 추가로 공부를 하면 좋을 내용들입니다.

Objective-c나 rx는 회사, 팀마다 사용하는곳이 차이가있고 신입이나 주니어기준으로 필수라고 여겨지지않기에 옵셔널에 추가하였습니다.

# Rx

## Reactive Programming이 무엇인지 설명하시오.
> Reactive Programming은 데이터 흐름과 변화 전파에 중점을 둔 프로그래밍 패러다임입니다. iOS에서 리액티브 프로그래밍은 주로 비동기 작업을 간편하게 관리하고 UI업데이트와 같은 작업을 구현하는데 사용됩니다. 이를 통해 앱 내에서 다양한 이벤트가 발생할 때마다 즉시 반응하고, UI를 업데이트할 수 있습니다.

## RxSwift를 왜 사용하는지 설명하시오. (장점을 설명하시오)
> RxSwift를 사용하면 복잡한 비동기 작업과 이벤트 처리 코드를 간결하고 직관적으로 작성할 수 있습니다.

## RxSwift의 단점을 설명하시오.
> RxSwift에서 발생하는 문제를 디버깅하는 것은 복잡하고 어려울 수 있습니다. 리액티브 프로그래밍의 비동기적인 성격 때문에 에러의 원인을 찾거나 행동을 추적하는 것이 어렵게 될 수 있습니다.

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
