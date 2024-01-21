## Structures and Classes (구조체와 클래스)


### Model custom types that encapsulate data
데이터를 캡슐화하는 사용자 정의 타입 모델링

Structures and classes are general-purpose, flexible constructs  
구조체와 클래스는 범용적이고 유연한 구조입니다.

that become the building blocks of your program’s code.  
그것들은 프로그램 코드의 구성 요소가 됩니다.

You define properties and methods  
속성과 메서드를 정의합니다

to add functionality to your structures and classes  
이것들은 구조체와 클래스에 기능을 추가하기 위함입니다.

using the same syntax you use to define constants, variables, and functions.  
상수, 변수, 함수를 정의할 때 사용하는 문법을 그대로 사용합니다.

Unlike other programming languages,  
다른 프로그래밍 언어들과 달리,

Swift doesn’t require you to create separate interface and implementation files  
스위프트는 인터페이스와 구현을 위한 따로 떨어진 파일을 만들 필요가 없다.

for custom structures and classes.
여러분이 만든 구조체나 클래스를 위해서

In Swift, you define a structure or class in a single file,  
스위프트에서는 구조체나 클래스를 하나의 파일 안에서 정의합니다.

and the external interface to that class or structure is automatically made available for other code to use.  
그리고 그 구조체나 클래스의 외부 인터페이스는 다른 코드가 사용할 수 있도록 자동으로 제공됩니다.

<div style="display:block;background-color:#9ef0fb;padding:0.5rem;color:#000">
간단히 말해서, 스위프트에서는 여러분이 만든 구조체나 클래스를 하나의 파일로 만들면, 그것을 다른 코드에서 바로 사용할 수 있도록 스위프트가 알아서 처리해준다는 뜻이다. 다른 언어에서는 보통 두 개의 파일(인터페이스 파일과 구현 파일)을 만들어야 하지만 스위프트에서는 그럴 필요가 없다.
</div><br>

> **Note**
>
> <b>An instance of a class is traditionally known as an *object*.</b>  
클래스의 인스턴스는 전통적으로 객체라고 알려져 있습니다.  
<b>However, Swift structures and classes are much closer in functionality than in other languages,</b>  
하지만, 스위프트에서는 구조체와 클래스의 기능이 다른 언어들보다 훨씬 비슷합니다.
<b>and much of this chapter describes functionality that applies to instances of *either* a class or a structure type.</b>  
이 챕터에서 설명하는 많은 기능은 클래스나 구조체 타입의 인스턴스에 모두 적용됩니다.  
<b>Because of this, the more general term *instance* is used.</b>  
그래서 더 일반적인 용어인 '인스턴스'를 사용합니다.

<div style="display:block;background-color:#9ef0fb;padding:0.5rem;color:#000">
보통 '클래스의 인스턴스'를 '객체'라고 부르지만, 스위프트에서는 구조체와 클래스가 기능적으로 매우 비슷하기 때문에, 이들을 모두 '인스턴스'라고 부른다.
</div><br>

<br>

**Comparing Structures and Classes**  
구조체와 클래스 비교하기


Structures and classes in Swift have many things in common. Both can:  
스위프트의 구조체와 클래스는 많은 공통점을 갖고 있다. 둘 다 다음과 같은 일을 할 수 있다:

- Define properties to store values  
값 저장을 위해 속성을 정의할 수 있다.
- Define methods to provide functionality  
기능 제공을 위해 메서드를 정의할 수 있다.

- Define subscripts to provide access to their values using subscript syntax  
첨자 구문을 사용해서 그들의 값에 접근하기 위한 첨자를 정의할 수 있다.

- Define initializers to set up their initial state  
초기 상태를 설정하기 위해 초기화 함수를 정의할 수 있다.

- Be extended to expand their functionality beyond a default implementation  
기본 구현을 넘어서 기능을 확장할 수 있다.

- Conform to protocols to provide standard functionality of a certain kind  
특정 종류의 표준 기능을 제공하기 위해 프로토콜을 따를 수 있다.

<div style="display:block;background-color:#9ef0fb;padding:0.5rem;color:#000">
스위프트의 구조체와 클래스는 값을 저장하고, 기능을 제공하고, 값에 접근하고, 초기 상태를 만들고, 기능을 확장하며, 표준 기능을 제공하는 등 비슷한 방식으로 동작한다고 이해하면 된다.
</div><br>

For more information, see Properties, Methods, Subscripts, Initialization, Extensions, and Protocols.  
더 많은 정보를 원하시면, 속성(프로퍼티), 메소드, 서브스크립트, 초기화, 확장, 그리고 프로토콜에 관련된 내용을 참조하세요.

Classes have additional capabilities that structures don’t have:  
클래스는 구조체에 없는 몇 가지 추가적인 기능을 가지고 있다:

- Inheritance enables one class to inherit the characteristics of another.  
상속: 한 클래스가 다른 클래스의 특성을 물려받을 수 있다.

- Type casting enables you to check and interpret the type of a class instance at runtime.
타입 캐스팅: 실행 중에 클래스 인스턴스의 타입을 확인하고 해석할 수 있다.

- Deinitializers enable an instance of a class to free up any resources it has assigned.  
소멸자: 클래스 인스턴스가 할당한 자원을 해제할 수 있게 해준다.

- Reference counting allows more than one reference to a class instance.  
참조 카운팅: 하나의 클래스 인스턴스에 여러 참조가 가능하다.

<div style="display:block;background-color:#9ef0fb;padding:0.5rem;color:#000">
클래스에만 있는 이런 특별한 기능들 때문에, 클래스는 구조체보다 복잡한 상황에서 더 많이 사용된다.
</div><br>

For more information, see Inheritance, Type Casting, Deinitialization, and Automatic Reference Counting.  
더 많은 정보를 알고 싶으면 상속, 타입 캐스팅, 자동 참조 카운팅을 참고하세요.

The additional capabilities that classes support come at the cost of increased complexity.  
클래스가 지원하는 추가적인 기능들은 복잡성이 증가한다는 것을 의미한다.

As a general guideline, prefer structures because they’re easier to reason about, and use classes when they’re appropriate or necessary.
일반적인 지침으로는, 구조체는 이해하기 쉽기 때문에 구조체를 선호하고, 클래스는 적절하거나 필요할 때 사용하세요.

In practice, this means most of the custom types you define will be structures and enumerations.  
실제로 이것은 여러분이 정의하는 맞춤형 타입들은 대부분 구조체와 열거형이 될 것이라는 의미입니다.

For a more detailed comparison, see Choosing Between Structures and Classes.  
더 자세한 비교를 위해 구조체와 클래스 사이에서 선택하기를 참고하세요.

> **Note**  
Classes and actors share many of the same characteristics and behaviors.  
클래스와 액터는 많은 같은 특성과 행동을 공유합니다.  
For information about actors, see Concurrency.  
액터에 대한 정보는 동시성을 참조하세요.

<br>

**Definition Syntax**  
정의 문법

Structures and classes have a similar definition syntax.  
구조체와 클래스는 유사한 정의 문법을 가지고 있습니다.

You introduce structures with the `struct` keyword and classes with the `class` keyword.  
구조체는 struct 키워드로, 클래스는 'class' 키워드로 시작합니다.

Both place their entire definition within a pair of braces:  
둘 다 전체 정의를 중괄호 쌍 안에 넣습니다.

```swift
struct SomeStructure {
    // structure definition goes here
}

class SomeClass {
    // class definition goes here
}
```
> Note  
<b>Whenever you define a new structure or class, you define a new Swift type.</b>  
새로운 구조체나 클래스를 정의할 때마다, 새로운 스위프트 타입을 정의하는 것입니다.  
<b>Give types UpperCamelCase names (such as SomeStructure and SomeClass here) to match the capitalization of standard Swift types (such as String, Int, and Bool).</b>  
타입 이름에는 대문자로 시작하는 카멜 표기법을 사용하세요.(예 SomeStructure, SomeClass), 이는 스위프트의 표준 타입 이름 (예: String, Int, Bool)과 일치시키기 위함입니다.  
<b>Give properties and methods lowerCamelCase names (such as frameRate and incrementCount) to differentiate them from type names.</b>  
속성과 메소드 이름에는 소문자로 시작하는 카멜 표기법을 사용하세요 (예: frameRate, incrementCount), 이는 타입 이름과 구별하기 위함입니다.

Here’s an example of a structure definition and a class definition:

```swift
struct Resolution {
    var width = 0
    var height = 0
}

class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}
```

The example above defines a new structure called Resolution, to describe a pixel-based display resolution.  
위의 예는 픽셀 기반 디스플레이 해상도를 설명하기 위한 'Resolution'이라는 새로운 구조체를 정의합니다.  

This structure has two stored properties called width and height.  
이 구조체에는 width와 height라는 두 개의 저장 속성이 있습니다.

Stored properties are constants or variables that are bundled up and stored as part of the structure or class.  
저장 속성은 구조체나 클래스의 일부로 묶여 저장되는 상수 또는 변수입니다.

These two properties are inferred to be of type Int by setting them to an initial integer value of 0.  
이 두 속성은 초기 정수 값 0으로 설정함으로써 Int 타입으로 추론됩니다.

The example above also defines a new class called VideoMode, to describe a specific video mode for video display.  
위의 예에서는 비디오 디스플레이를 위한 특정 비디오 모드를 설명하기 위해 'VideoMode'라는 새로운 클래스를 정의합니다.

This class has four variable stored properties.  
이 클래스는 네 개의 변수 저장 속성을 가지고 있습니다.

The first, resolution, is initialized with a new Resolution structure instance, which infers a property type of Resolution.  
첫 번째 속성인 'resolution'은 'Resolution' 구조체의 새 인스턴스로 초기화되며, 이로 인해 속성 타입이 'Resolution'으로 추론됩니다.

For the other three properties, new VideoMode instances will be initialized with an interlaced setting of false (meaning “noninterlaced video”), a playback frame rate of 0.0, and an optional String value called name.  
나머지 세 가지 속성의 경우, 새로운 'VideoMode' 인스턴스는 'interlaced' 설정을 'false'(비인터레시으 비디오를 의미)로, 재생 프레임율을 '0.0'으로, 그리고 'name'이라는 선택적인(String?) 문자열 값으로 초기화됩니다.

The name property is automatically given a default value of nil, or “no name value”, because it’s of an optional type.  
'name' 속성은 선택적 타입이기 때문에 자동으로 기본값으로 'nil' 또는 "이름 값 없음"을 갖게 됩니다.

<br>

**Structure and Class Instances**  
구조체와 인스턴스

The Resolution structure definition and the VideoMode class definition only describe what a Resolution or VideoMode will look like.  
'Resolution' 구조체 정의와 'VideoMode' 클래스 정의는 'Resolution'이나 'VideoMode'가 어떤 모습일지에 대해서만 설명합니다.

They themselves don’t describe a specific resolution or video mode.  
그들 자체는 특정 해상도나 비디오 모드를 설명하지 않습니다.

To do that, you need to create an instance of the structure or class.  
그렇게 하려면, 구조체나 클래스의 인스턴스를 생성해야 합니다.

The syntax for creating instances is very similar for both structures and classes:  
구조체와 클래스의 인스턴스를 생성하는 문법은 매우 유사합니다:

```swift
let someResolution = Resolution()
let someVideoMode = VideoMode()
```

Structures and classes both use initializer syntax for new instances.  
구조체와 클래스 모두 새 인스턴스에 대한 초기화 문법을 사용합니다.

The simplest form of initializer syntax uses the type name of the class or structure followed by empty parentheses, such as `Resolution()` or `VideoMode()`.  
가장 간단한 초기화 문법 형태는 클래스나 구조체의 타입 이름 다음에 빈 괄호를 사용하는 것으로, 예를 들어 `Resolution()` 또는 `VideoMode()`와 같습니다.

This creates a new instance of the class or structure, with any properties initialized to their default values.  
이 방법으로 클래스나 구조체의 새로운 인스턴스를 생성하며, 모든 속성은 기본값으로 초기화 됩니다.

Class and structure initialization is described in more detail in Initialization.  
클래스와 구조체의 초기화는 '초기화(Initialization)'에서 더 자세히 설명됩니다.

<br>

**Accessing Properties**  
속성 접근하기

You can access the properties of an instance using dot syntax.  
점 문법(dot syntax)을 사용하여 인스턴스의 속성에 접근할 수 있습니다.

In dot syntax, you write the property name immediately after the instance name, separated by a period (`.`), without any spaces:  
점 문법에서는 인스턴스 이름 뒤에 곧바로 속성 이름을 쓰고, 점(.)으로 구분하며, 사이에 공백은 넣지 않습니다:

```swift
print("The width of someResolution is \(someResolution.width)")
// Prints "The width of someResolution is 0"
```

In this example, someResolution.width refers to the width property of someResolution, and returns its default initial value of 0.  
이 예시에서 `someResolution.width`는 `someResolution`의 `width` 속성을 참조하고, 기본 초기값인 0을 반환합니다.

You can drill down into subproperties, such as the width property in the resolution property of a VideoMode:  
`VideoMode`의 `resolution` 속성 안에 있는 `width` 속성과 같은 하위 속성으로 들어가는 것도 가능합니다.

<div style="display:block;background-color:#9ef0fb;padding:0.5rem;color:#000">
`VideoMode`라는 비디오 설정을 저장하는 클래스가 있고, 그 안에 `resolution`이라는 화면 해상도를 나타내는 구조체가 있다. 이 `resolution` 구조체 안에는 `width`라는 너비를 나태는 값이 있다. 클래스의 속성에 접근할 때는 점(.)을 사용해서 `someVideoMode.resolution.width`라고 쓰면 된다. 이렇게 하면 `VideoMode`의 `resolution` 안에 있는 `width` 값을 볼 수 있다.
</div><br>

```swift
print("The width of someVideoMode is \(someVideoMode.resolution.width)")
// Prints "The width of someVideoMode is 0"
```

You can also use dot syntax to assign a new value to a variable property:  
당신은 또한 점 문법(dot syntax)을 사용해서, 변수 속성((variable property)에 새 값을 할당(assign)할 수 있습니다.

```swift
someVideoMode.resolution.width = 1280
print("The width of someVideoMode is now \(someVideoMode.resolution.width)")
// Prints "The width of someVideoMode is now 1280"
```

**Memberwise Initializers for Structure Types**  
구조체 타입을 위한 멤버별 초기화

All structures have an automatically generated memberwise initializer,
모든 구조체들은 자동으로 생성되는 멤버별 초기화기를 가지고 있다.

which you can use to initialize the member properties of new structure instances.  
새로운 구조체 인스턴스의 멤버 속성을 초기화하기 위해 사용할 수 있다.

Initial values for the properties of the new instance can be passed to the memberwise initializer by name:  
새 인스턴스의 속성을 위한 초기 값들은 이름에 의해 멤버별 초기화기에 전달될 수 있다.

```swift
let vga = Resolution(width: 640, height: 480)
```

Unlike structures, class instances don’t receive a default memberwise initializer.  
구조체와는 달리, 클래스 인스턴스는 기본 멤버별 초기화기를 받지 않습니다.

Initializers are described in more detail in Initialization.  
초기화기에 대한 자세한 설명은 `Initialization` 에서 볼 수 있다.

<br>

**Structures and Enumerations Are Value Types**  
구조체와 열거형은 값 타입이다.

A value type is a type whose value is copied when it’s assigned to a variable or constant, or when it’s passed to a function.  
값 타입은 그 값이 복사되는 변수나 상수에 할당될 때, 또는 함수에 전달될 때이다.


You’ve actually been using value types extensively throughout the previous chapters.  
사실, 당신은 이전 챕터에서 이미 값 타입을 많이 사용했다.

In fact, all of the basic types in Swift  
실제로, Swift의 모든 기본 타입들이

— integers, floating-point numbers, Booleans, strings, arrays, and dictionaries —  
정수, 부동 소수점 숫자, 불린, 문자열, 배열, 그리고 사전

are value types, and are implemented as structures behind the scenes.  
값 타입이며, 내부적으로 구조체를 구현되어 있습니다.

All structures and enumerations are value types in Swift.  
Swift에서 모든 구조체와 열거형은 값 타입입니다.

This means that any structure and enumeration instances you create  
이것은 당신이 만든 어떤 구조체나 열거형 인스턴스도

— and any value types they have as properties —  
그리고 그것들이 가진 모든 값 타입 속성도

are always copied when they’re passed around in your code.  
코드에서 전달될 때는 항상 복사된다는 것을 의미합니다.

> <b>Note</b>  
<b>Collections defined by the Swift standard library</b>   
Swift 표준 라이브러리에 의해 정의된 컬렉션들  
<b>like arrays, dictionaries, and strings</b>   
배열, 사전 문자열 같은  
<b>use an optimization to reduce the performance cost of copying.</b>   
복사의 성능 비용을 줄이기 위한 최적화를 사용합니다.  
<b>Instead of making a copy immediately, these collections share the memory where the elements are stored</b>   
바로 복사를 하는 대신, 이 컬렉션들은 원소가 저장되는 메모리를 공유한다.  
<b>between the original instance and any copies.</b>   
원본 인스턴스와 복사본들 사이에서  
<b>If one of the copies of the collection is modified,</b>   
만약 컬렉션의 복사본 중 하나가 수정되면,  
<b>the elements are copied just before the modification.</b>   
수정 바로 직전에 원소들이 복사된다.  
<b>The behavior you see in your code is always as if a copy took place immediately.</b>   
코드에서 보이는 행동은 항상 마치 즉시 복사가 일어난 것처럼 보인다.

<br>

Consider this example, which uses the Resolution structure from the previous example:  
이 예제를 생각해 보아라, 이것은 이전 예제에서 Resolution 구조체를 사용한다.

```swift
let hd = Resolution(width: 1920, height: 1080)
var cinema = hd
```

This example declares a constant called hd and sets it to a Resolution instance initialized with the width and height of full HD video (1920 pixels wide by 1080 pixels high).  
이 예제는 hd라는 상수를 선언한다 그리고 그것을 Resolution 인스턴스로 설정한다. 풀 HD 비디오의 너비와 높이로 초기화된(너비 1920 픽셀, 높이 1080 픽셀).

It then declares a variable called cinema and sets it to the current value of hd.  
그런 다음 cinema라는 변수를 선언한다. 그리고 그것을 hd의 현재 값으로 설정한다.

Because Resolution is a structure, a copy of the existing instance is made, and this new copy is assigned to cinema.  
Resolution의 구조체이기 때문에, 기존 인스턴스의 복사본이 만들어진다, 그리고 이 새로운 복사본이 cinema에 할당된다.

Even though hd and cinema now have the same width and height, they’re two completely different instances behind the scenes.  
hd와 cinema가 이제 같은 너비와 높이를 가지고 있지만, 내부적으로는 완전히 다른 두 개의 인스턴스이다.

Next, the width property of cinema is amended  
다음으로, 영화관의 너비 속성이 변경된다.

to be the width of the slightly wider 2K standard  
조금 더 넓은 2K 표준의 너비가 되도록

used for digital cinema projection  
디지털 영화 상영에 사용된다.

(2048 pixels wide and 1080 pixels high):  
(가로는 2048픽셀이고 세로는 1080 픽셀이다.

```swift
cinema.width = 2048
```

Checking the width property of cinema shows  
영화관의 너비 속성을 확인해보면

that it has indeed changed to be 2048:  
그것은 실제로 2048로 변경되었다.

```swift
print("cinema is now \(cinema.width) pixels wide")
// Prints "cinema is now 2048 pixels wide"
```

However, the width property of the original hd instance still has the old value of 1920:  
그러나 원래 hd 인스턴의 너비 속성은 여전히 이전의 값인 1920을 가지고 있다.

```swift
print("hd is still \(hd.width) pixels wide")
// Prints "hd is still 1920 pixels wide"
```

When cinema was given the current value of hd,  
영화관에 현재 hd의 값을 줬을 때,

the values stored in hd were copied into the new cinema instance.  
hd에 저장된 값은 새 영화관 인스턴스로 복사되었다.

The end result was two completely separate instances that contained the same numeric values.  
결과적으로 숫자 값이 같지만 완전히 분리된 두 인스턴스가 만들어졌다.

However, because they’re separate instances,  
그러나, 두 인스턴스가 분리되어 있기 때문에,

setting the width of cinema to 2048 doesn’t affect the width stored in hd.  
영화관의 너비를 2048로 설정해도 hd에 저장된 너비에는 영향을 주지 않는다.

The same behavior applies to enumerations:  
열거형에도 동일한 행동이 적용된다.

```swift
enum CompassPoint {
    case north, south, east, west
    mutating func turnNorth() {
        self = .north
    }
}

var currentDirection = CompassPoint.west
let rememberedDirection = currentDirection
currentDirection.turnNorth()

print("The current direction is \(currentDirection)")
print("The remembered direction is \(rememberedDirection)")
// Prints "The current direction is north"
// Prints "The remembered direction is west"
```

When rememberedDirection is assigned the value of currentDirection,  
`rememberedDirection`에 `currentDirection`의 값이 할당될 때,

it’s actually set to a copy of that value.  
실제로 그 값의 복사본으로 설정된다.

Changing the value of currentDirection thereafter  
그 이후에 currentDirection의 값을 변경해도

doesn’t affect the copy of the original value that was stored in rememberedDirection.  
rememberedDirection에 저장된 원래 값의 복사본에는 영향을 주지 않는다.

---
