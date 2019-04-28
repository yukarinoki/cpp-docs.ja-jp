---
title: __noop
ms.date: 11/04/2016
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 674b5170dd2bba7038dfe11af906e31540acd993
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262984"
---
# <a name="noop"></a>__noop

**Microsoft 固有の仕様**

`__noop`組み込み関数を無視することを指定し、引数リストを解析できませんが、引数のコードを生成できません。 可変個の引数を取るグローバル デバッグ関数で使用するものでは。

コンパイラに変換、`__noop`コンパイル時に 0 に固有です。

## <a name="example"></a>例

次のコードは、使用する方法を示しています。`__noop`します。

```
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[キーワード](../cpp/keywords-cpp.md)