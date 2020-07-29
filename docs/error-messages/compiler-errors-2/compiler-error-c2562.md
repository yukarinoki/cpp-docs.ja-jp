---
title: コンパイラ エラー C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 7efc94cc859bbee6db0ce973135c7501fd79ae1d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206940"
---
# <a name="compiler-error-c2562"></a>コンパイラ エラー C2562

' identifier ': ' void ' 関数は値を返します

関数はとして宣言されてい **`void`** ますが、値を返します。

このエラーは、関数プロトタイプが正しくないことが原因で発生する可能性があります。

関数宣言で戻り値の型を指定すると、このエラーが解決される場合があります。

次の例では、C2562 が生成されます。

```cpp
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```
