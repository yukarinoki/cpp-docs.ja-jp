---
title: コンパイラ エラー C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 4537c6c76814f2aeb8f8d62579caec86785de252
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510137"
---
# <a name="compiler-error-c3531"></a>コンパイラ エラー C3531

' symbol ': 型に ' auto ' を含むシンボルには初期化子を指定しなければなりません

指定された変数に初期化子式がありません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 変数を宣言するときに、等号構文を使用する単純な代入などの初期化子式を指定します。

## <a name="example"></a>例

次の例では、変数 `x1` 、 `y1, y2, y3` 、およびが初期化されていないため、C3531 `z2` が生成されます。

```cpp
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

[auto キーワード](../../cpp/auto-cpp.md)
