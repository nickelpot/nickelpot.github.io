---
layout: post
title: "[Swift 5 Beta] 02.00. A Swift Tour"
description: 
modified: 2019-03-09
tags: [Swift5, translation]
image:
  path: /images/title-background-4.jpg
  feature: title-background-4.jpg
  credit: nickelpot
  creditlink: https://nickelpot.github.io
---

## Swift 여행 시작하기

전통적인 제안은 새 언어를 사용한 첫 프로그램으로 화면에 "Hello, world!"를 출력하는 것입니다. Swift는 다음과 같이 간단하게 출력할 수 있습니다.

```swift
print("Hello, world!")
// Prints "Hello, world!"
```

만약 여러분이 C 언어나 Objective-C 언어로 코딩 해 본 적이 있다면, 이 문법은 여러분에게 익숙 할 것입니다—Swift에서는 이 것이 프로그램의 전부입니다. 입출력이나 문자열 처리를 위해 별개의 라이브러리를 추가 할 필요가 없습니다. 전역 범위에서 작성된 코드는 프로그램의 진입점이 되므로 `main()` 함수 역시 Swift에서는 필요하지 않습니다. 또한 여러분은 매 문장의 끝 마다 세미콜론 `;`을 쓰지 않아도 됩니다.

이 여정은 다양한 프로그래밍 작업을 보여줌으로써 Swift로 코딩을 시작하기 위한 여러분께 충분한 정보를 제공합니다. 만약 여러분이 일부분을 이해하지 못한다 하더라도 걱정하지 마세요—
이 여정에서 소개되는 모든 내용은 이 책의 나머지 부분에서 더 자세하게 다루고 있습니다.

**NOTE** <br><br> Xcode가 설치 된 Mac, 또는 Swift Playgrounds가 설치 된 iPad에서 이 장을 열 수 있습니다. Playgrounds를 통해 여러분은 코드 목록을 편집하고 결과를 즉시 볼 수 있습니다.
{: .note}

이 글은 2019년 1월 24일 출간 된 The Swift Programming Language (Swift 5 Beta)를 직접 번역한 글입니다. Dictionary 앱, Google, Google 번역기의 도움으로 작성되었으며 오역 및 오탈자에 대한 피드백은 언제든지 환영합니다. <br><br> This article is a Korean translation of The Swift Programming Language (Swift 5 Beta), published 24 January, 2019. It is written with the help of Dictionary app, Google, and Google Translator. Feedback on mistranslation and typographical errors is always welcome. <br><br><a rel="cc:attributionURL" property="cc:attributionName" href="https://itunes.apple.com/kr/book/the-swift-programming-language-swift-5-beta/id1002622538?l=en&mt=11">Read The Swift Programming Language (Swift 5 Beta)</a>
{: .notice}
