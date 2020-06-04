---
title: コンパイラの警告 (レベル 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: fa948865685af4cbd6a865cfbf1d8546b29ab280
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161140"
---
# <a name="compiler-warning-level-4-c4221"></a>コンパイラの警告 (レベル 4) C4221

非標準の拡張機能が使用されています: ' identifier ': 自動変数のアドレスを使用して初期化することはできません

既定の Microsoft 拡張機能 (/Ze) を使用すると、ローカル (自動) 変数のアドレスを使用して集計の種類 (**配列**、`struct`、または**共用体**) を初期化できます。

## <a name="example"></a>例

```c
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

このような初期化は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
