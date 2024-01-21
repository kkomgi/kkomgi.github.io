# Structures and Classes

- **구조체와 클래스**

- Custom Types for Data Encapsulation
- **데이터 캡슐화를 위한 사용자 정의 타입**

- Structures and classes are fundamental constructs in Swift that serve as the foundation for building your program's code.
- **구조체와 클래스는 Swift에서 프로그램 코드를 구축하는 기반으로, 기본적인 구성 요소입니다.**

- You can define properties and methods to add functionality to these structures and classes, using the same syntax as when defining constants, variables, and functions.
- **이 구조체와 클래스에 속성과 메서드를 정의하여 기능을 추가할 수 있으며, 상수, 변수, 함수를 정의할 때와 동일한 문법을 사용합니다.**

- Unlike some other programming languages, Swift does not require you to create separate interface and implementation files for custom structures and classes.
- **스위프트는 다른 일부 프로그래밍 언어와 달리, 사용자 정의 구조체와 클래스에 대해 별도의 인터페이스 파일과 구현 파일을 만들 필요가 없습니다.**

- **Note:** Traditionally, an instance of a class is referred to as an "object."

- **참고:** 전통적으로 클래스의 인스턴스는 "객체"로 언급됩니다.

- However, in Swift, structures and classes are functionally closer to each other than in other languages.

- 그러나 Swift에서는 구조체와 클래스가 다른 언어보다 기능적으로 서로 가까운 특성을 공유합니다.

- Much of this chapter applies to instances of both classes and structures.

- 이 장의 대부분은 클래스와 구조체의 인스턴스에 모두 적용됩니다.

- Therefore, the term "instance" is used more broadly.

- 따라서 "인스턴스"라는 용어가 더 널리 사용됩니다.

### Comparing Structures and Classes


### 구조체와 클래스 비교


- Structures and classes in Swift share several common features. 

- Swift에서 구조체와 클래스는 여러 공통 기능을 공유합니다.

- Both can:

- 둘 다 다음을 수행할 수 있습니다:

- - Define properties to store values

-   - 값을 저장하기 위한 속성 정의

- - Define methods to provide functionality

-   - 기능을 제공하기 위한 메서드 정의

- - Define subscripts to provide access to their values using subscript syntax

-   - 서브스크립트 문법을 사용하여 값을 제공하는 서브스크립트 정의

- - Define initializers to set up their initial state

-   - 초기 상태를 설정하기 위한 이니셜라이저 정의

- - Be extended to expand their functionality beyond a default implementation

-   - 확장을 통해 기본 구현을 넘어서기 위한 확장 정의

- - Conform to protocols to provide standard functionality of a certain kind

-   - 특정 종류의 표준 기능을 제공하기 위해 프로토콜을 준수

- Classes have additional capabilities that structures do not have:

- 클래스에는 구조체에는 없는 추가 기능이 있습니다:

- - Inheritance enables one class to inherit the characteristics of another.

-   - 상속을 통해 하나의 클래스가 다른 클래스의 특성을 상속할 수 있습니다.

- - Type casting allows you to check and interpret the type of a class instance at runtime.

-   - 타입 캐스팅을 사용하여 실행 시간에 클래스 인스턴스의 타입을 확인하고 해석할 수 있습니다.

- - Deinitializers enable an instance of a class to free up any resources it has allocated.

-   - 디이니셜라이저를 사용하여 클래스의 인스턴스가 할당한 리소스를 해제할 수 있습니다.

- - Reference counting allows multiple references to a class instance.

-   - 참조 카운팅을 통해 클래스 인스턴스에 대한 다중 참조가 가능합니다.

- These additional capabilities in classes come at the cost of increased complexity. 
- **클래스의 이러한 추가 기능은 복잡성이 증가하는 대가로 제공됩니다.**

- As a general guideline, prefer structures because they are easier to understand. 
- **일반적인 지침으로 구조체를 선호하십시오. 구조체는 이해하기 쉬워서입니다.**

- Use classes when they are appropriate or necessary. 
- **적절하거나 필요할 때 클래스를 사용하십시오.**

- In practice, most of the custom types you define will be structures and enumerations. 
- **실제로 정의하는 대부분의 사용자 정의 타입은 구조체와 열거형일 것입니다.**

- For a more detailed comparison, refer to the "Choosing Between Structures and Classes" section. 
- **더 자세한 비교에 대해서는 "구조체와 클래스 중 어떤 것을 선택할 것인가" 섹션을 참조하십시오.**

- ```swift
- struct Resolution {
-     var width = 0
-     var height = 0
- }

- class VideoMode {
-     var resolution = Resolution()
-     var interlaced = false
-     var frameRate = 0.0
-     var name: String?
- }
- ```

- In this example, we define a `Resolution` structure to represent a pixel-based display resolution, with properties for `width` and `height`.

- **이 예제에서는 `Resolution` 구조체를 정의하여 픽셀 기반의 디스플레이 해상도를 나타내며, `width`와 `height` 속성을 가지고 있습니다.**

- We also define a `VideoMode` class to describe a specific video mode, with properties for `resolution`, `interlaced`, `frameRate`, and an optional `name` string.

- **또한 특정 비디오 모드를 설명하는 데 사용할 `VideoMode` 클래스를 정의하며, `resolution`, `interlaced`, `frameRate`, 그리고 선택적인 `name` 문자열 속성을 가지고 있습니다.**

### Structure and Class Instances


- The definitions of `Resolution` and `VideoMode` describe the structure of these types, but they do not represent specific instances of resolutions or video modes.  
- `Resolution`과 `VideoMode`의 정의는 이러한 유형의 구조를 설명하지만, 해상도나 비디오 모드의 구체적인 인스턴스를 나타내지는 않습니다.

- To work with actual data, you need to create instances of the structure or class.  
- 실제 데이터를 다루기 위해서는 구조체나 클래스의 인스턴스를 생성해야 합니다.

- ```swift
- let someResolution = Resolution()
- let someVideoMode = VideoMode()
- ```

- Both structures and classes use initializer syntax for creating new instances.  
- 구조체와 클래스 모두 새 인스턴스를 생성하기 위해 초기화 구문을 사용합니다.

- The simplest form of initializer syntax involves using the type name followed by empty parentheses, such as `Resolution()` or `VideoMode()`.  
- 초기화 구문의 가장 간단한 형태는 타입 이름 뒤에 빈 괄호를 사용하는 것입니다, 예를 들어 `Resolution()` 또는 `VideoMode()`와 같이 사용합니다.

- This creates a new instance of the structure or class, with properties initialized to their default values.  
- 이것은 구조체나 클래스의 새로운 인스턴스를 생성하며, 속성들은 기본값으로 초기화됩니다.

- Initialization is covered in more detail in the Initialization section.  
- 초기화는 초기화 섹션에서 더 자세히 다루어집니다.

### Accessing Properties


- You can access the properties of an instance using dot syntax.  
- 인스턴스의 속성에 접근하는 방법 중 하나는 점 구문(dot syntax)을 사용하는 것입니다.

- In dot syntax, you write the property name immediately after the instance name, separated by a period (.), without any spaces:  
- 점 구문에서는 인스턴스 이름 바로 뒤에 속성 이름을 씁니다. 이때 속성 이름과 인스턴스 이름은 점(.)으로 구분되며, 사이에 공백이 없어야 합니다:

- ```swift
- print("The width of someResolution is \(someResolution.width)")
- // Prints "The width of someResolution is 0"
- ```

- In this example, `someResolution.width` refers to the `width` property of `someResolution`, returning its default initial value of 0.  
- 이 예제에서, `someResolution.width`는 `someResolution`의 `width` 속성을 참조하며, 그 기본 초기값인 0을 반환합니다.

- You can also access subproperties, such as the `width` property within the `resolution` property of a `VideoMode`:  
- 또한, `VideoMode`의 `resolution` 속성 내의 `width` 속성과 같은 하위 속성에도 접근할 수 있습니다:

- ```swift
- print("The width of someVideoMode is \(someVideoMode.resolution.width)")
- // Prints "The width of someVideoMode is 0"
- ```

- Dot syntax can also be used to assign a new value to a variable property:  
- 점 구문은 변수 속성에 새로운 값을 할당하는 데에도 사용할 수 있습니다:

- ```swift
- someVideoMode.resolution.width = 1280
- print("The width of someVideoMode is now \(someVideoMode.resolution.width)")
- // Prints "The width of someVideoMode is now 1280"
- ```

### Memberwise Initializers for Structure Types


- All structures have an automatically generated memberwise initializer.  
- 모든 구조체에는 자동으로 생성되는 멤버별 초기화 구문이 있습니다.

- This initializer allows you to initialize the member properties of new structure instances.  
- 이 초기화 구문을 통해 새 구조체 인스턴스의 멤버 속성을 초기화할 수 있습니다.

- You can pass initial values for the properties to the memberwise initializer by name:  
- 멤버별 초기화 구문에 이름을 지정하여 속성의 초기값을 전달할 수 있습니다:

- ```swift
- let vga = Resolution(width: 640, height: 480)
- ```

- Unlike structures, class instances do not receive a default memberwise initializer.  
- 구조체와 달리, 클래스 인스턴스는 기본 멤버별 초기화 구문을 받지 않습니다.

- Initialization is discussed in more detail in the Initialization section.  
- 초기화는 초기화 섹션에서 더 자세히 다루어집니다.

### Structures and Enumerations Are Value Types


- In Swift, a value type is a type whose value is copied when assigned to a variable, constant, or passed to a function.  
- Swift에서 값 타입은 변수, 상수에 할당되거나 함수에 전달될 때 그 값이 복사되는 타입입니다.

- Basic types in Swift, such as integers, floating-point numbers, Booleans, strings, arrays, and dictionaries, are all value types and are implemented as structures behind the scenes.  
- Swift의 기본 타입들, 예를 들어 정수, 부동 소수점 숫자, 불리언, 문자열, 배열, 사전은 모두 값 타입이며, 내부적으로는 구조체로 구현됩니다.

- All structures and enumerations in Swift are value types.  
- Swift의 모든 구조체와 열거형은 값 타입입니다.

- This means that when you create instances of structures and enumerations, as well as any value types they contain as properties, copies are always made when they are passed around in your code.  
- 이는 구조체와 열거형의 인스턴스를 생성할 때, 그들이 속성으로 포함하는 값 타입이 코드에서 전달될 때 항상 복사본이 생성된다는 것을 의미합니다.

- > **Note:** Collections like arrays, dictionaries, and strings in the Swift standard library use an optimization to reduce the performance cost of copying. Instead of making an immediate copy, these collections share memory where elements are stored between the original instance and any copies. If one of the copies is modified, the elements are copied just before the modification. The behavior you observe in your code is as if a copy took place immediately.  
- > **참고:** Swift 표준 라이브러리의 배열, 사전, 문자열과 같은 컬렉션들은 복사의 성능 비용을 줄이기 위해 최적화를 사용합니다. 즉시 복사하는 대신, 이러한 컬렉션들은 원본 인스턴스와 복사본 사이에 요소가 저장된 메모리를 공유합니다. 복사본 중 하나가 수정되면, 수정 전에 요소들이 복사됩니다. 코드에서 관찰하는 동작은 즉시 복사가 이루어진 것처럼 보입니다.

- Consider the following example using the `Resolution` structure from earlier:  
- 앞서 소개된 `Resolution` 구조체를 사용하는 다음 예를 고려해 보세요:

- ```swift
- let hd = Resolution(width: 1920, height: 1080)
- var cinema = hd
- ```

- In this example, `hd` is assigned a `Resolution` instance with the dimensions of full HD video (1920 pixels wide by 1080 pixels high).  
- 이 예제에서, `hd`는 전체 HD 비디오의 치수(가로 1920픽셀, 세로 1080픽셀)를 가진 `Resolution` 인스턴스에 할당됩니다.

- Then, a new variable `cinema` is assigned the current value of `hd`. Since `Resolution` is a structure, a copy of the existing instance is made, and this new copy is assigned to `cinema`.  
- 그 다음, 새로운 변수 `cinema`에 `hd`의 현재 값이 할당됩니다. `Resolution`이 구조체이기 때문에, 기존 인스턴스의 복사본이 만들어지고, 이 새로운 복사본이 `cinema`에 할당됩니다.

- Even though `hd` and `cinema` now have the same width and height values, they are two completely different instances behind the scenes.  
- `hd`와 `cinema`가 같은 너비와 높이 값을 가지고 있지만, 실제로는 완전히 다른 두 인스턴스입니다.

- Next, the `width` property of `cinema` is updated to match the slightly wider 2K standard used for digital cinema projection (2048 pixels wide and 1080 pixels high):  
- 이어서, `cinema`의 `width` 속성이 디지털 시네마 투사에 사용되는 약간 더 넓은 2K 표준(가로 2048픽셀, 세로 1080픽셀)과 일치하도록 업데이트됩니다:

- ```swift
- cinema.width = 2048
- ```

- Checking the `width` property of `cinema` now correctly reports the new width of 2048:  
- 이제 `cinema`의 `width` 속성을 확인하면 새로운 너비인 2048을 정확하게 보고합니다:

- ```swift
- print("cinema is now \(cinema.width) pixels wide")
- // Prints "cinema is now 2048 pixels wide"
- ```

- However, the `width` property of the original `hd` instance remains unchanged with the old value of 1920:  
- 하지만

-  원래 `hd` 인스턴스의 `width` 속성은 이전 값인 1920으로 그대로 유지됩니다:

- ```swift
- print("hd is still \(hd.width) pixels wide")
- // Prints "hd is still 1920 pixels wide"
- ```

- When `cinema` was assigned the current value of `hd`, the values stored in `hd` were copied into the new `cinema` instance. As a result, you have two separate instances that contain the same numeric values. However, since they are distinct instances, changing the width of `cinema` to 2048 does not affect the width stored in `hd`.

- The same behavior applies to enumerations:  
- 동일한 동작이 열거형에도 적용됩니다:

- ```swift
- enum CompassPoint {
-     case north, south, east, west
-     mutating func turnNorth() {
-         self = .north
-     }
- }

- var currentDirection = CompassPoint.west
- let rememberedDirection = currentDirection
- currentDirection.turnNorth()

- print("The current direction is \(currentDirection)")
- print("The remembered direction is \(rememberedDirection)")
- ```

- When `rememberedDirection` is assigned the value of `currentDirection`, it is set to a copy of that value. Changing the value of `currentDirection` afterward does not affect the copy of the original value stored in `rememberedDirection`.  
- `rememberedDirection`에 `currentDirection`의 값이 할당될 때, 그 값의 복사본으로 설정됩니다. 이후 `currentDirection`의 값을 변경해도 `rememberedDirection`에 저장된 원래 값의 복사본에는 영향을 미치지 않습니다.

### Classes Are Reference Types


- In contrast to value types, reference types are not copied when assigned to a variable, constant, or passed to a function.  
- 값 타입과 달리, 참조 타입은 변수, 상수에 할당되거나 함수에 전달될 때 복사되지 않습니다.

- Instead, a reference to the same existing instance is used.  
- 대신, 동일한 기존 인스턴스에 대한 참조가 사용됩니다.

- Here's an example using the `VideoMode` class defined earlier:  
- 앞서 정의된 `VideoMode` 클래스를 사용하는 예를 들어보겠습니다:

- ```swift
- let tenEighty = VideoMode()
- tenEighty.resolution = hd
- tenEighty.interlaced = true
- tenEighty.name = "1080i"
- tenEighty.frameRate = 25.0
- ```

- In this example, a new constant named `tenEighty` is declared, and it is assigned to a new instance of the `VideoMode` class.  
- 이 예제에서는 `tenEighty`라는 새로운 상수가 선언되고, `VideoMode` 클래스의 새 인스턴스에 할당됩니다.

- This video mode is configured with a copy of the HD resolution (1920 by 1080 pixels) from earlier, set to be interlaced, given a name of "1080i," and a frame rate of 25.0 frames per second.  
- 이 비디오 모드는 이전의 HD 해상도(1920 x 1080 픽셀)의 복사본으로 구성되며, 인터레이스로 설정되고, "1080i"라는 이름과 초당 25.0 프레임의 프레임률로 설정됩니다.

- Next, `tenEighty` is assigned to a new constant called `alsoTenEighty`, and the frame rate of `alsoTenEighty` is modified:  
- 다음으로, `tenEighty`는 `alsoTenEighty`라는 새로운 상수에 할당되고, `alsoTenEighty`의 프레임률이 수정됩니다:

- ```swift
- let alsoTenEighty = tenEighty
- alsoTenEighty.frameRate = 30.0
- ```

- Because classes are reference types, both `tenEighty` and `alsoTenEighty` actually refer to the same `VideoMode` instance.  
- 클래스가 참조 타입이기 때문에, `tenEighty`와 `alsoTenEighty`는 실제로 동일한 `VideoMode` 인스턴스를 참조합니다.

- Essentially, they are two different names for the same single instance.  
- 본질적으로, 그들은 같은 단일 인스턴스의 두 가지 다른 이름입니다.

- Checking the `frameRate` property of `tenEighty` correctly reports the new frame rate of 30.0 from the underlying `VideoMode` instance:  
- `tenEighty`의 `frameRate` 속성을 확인하면 기본 `VideoMode` 인스턴스에서 새로운 프레임률 30.0을 올바르게 보고합니다:

- ```swift
- print("The frameRate property of tenEighty is now \(tenEighty.frameRate)")
- // Prints "The frameRate property of tenEighty is now 30.0"
- ```

- This example also illustrates how reference types can be more challenging to manage.  
- 이 예시는 또한 참조 타입이 관리하기 더 어려울 수 있다는 것을 보여줍니다.

- If `tenEighty` and `alsoTenEighty` were far apart in your code, it might be difficult to track all the places where the video mode is modified.  
- `tenEighty`와 `alsoTenEighty`가 코드에서 멀리 떨어져 있다면, 비디오 모드가 수정된 모든 장소를 추적하기 어려울 수 있습니다.

- When you use `tenEighty`, you also have to consider code that uses `alsoTenEighty`, and vice versa.  
- `tenEighty`를 사용할 때는 `alsoTenEighty`를 사용하는 코드도 고려해야 하며, 그 반대의 경우도 마찬가지입니다.

- In contrast, value types are easier to reason about because all the code that interacts with the same value is closely located in

-  your source files.  
- 반면, 값 타입은 동일한 값을 다루는 모든 코드가 소스 파일 내에서 가까이 위치하기 때문에 이해하기 쉽습니다.

- Note that both `tenEighty` and `alsoTenEighty` are declared as constants, not variables.  
- `tenEighty`와 `alsoTenEighty`는 변수가 아니라 상수로 선언되었다는 점을 주목하세요.

- However, you can still change `tenEighty.frameRate` and `alsoTenEighty.frameRate` because the values of the constants themselves do not change.  
- 그러나 상수 자체의 값은 변경되지 않기 때문에 `tenEighty.frameRate`와 `alsoTenEighty.frameRate`를 변경할 수 있습니다.

- `tenEighty` and `alsoTenEighty` do not "store" the `VideoMode` instance; instead, they both refer to a `VideoMode` instance behind the scenes.  
- `tenEighty`와 `alsoTenEighty`는 `VideoMode` 인스턴스를 "저장"하지 않습니다; 대신, 그들은 모두 내부적으로 `VideoMode` 인스턴스를 참조합니다.

- It is the `frameRate` property of the underlying `VideoMode` instance that is modified, not the values of the constant references to that `VideoMode`.  
- 수정되는 것은 `VideoMode`에 대한 상수 참조의 값이 아니라 기본 `VideoMode` 인스턴스의 `frameRate` 속성입니다.

