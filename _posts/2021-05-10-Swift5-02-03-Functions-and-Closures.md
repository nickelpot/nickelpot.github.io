---
layout: post
title: "[Swift 5.4] 02.03. Functions and Closures"
description: 
modified: 2021-05-10
tags: [Swift5, translation]
image:
  path: /images/title-background-4.jpg
  feature: title-background-4.jpg
  credit: nickelpot
  creditlink: https://nickelpot.github.io
---

## Swift 여행 시작하기
### 함수와 클로저(Closures)

`func`를 사용하여 함수를 정의합니다. 괄호 안의 인수 목록과 함께 함수의 이름을 사용하여 함수를 호출합니다. `->`를 사용하여 매개변수의 이름과 유형을 함수의 리턴 유형과 분리합니다.

```swift
func greet(person: String, day: String) -> String {
  return "Hello \(person), today is \(day)."
}
greet(person: "Bob", day: "Tuesday")
```

**EXPERIMENT** <br><br> `day` 매개변수를 지워보세요. 인사말에 오늘의 스페셜 런치메뉴를 알리는 매개변수를 추가하세요.
{: .note}

기본적으로 함수는 매개변수 이름을 인수의 레이블로 사용합니다. 매개변수 이름 앞에 사용자 정의 인수 레이블을 사용하거나 `_`를 사용하여 인수 레이블을 사용하지 않을 수도 있습니다.

```swift
func greet(_ person: String, on day: String) -> String {
  return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

튜플을 사용하여 복합적인 값을 만들 수 있습니다-예를 들어, 함수에서 다중 값을 변환하는 경우. 튜플의 요소는 이름이나 번호로 참조할 수 있습니다.

```swift
func calculateStatistics(scores: [Int]) -> (min: Int, max: Int, sum: Int) {
  var min = scores[0]
  var max = scores[0]
  var sum = 0

  for score in scores {
    if score > max {
      max = score
    } else if score < min {
      min = score
    }
    sum += score
  }

  return (min, max, sum)
}
let statistics = calculateStatistics(scores: [5, 3, 100, 3, 9])
print(statistics.sum)
// Prints "120"
print(statistics.2)
// Prints "120"
```

함수는 하나로 묶을 수 있습니다. 하나로 묶인 함수는 함수 외부에서 변수로 선언하여 접근 할 수 있습니다. 함수를 사용하여 길거나 복잡한 코드를 간단하게 구성 할 수 있습니다.

```swift
func returnFifteen() -> Int {
  var y = 10
  func add() {
    y += 5
  }
  add()
  return y
}
returnFifteen()
```

함수는 최고급 유형입니다. 이것은 함수가 다른 함수를 값으로 반환 할 수 있음을 의미합니다.

```swift
func makeIncrementer() -> ((Int) -> Int) {
  func addOne(number: Int) -> Int {
    return 1 + number
  }
  return addOne
}
var increment = makeIncrementer()
increment(7)
```

함수는 다른 함수를 인수로 취할 수도 있습니다.

```swift
func havAnyMatches(list: [Int], condition: (Int) -> Bool) -> Bool {
  for item in list {
    if condition(item){
      return true
    }
  }
  return false
}
func lessThanTen(number: Int) -> Bool {
  return number < 10
}
var numbers = [20, 19, 7, 12]
hasAnyMatches(list: numbers, condition: lessThanTen)
```

함수는 클로저(Closures)의 특별한 경우입니다: 나중에 호출할 수 있는 일련의 코드 블록입니다. 클로저의 코드는 클로저가 실행될 때 다른 범위에 있더라도 클로저가 생성 된 범위에서 사용 가능한 변수 및 함수와 같은 항목에 액세스 할 수 있습니다-여러분은 이미 하나로 묶인 함수를 예제로 보았습니다. 중괄호({})로 코드를 묶어 이름없이 클로저를 작성할 수 있습니다. `in`을 사용하여 인수를 분리하고 본문에서 유형을 반환합니다.

```swift
numbers.map({ (number: Int) -> Int in
  let result = 3 * number
  return result
})
```

**EXPERIMENT** <br><br> 모든 홀수에 대해 0을 반환하는 클로저를 만드세요.
{: .note}

더 간단하게 클로저를 사용할 수 있는 여러가지 방법이 있습니다. 대리자에 대한 콜백과 같이 클로저의 유형을 이미 알고 있다면, 매개변수의 유형이나 반환 유형, 또는 둘 다를 생략할 수 있습니다. 단일 명령문 클로저는 암시적으로 유일한 명령문의 값을 반환합니다. 

```swift
let mappedNumbers = numbers.map({ number in 3 * number })
print(mappedNumbers)
// Prints "[60, 57, 21, 36]"
```

이름 대신 숫자로 매개변수를 참조 할 수 있습니다-이 접근 방식은 매우 짧은 클로저에 특히 유용합니다. 함수의 마지막 인수로 전달 된 클로저는 괄호 바로 뒤에 나타날 수 있습니다. 클로저가 함수에 대한 유일한 인수 인 경우, 괄호를 완전히 생략 할 수 있습니다.

```swift
let sortedNumbers = numbers.sorted { $0 > $1 }
print(sortedNumbers)
// Prints "[20, 19, 12, 7]"
```

이 글은 The Swift Programming Language: Swift 5.4 Edition을 직접 번역한 글입니다. Dictionary 앱, Google, Google 번역기의 도움으로 작성되었으며 오역 및 오탈자에 대한 피드백은 언제든지 환영합니다. <br><br> This article is a Korean translation of The Swift Programming Language: Swift 5.4 Edition. It is written with the help of Dictionary app, Google, and Google Translator. Feedback on mistranslation and typographical errors is always welcome. <br><br><a rel="cc:attributionURL" property="cc:attributionName" href="https://books.apple.com/kr/book/the-swift-programming-language-swift-5-4/id881256329?l=en">Read The Swift Programming Language: Swift 5.4 Edition</a>
{: .notice}
