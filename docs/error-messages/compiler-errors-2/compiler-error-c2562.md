---
description: 詳細については、「コンパイラエラー C2562」を参照してください。
title: コンパイラ エラー C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 9e9da8a7463b450073f4b537ec36512242995760
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338713"
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
