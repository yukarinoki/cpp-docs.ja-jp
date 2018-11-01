---
title: コンパイラの警告 (レベル 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: c5ffa07b06f010d10edc14aa7576bb614aa9dd04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471904"
---
# <a name="compiler-warning-level-4-c4238"></a>コンパイラの警告 (レベル 4) C4238

使用される標準の拡張機能: 左辺値として使用されるクラスの右辺値

Microsoft の拡張機能、Visual C の以前のバージョンとの互換性 (**/Ze**) のコンテキストで、右辺値を暗黙的または明示的には、アドレスは、クラス型を使用することです。 場合によっては、次の例などの危険な指定できます。

## <a name="example"></a>例

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

この使用法、ANSI 互換のエラーが発生 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。