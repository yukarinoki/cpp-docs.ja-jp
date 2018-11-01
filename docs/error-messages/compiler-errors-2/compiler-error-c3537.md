---
title: コンパイラ エラー C3537
ms.date: 11/04/2016
f1_keywords:
- C3537
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
ms.openlocfilehash: 22387470019b0118d06b4cacd82a1df5c3e505fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576125"
---
# <a name="compiler-error-c3537"></a>コンパイラ エラー C3537

'type': 'auto' を含む型にキャストすることはできません

型が含まれているため、示された型の変数をキャストすることはできません、`auto`キーワードおよび既定[/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションが有効にします。

## <a name="example"></a>例

変数は、含む型にキャストするため、次のコード生成 C3537、`auto`キーワード。

```
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