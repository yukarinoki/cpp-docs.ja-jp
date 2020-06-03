---
title: コンパイラの警告 (レベル 4) C4213
ms.date: 11/04/2016
f1_keywords:
- C4213
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
ms.openlocfilehash: e462fcc2d0283d2519796127612123f7d792d00e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161296"
---
# <a name="compiler-warning-level-4-c4213"></a>コンパイラの警告 (レベル 4) C4213

非標準の拡張機能が使用されています: 左辺値にキャストします

既定の Microsoft 拡張機能 (/Ze) では、代入ステートメントの左側でキャストを使用できます。

## <a name="example"></a>例

```c
// C4213.c
// compile with: /W4
void *a;
void f()
{
   int   i[3];
   a = &i;
   *(( int * )a )++ = 3;  // C4213
}

int main()
{
}
```

ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では、このようなキャストは無効です。
