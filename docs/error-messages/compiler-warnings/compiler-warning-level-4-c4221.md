---
title: コンパイラの警告 (レベル 4) C4221 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4221
dev_langs:
- C++
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18b0804c8b7cb2d059e45fa504334687a796fbe1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056418"
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