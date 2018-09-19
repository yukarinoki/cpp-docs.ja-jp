---
title: コンパイラ エラー C3531 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 375eb419e3f2f492df328a964eeb1bb77bc0d5dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106851"
---
# <a name="compiler-error-c3531"></a>コンパイラ エラー C3531

'symbol': 'auto' を含む型のシンボルは初期化子が必要

指定された変数の初期化子式ではありません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 変数を宣言するときに、等号 (=) の構文を使用する単純な代入など、初期化子式を指定します。

## <a name="example"></a>例

次の例では C3531 のため変数`x1`、 `y1, y2, y3`、および`z2`が初期化されていません。

```
// C3531.cpp
// Compile with /Zc:auto
int main()
{
   auto x1;                  // C3531
   auto y1, y2, y3;          // C3531
   auto z1 = 1, z2, z3 = -1; // C3531
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)