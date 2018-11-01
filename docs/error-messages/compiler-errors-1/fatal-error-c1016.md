---
title: 致命的なエラー C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: 7463c6962817716611f3571e073712f374773fa7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566037"
---
# <a name="fatal-error-c1016"></a>致命的なエラー C1016

\#ifdef は #ifndef 識別子が必要です。

条件付きコンパイル ディレクティブ ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) または `#ifndef`) に、評価する識別子が指定されていません。 このエラーを解決するには、識別子を指定してください。

次の例では C1016 が生成されます。

```
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

考えられる解決方法:

```
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```