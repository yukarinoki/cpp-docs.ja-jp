---
title: 致命的なエラー C1016 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1016
dev_langs:
- C++
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72da7f9413724fe83352e888eff8b5e577fb0eda
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052258"
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