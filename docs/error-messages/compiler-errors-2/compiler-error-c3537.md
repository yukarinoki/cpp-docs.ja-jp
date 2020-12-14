---
description: 詳細については、「コンパイラエラー C3537」を参照してください。
title: コンパイラ エラー C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 84440b757b85a59f87fcca064911136da6cce269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315258"
---
# <a name="compiler-error-c3537"></a>コンパイラ エラー C3537

' type ': ' auto ' を含む型にキャストすることはできません

型にキーワードが含まれ、 **`auto`** 既定の [/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) コンパイラオプションが有効になっているため、指定された型に変数をキャストすることはできません。

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

[auto キーワード](../../cpp/auto-cpp.md)
