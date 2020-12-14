---
description: '詳細情報: コンパイラの警告 (レベル 4) C4213'
title: コンパイラの警告 (レベル 4) C4213
ms.date: 11/04/2016
f1_keywords:
- C4213
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
ms.openlocfilehash: 400cd650542bfd7a71640947467e8340f63bb3df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297344"
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
