---
title: コンパイラの警告 (レベル 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 36d5de3b1270b41edfc391df960a556aca207709
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555299"
---
# <a name="compiler-warning-level-1-c4218"></a>コンパイラの警告 (レベル 1) C4218

使用される標準の拡張機能: ストレージ クラスまたは型を指定する必要があります

既定の Microsoft 拡張 (/Ze) で型またはストレージ クラスを指定することがなく変数を宣言することができます。 既定の型は `int` です。

## <a name="example"></a>例

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

このような宣言が ANSI 互換では無効です ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。