---
title: コンパイラの警告 (レベル 3) C4018 由来
description: Microsoft C/c + + コンパイラの警告 C4018 由来、その原因、および解決策。
ms.date: 10/16/2020
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.openlocfilehash: b9d01f6b733c2ca18880aa6f4b6fca9771f8123f
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176179"
---
# <a name="compiler-warning-level-3-c4018"></a>コンパイラの警告 (レベル 3) C4018 由来

> '*token*': 符号付きまたは符号なしの不一致です。

*トークン*演算子を使用してとの数値を比較するに **`signed`** は、 **`unsigned`** コンパイラが値をに変換する必要がありました **`signed`** **`unsigned`** 。

## <a name="remarks"></a>注釈

この警告を解決する1つの方法は **`signed`** 、型と型を比較するときに、2つの型のいずれかをキャストする場合です **`unsigned`** 。

## <a name="example"></a>例

このサンプルでは、C4018 由来を生成し、その修正方法を示しています。

```cpp
// C4018.cpp
// compile with: cl /EHsc /W4 C4018.cpp
int main() {
    unsigned int uc = 0;
    int c = 0;
    unsigned int c2 = c; // implicit conversion

    if (uc < c)           // C4018
        uc = 0;

    if (uc < unsigned(c)) // OK
        uc = 0;

    if (uc < c2)          // Also OK
       uc = 0;
}
```

## <a name="see-also"></a>関連項目

[コンパイラの警告 (レベル 4) C4388](c4388.md)\
[コンパイラの警告 (レベル 4) C4389](compiler-warning-level-4-c4389.md)
