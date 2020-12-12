---
description: '詳細情報: コンパイラの警告 (レベル 4) C4463'
title: コンパイラの警告 (レベル 4) C4463
ms.date: 11/04/2016
f1_keywords:
- C4463
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
ms.openlocfilehash: fe4ea13c50e16bf5b72f5753fa989970db3cadde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251324"
---
# <a name="compiler-warning-level-4-c4463"></a>コンパイラの警告 (レベル 4) C4463

> 超え *low_value* から *high_value* までの値のみを保持できるビットフィールドへの *値* の代入

割り当てられた *値* が、ビットフィールドに保持できる値の範囲外です。 符号付きビットフィールド型は、符号に上位ビットを使用します。そのため、 *n* がビットフィールドサイズの場合、符号付きビットフィールドの範囲は-2 <sup>n-1</sup> ~ 2 <sup>n-1</sup>-1 になります。一方、符号なしビットフィールドの範囲は 0 ~ 2 <sup>n-1</sup>です。

## <a name="example"></a>例

この例では、-2 ~ 1 の範囲のサイズが2である型のビットフィールドに3の値を割り当てようとするため、C4463 が生成さ **`int`** れます。

この問題を解決するには、割り当てられた値を、許容範囲内の値に変更します。 ビットフィールドが 0 ~ 3 の範囲内の符号なしの値を保持することを意図している場合は、宣言の種類をに変更でき **`unsigned`** ます。 フィールドが-4 ~ 3 の範囲の値を保持することを目的としている場合は、ビットフィールドのサイズを3に変更できます。

```cpp
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S {
    int x : 2; // int type treats high-order bit as sign
};

int main() {
    S s;
    s.x = 3; // warning C4463: overflow; assigning 3
    // to bit-field that can only hold values from -2 to 1
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type
    // to unsigned.
}
```
