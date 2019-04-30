---
title: コンパイラ エラー C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 437727b334087aef496dbb0a1f3f1c8cf2b45458
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345598"
---
# <a name="compiler-error-c2537"></a>コンパイラ エラー C2537

'specifier': リンケージの仕様

以下の原因が考えられます。

1. リンケージ指定子がサポートされていません。 "C"リンケージ指定子のみがサポートされています。

1. "C"リンケージは、一連のオーバー ロードされた関数の 1 つ以上の関数に対して指定されます。 これは認められていません。

次の例では、C2537 が生成されます。

```
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```