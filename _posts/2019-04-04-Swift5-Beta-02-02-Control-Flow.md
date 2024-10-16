---
layout: post
title: "[Swift 5 Beta] 02.02. Control Flow"
description: 
modified: 2019-04-05
tags: [Swift5, translation]
image:
  path: /images/title-background-4.jpg
  feature: title-background-4.jpg
  credit: nickelpot
  creditlink: https://nickelpot.github.io
---

## Swift 여행 시작하기
### 흐름 제어

`if`와 `switch`를 사용하여 조건문을, `for-in`, `while`, 그리고 `repeat-while`을 사용하여 반복문을 만들 수 있습니다. 조건문과 반복문의 조건식에 소괄호 `()`를 사용하는 것은 자유입니다. 조건문과 반복문의 내용에는 반드시 중괄호 `{}`가 필요합니다.

```swift
let individualScores = [75, 43, 103, 87, 12]
var teamScore = 0
for score in individualScores {
    if score > 50 {
        teamScore += 3
    } else {
        teamScore += 1
    }
}
print(teamScore)
// Prints "11"
```

`if`문의 조건식에는 Boolean 표현이 필요합니다--이것이 의미하는 바는 `if score { ... }`는 에러가 발생하며, 암시적으로 0과 비교하는것이 아닙니다.

여러분은 `if`문과 `let`을 함께 사용하여 누락된 값을 처리할 수 있습니다. 이 값을 옵셔널(Optional)이라고 합니다. 옵셔널(Optional)은 값을 포함하거나 `nil`로 값이 없음을 표현할 수 있습니다. 타입명에 물음표(`?`)의 사용하여 옵셔널(Optional)을 만들 수 있습니다.

```swift
var optionalString: String? = "Hello"
print(optionalString == nil)
// Prints "false"

var optionalName: String? = "John Appleseed"
var greeting = "Hello!"
if let name = optionalName {
  greeting = "Hello, \(name)"
}
```

**EXPERIMENT** <br><br> `optionalName`을 `nil`로 바꿔보세요. greeting의 결과값이 어떻게 출력되나요? 만약`optionalName`가 `nil` 값이 나온다면 `else`문을 추가하여 greeting을 바꿔 보세요.
{: .note}

만약 옵셔널(Optional)의 값이 `nil`이면, 조건식은 `false`가 되어 중괄호 `{}` 안의 코드는 실행하지 않습니다. 그렇지 않으면 언래핑으로 할당 된 `let` 뒤의 상수가 옵셔널(Optional) 값이 되고, 언래핑된 값은 코드 안에서 사용할 수 있습니다.

옵셔널(Optional)값을 다룰 수 있는 다른 방법으로는 `??` 연산자를 사용하여 기본값을 제공하는 것입니다. 만약 옵셔널(Optional)값이 없으면, 대신 기본값을 사용하게 됩니다.

```swift
let nickName: String? = nil
let fullName: String = "John Appleseed"
let informalGreeting = "Hi \(nickName ?? fullName)"
```

`switch`문에서는 모든 종류의 데이터와 다양한 비교 연산자를 사용할 수 있습니다--정수나 등식에 국한되지 않습니다.

```swift
let vegetable = "red pepper"
switch vegetable {
case "celery":
  print("Add some raisins and make ants on a log.")
case "cucumber", "watercress":
  print("That would make a good tea sandwich.")
case let x where x.hasSuffix("pepper"):
  print("Is it a spicy \(x)?")
default:
  print("Everyting tastes good in soup.")
}
// Prints "Is it a spicy red pepper?"
```

**EXPERIMENT** <br><br> default 조건을 제거해 보세요. 어떤 에러가 발생하나요?
{: .note}

`let`이 어떻게 패턴 안에서 일치하는 상수값을 얻는지 주목하세요.

`switch`문의 `case`에서 값을 얻고 코드를 빠져나온 뒤, 프로그램의 `switch`문은 끝납니다. 코드를 빠져나오면 다음 `case`는 실행되지 않으며, 이것은 명시적으로 `switch`문 내의 모든 `case` 코드에 break를 쓸 필요가 없습니다.

여러분은 `for-in`과 딕셔너리(Dictionary)의 각 키-값의 이름을 사용하여 반복문을 만들 수 있습니다. 정렬되지 않은 딕셔너리(Dictionary)는 임의의 순서로 반복문에서 사용됩니다.

```swift
let interstingNumbers = [
  "Prime": [2, 3, 5, 7, 11, 13],
  "Fibonacci": [1, 1, 2, 3, 5, 8],
  "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (kind, numbers) in interestingNumbers {
  for number in numbers {
    if number > largest {
      largest = number
    }
  }
}
print(largest)
// Prints "25"
```

**EXPERIMENT** <br><br> 변수를 추가하여 어느 종류의 값이 가장 큰 지, 그것이 제일 큰 값인지 추적해 보세요.
{: .note}

조건이 바뀔 때 까지 `whil`을 사용하여 코드를 반복할 수 있습니다. 조건은 반복문의 끝에 위치할 수 있으며, 적어도 한 번은 실행되도록 할 수 있습니다.

```swift
var n = 2
while n < 100 {
  n *= 2
}
print(n)
// Prints "128"

var m = 2
repeat {
  m *= 2
} while m < 100
print(m)
// Prints "128"
```

여러분은 `..<`를 사용하여 반복문 내 조건값의 범위를 설정할 수 있습니다.

```swift
var total = 0
for i in 0..<4 {
  total += 1
}
print(total)
// Prints "6"
```

`..<`는 조건값 미만의 범위를, `...`는 두 조건값과 그 사이를 포함하는 값의 범위를 나타냅니다.

이 글은 2019년 1월 24일 출간 된 The Swift Programming Language (Swift 5 Beta)를 직접 번역한 글입니다. Dictionary 앱, Google, Google 번역기의 도움으로 작성되었으며 오역 및 오탈자에 대한 피드백은 언제든지 환영합니다. <br><br> This article is a Korean translation of The Swift Programming Language (Swift 5 Beta), published 24 January, 2019. It is written with the help of Dictionary app, Google, and Google Translator. Feedback on mistranslation and typographical errors is always welcome. <br><br><a rel="cc:attributionURL" property="cc:attributionName" href="https://itunes.apple.com/kr/book/the-swift-programming-language-swift-5-beta/id1002622538?l=en&mt=11">Read The Swift Programming Language (Swift 5 Beta)</a>
{: .notice}
