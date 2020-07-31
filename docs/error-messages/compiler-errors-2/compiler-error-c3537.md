---
title: コンパイラ エラー C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 663ef761d6c52aeb4c3cc9ce109079c647904e36
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197554"
---
# <a name="compiler-error-c3537"></a>コンパイラ エラー C3537

' type ': ' auto ' を含む型にキャストすることはできません

型にキーワードが含まれ、 **`auto`** 既定の[/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラオプションが有効になっているため、指定された型に変数をキャストすることはできません。

## <a name="example"></a>例

次のコードでは、変数がキーワードを含む型にキャストされるため、C3537 が生成され **`auto`** ます。

```cpp
// C3537.cpp
// Compile with /Zc:auto
int main()
{
   int value = 123;
   auto(value);                        // C3537
   (auto)value;                        // C3537
   auto x1 = auto(value);              // C3537
   auto x2 = (auto)value;              // C3537
   auto x3 = static_cast<auto>(value); // C3537
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)
