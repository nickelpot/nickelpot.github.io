---
layout: post
title: "[Swift 5 Beta] 01. Version Compatibility"
description: 
modified: 2019-03-09
tags: [Swift5, translation]
image:
  path: /images/title-background-4.jpg
  feature: title-background-4.jpg
  credit: nickelpot
  creditlink: https://nickelpot.github.io
---

## 버전 호환성

이 책은 Swift 5에 대하여 기술되어 있으며, Swift 5는 Xcode 10.2에 포함되어 있는 기본 버전입니다. 여러분은 빌드 타겟으로 Swift 5, Swift 4.2, 그리고 Swift 4로 작성된 코드 모두 Xcode 10.2에서 사용할 수 있습니다.

여러분이 Swift 4와 Swift 4.2로 작성된 코드를 Xcode 10.2로 빌드하려 할 때 Swift 5의 기능을 사용할 수 있습니다. 이는 아래 변경 사항은 Swift 5 코드에서만 적용됨을 의미합니다:

* `try?`는 이미 옵셔널(Optionl)을 반환하는 표현식에 추가 옵셔널(Optionl)을 적용할 수 없습니다.
* 큰 범위 정수의 리터럴(Literal) 초기화를 표현할 때 올바른 정수 유형으로 추정됩니다. 예를 들어, `UInt64(0xffff_ffff_ffff_ffff)`는 오버플로우로 처리되기 보다 올바른 정수 유형으로 추정됩니다.

Swift 5를 타겟으로 작성된 코드는 Swift 4.2, Swift 4의 타겟에도 의존 가능하며, 그 반대도 가능합니다. 말인즉슨, 만약 여러분이 다중 프레임워크로 구성된 대규모 프로젝트를 수행 하더라도 Swift 4에서 Swift 5로 각각 마이그레이션 할 수 있습니다.

이 글은 2019년 1월 24일 출간 된 The Swift Programming Language (Swift 5 Beta)를 직접 번역한 글입니다. Dictionary 앱, Google, Google 번역기의 도움으로 작성되었으며 오역 및 오탈자에 대한 피드백은 언제든지 환영합니다. <br><br> This article is a Korean translation of The Swift Programming Language (Swift 5 Beta), published 24 January, 2019. It is written with the help of Dictionary app, Google, and Google Translator. Feedback on mistranslation and typographical errors is always welcome. <br><br><a rel="cc:attributionURL" property="cc:attributionName" href="https://itunes.apple.com/kr/book/the-swift-programming-language-swift-5-beta/id1002622538?l=en&mt=11">Read The Swift Programming Language (Swift 5 Beta)</a>
{: .notice}
