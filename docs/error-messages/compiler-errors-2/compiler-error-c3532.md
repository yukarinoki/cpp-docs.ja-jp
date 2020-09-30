---
title: コンパイラ エラー C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: b8d516074b79704b10d27dd4638585a5ada08323
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510122"
---
# <a name="compiler-error-c3532"></a>コンパイラ エラー C3532

' type ': ' auto ' の使用法が正しくありません

指定された型をキーワードで宣言することはできません **`auto`** 。 たとえば、キーワードを使用して、 **`auto`** 配列またはメソッドの戻り値の型を宣言することはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 初期化式によって有効な型が生成されていることを確認します。

1. 配列またはメソッドの戻り値の型が宣言されていないことを確認してください。

## <a name="examples"></a>例

次の例では、 **`auto`** キーワードがメソッドの戻り値の型を宣言できないため、C3532 が生成されます。

```cpp
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

次の例では、 **`auto`** キーワードが配列を宣言できないため、C3532 が生成されます。

```cpp
// C3532b.cpp
// Compile with /Zc:auto
int main()
{
   int x[5];
   auto a[5];            // C3532
   auto b[1][2];         // C3532
   auto y[5] = x;        // C3532
   auto z[] = {1, 2, 3}; // C3532
   auto w[] = x;         // C3532
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-cpp.md)
