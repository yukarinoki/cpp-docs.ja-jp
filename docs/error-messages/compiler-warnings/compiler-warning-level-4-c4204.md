---
title: コンパイラの警告 (レベル 4) C4204
ms.date: 11/04/2016
f1_keywords:
- C4204
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
ms.openlocfilehash: 45ed4817dbf2c7ecd63cd0c669d6e1cf768184bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174051"
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
