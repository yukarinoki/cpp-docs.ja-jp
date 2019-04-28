---
title: コンパイラ エラー C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: c23f17483925f25468214165fb459db577e576fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209011"
---
# <a name="compiler-error-c2006"></a>コンパイラ エラー C2006

'directive' が 'token' が見つかりません、ファイル名が必要です。

などのディレクティブ[#include](../../preprocessor/hash-include-directive-c-cpp.md)または[#import](../../preprocessor/hash-import-directive-cpp.md)ファイル名が必要です。 エラーを解決することを確認します*トークン*が有効なファイル名。 また、二重引用符や山かっこでファイル名を配置します。

次の例では、C2006 が生成されます。

```
// C2006.cpp
#include stdio.h   // C2006
```

考えられる解決方法:

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```