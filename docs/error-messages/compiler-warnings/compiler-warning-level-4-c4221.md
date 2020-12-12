---
description: '詳細情報: コンパイラの警告 (レベル 4) C4221'
title: コンパイラの警告 (レベル 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: 4632b075dfb6a7c1895415a253c70f5b4fd4f278
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164277"
---
# <a name="compiler-warning-level-4-c4221"></a>コンパイラの警告 (レベル 4) C4221

非標準の拡張機能が使用されています: ' identifier ': 自動変数のアドレスを使用して初期化することはできません

既定の Microsoft 拡張機能 (/Ze) では、集計型 (**配列**、 **`struct`** 、または **`union`** ) をローカル (自動) 変数のアドレスで初期化できます。

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
