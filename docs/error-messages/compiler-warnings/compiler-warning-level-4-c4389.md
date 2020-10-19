---
title: コンパイラの警告 (レベル 4) C4389
description: Microsoft C/c + + コンパイラの警告 C4389、その原因、および解決策。
ms.date: 10/16/2020
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.openlocfilehash: b06b013151ed12b4f66bb23a7e862992d05e6b30
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176259"
---
# <a name="compiler-warning-level-4-c4389"></a>コンパイラの警告 (レベル 4) C4389

> '*等値演算子*': 符号付きまたは符号なしの不一致です。

**`==`** **`!=`** および変数に関連する or 操作 **`signed`** **`unsigned`** 。 これにより、データが失われる可能性があります。

## <a name="remarks"></a>注釈

この警告を解決する1つの方法は **`signed`** 、型と型を比較するときに、2つの型のいずれかをキャストする場合です **`unsigned`** 。

## <a name="example"></a>例

次の例では、C4389 が生成されます。

```cpp
// C4389.cpp
// compile with: cl /EHsc /W4 C4389.cpp

int main()
{
   int a = 9;
   unsigned int b = 10;
   int result = 0;

   if (a == b)   // C4389
      result = 1;
   else
      result = 2;

   if (unsigned(a) == b) // OK
      result = 3;
   else
      result = 4;

   return result;
}
```

## <a name="see-also"></a>関連項目

[コンパイラの警告 C4018 由来](compiler-warning-level-3-c4018.md)\
[コンパイラの警告 (レベル 4) C4388](c4388.md)
