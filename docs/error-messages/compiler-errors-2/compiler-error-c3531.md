---
title: コンパイラ エラー C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 0f6094daddf40b0899dc7f341f50a31daf7a999b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435452"
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