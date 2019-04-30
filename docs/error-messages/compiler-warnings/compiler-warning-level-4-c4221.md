---
title: コンパイラの警告 (レベル 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: f552a5d76d1a778cdf72cbe079138f609350ffb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401099"
---
# <a name="compiler-warning-level-4-c4221"></a>コンパイラの警告 (レベル 4) C4221

使用される標準の拡張機能: 'identifier': 自動変数のアドレスを使用して初期化することはできません

既定の Microsoft 拡張子 (/Ze) を持つ集約型を初期化することができます (**配列**、 `struct`、または**共用体**) (自動) のローカル変数のアドレスを使用します。

## <a name="example"></a>例

```
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

このような初期化が有効で ANSI 互換でない ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。