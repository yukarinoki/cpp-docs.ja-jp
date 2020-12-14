---
description: '詳細情報: コンパイラの警告 (レベル 4) C4204'
title: コンパイラの警告 (レベル 4) C4204
ms.date: 11/04/2016
f1_keywords:
- C4204
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
ms.openlocfilehash: edb802e1aa958e28d0a41f3cc64f5ddf058db909
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314790"
---
# <a name="compiler-warning-level-4-c4204"></a>コンパイラの警告 (レベル 4) C4204

非標準の拡張機能が使用されています: 非定数集計初期化子

Microsoft 拡張機能 (/Ze) を使用すると、定数以外の値を使用して集計の種類 (配列、構造体、共用体、およびクラス) を初期化できます。

## <a name="example"></a>例

```c
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

このような初期化は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
