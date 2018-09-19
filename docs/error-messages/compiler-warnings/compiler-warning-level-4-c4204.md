---
title: コンパイラの警告 (レベル 4) C4204 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4204
dev_langs:
- C++
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61194e28081c42a71847eca3f97e4d1f46771d16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037542"
---
# <a name="compiler-warning-level-4-c4204"></a>コンパイラの警告 (レベル 4) C4204

標準の拡張機能を使用: 非定数の初期化子の集約

Microsoft 拡張機能 (/Ze)、定数ではない値を持つ集約型 (配列、構造体、共用体、およびクラス) を初期化できます。

## <a name="example"></a>例

```
// C4204.c
// compile with: /W4
int func1()
{
   return 0;
}
struct S1
{
   int i;
};

int main()
{
   struct S1 s1 = { func1() };   // C4204
   return s1.i;
}
```

このような初期化が有効で ANSI 互換でない ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。