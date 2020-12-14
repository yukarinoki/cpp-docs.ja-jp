---
description: '詳細情報: 致命的なエラー C1016'
title: 致命的なエラー C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: e0f9a887c42c7006a31124446021ebee54225984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262413"
---
# <a name="fatal-error-c1016"></a>致命的なエラー C1016

\#ifdef で識別子 # ifndef が必要です。

条件付きコンパイル ディレクティブ ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) または `#ifndef`) に、評価する識別子が指定されていません。 このエラーを解決するには、識別子を指定してください。

次の例では C1016 が生成されます。

```cpp
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

考えられる解決策:

```cpp
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```
