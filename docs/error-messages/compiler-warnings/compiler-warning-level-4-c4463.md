---
title: コンパイラの警告 (レベル 4) C4463 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4463
dev_langs:
- C++
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 388f18ce1bc2e3a4279510ad6dc1a6938ab6f0e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109432"
---
# <a name="compiler-warning-level-4-c4463"></a>コンパイラの警告 (レベル 4) C4463

> オーバーフローです。割り当てる*値*のみからの値を保持できるビット フィールドに*low_value*に*high_value*

割り当てられている*値*ビット フィールドが保持できる値の範囲外です。 符号付きビット フィールドの型を使用して、上位ビットを符号のため*n* 、ビット フィールドのサイズ範囲は、符号付きビット フィールドは-2<sup>n-1</sup> 2<sup>n-1</sup>-1 で、符号なしの中にビット フィールドが 0 ~ 2 の範囲にある<sup>n</sup>-1。

## <a name="example"></a>例

この例では生成しようとする型のビット フィールドに値 3 を割り当てるため C4463 `int` -2 ~ 1 の範囲のサイズが 2 には、あります。

この問題を解決するには、許容範囲内に割り当てられた値を変更できます。 宣言の型を変更するには、ビット フィールドを 0 ~ 3 の範囲の符号なしの値を保持する場合は`unsigned`します。 フィールドを 3 に範囲-4 の値を保持する場合は 3 に、ビット フィールドのサイズを変更できます。

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
