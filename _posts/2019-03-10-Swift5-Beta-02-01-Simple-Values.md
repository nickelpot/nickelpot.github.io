---
layout: post
title: "[Swift 5 Beta] 02.01. Simple Values"
description: 
modified: 2019-03-10
tags: [Swift5, translation]
image:
  path: /images/title-background-4.jpg
  feature: title-background-4.jpg
  credit: nickelpot
  creditlink: https://nickelpot.github.io
---

## Swift 여행 시작하기
### 기본값

상수를 만들 때는 `let`을, 변수를 만들 때는 `var`를 사용합니다. 상수는 컴파일 시 값은 몰라도 되지만, 여러분은 반드시 한 번은 값을 할당해 줘야만 합니다. 여러분은 상수를 사용하여 값의 이름을 한 번만 할당해도 여러 곳에서 사용할 수 있습니다.

```swift
var myVariable = 42
myVariable = 50
let myConstant = 42
```

상수와 변수는 여러분이 할당하려는 값과 같은 타입이어야 합니다. 그러나 항상 타입명을 입력해야 하는 것은 아닙니다. 여러분이 상수 또는 변수를 생성 할 때 값을 할당하면 컴파일러가 이들의 타입을 추론합니다. 아래의 예제에서, 컴파일러는 `myVariable`의 초기 값이 정수이기 때문에 이를 정수로 추론합니다.

만약 초기 값이 타입 추론을 위한 충분한 정보를 제공하지 않는다면 (또는 만약 초기 값이 없다면), 콜론 `:`을 사용하여 변수명과 함께 타입을 명시해야 합니다.

```swift
let implicitInteger = 70
let implicitDouble = 70.0
let explicitDouble: Double = 70
```

**EXPERIMENT** <br><br> `4`의 값을 가진 `Float` 타입의 상수를 선언 해 봅시다.
{: .note}

값은 은연 중에 다른 타입으로 변환되지 않습니다. 만약 여러분이 값을 다른 타입으로 바꾸고 싶다면, 원하는 타입을 아래와 같이 명시해야 합니다.

```swift
let label = "The width is "
let width = 94
let widthLabel = label + String(width)
```

**EXPERIMENT** <br><br> 마지막 세 번째 줄에서 `String`을 지워 봅시다. 오류 없이 동작 합니까?
{: .note}

문자열에 값을 포함하는 더 간단한 방법이 있습니다: 백슬래시 `\`를 입력한 다음 소괄호 `()` 안에 값을 입력합니다. 예를 들어:

```swift
let apples = 3
let oranges = 5
let appleSummary = "I have \(apples) apples."
let fruitSummary = "I have \(apples + oranges) pieces of fruit."
```
**EXPERIMENT** <br><br> `\()`를 사용하여 부동소수점 계산식을 포함하는 문자열과 누군가의 이름을 포함하는 인사말을 작성 해 봅시다.
{: .note}

여러 줄의 문자열을 입력하고 싶다면 쌍따옴표 세 개 `"""`를 사용합니다. 세 개의 쌍따옴표로 묶은 문자열은 들여쓰기가 제거됩니다. 예를 들어:

```swift
let quotation = """
Even though there's whitespace to the left,
the actual lines aren't indented.
Except for this line.
Doublt quotes can appear without being excaped.

I still have \(apples + oranges) pieces of fruit.
  """
```

배열과 딕셔너리(Dictionary)의 생성에는 대괄호 `[]`를 사용합니다. 원소에 접근하기 위해서는 인덱스(Index)와 키(Key)를 대괄호 안에 입력합니다. 마지막 원소 뒤에도 쉼표 `,`를 사용할 수 있습니다.

```swift
var shoppingList = ["catfish", "water", "tulips"]
shoppingList[1] = "bottle of water"

var occupations = [
  "Malcolm": "Captain",
  "Keylee": "Mechanic",
]
occupations["Jayne"] = "Public Relations"
```

여러분이 배열에서 새 원소를 추가 할 때 배열은 자동으로 커집니다.

```swift
shoppingList.append("blue paint")
print(shoppingList)
```

빈 배열 또는 딕셔너리(Dictionary)를 생성 할 때, 초기화 구문을 사용합니다.

```swift
let emptyArray = [String]()
let emptyDictionary = [String: Float]()
```

만약 타입 추론이 가능하다면, 여러분은 빈 배열에 `[]`를, 빈 딕셔너리(Dictionary)에 `[:]`를 입력할 수 있습니다—예를 들어, 여러분이 변수에 새로운 값을 설정하거나 함수에 인수를 전달 할 때 사용할 수 있습니다.

```swift
shoppingList = []
occupations = [:]
```

이 글은 2019년 1월 24일 출간 된 The Swift Programming Language (Swift 5 Beta)를 직접 번역한 글입니다. Dictionary 앱, Google, Google 번역기의 도움으로 작성되었으며 오역 및 오탈자에 대한 피드백은 언제든지 환영합니다. <br><br> This article is a Korean translation of The Swift Programming Language (Swift 5 Beta), published 24 January, 2019. It is written with the help of Dictionary app, Google, and Google Translator. Feedback on mistranslation and typographical errors is always welcome. <br><br><a rel="cc:attributionURL" property="cc:attributionName" href="https://itunes.apple.com/kr/book/the-swift-programming-language-swift-5-beta/id1002622538?l=en&mt=11">Read The Swift Programming Language (Swift 5 Beta)</a>
{: .notice}
