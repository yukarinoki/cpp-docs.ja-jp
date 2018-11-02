---
title: コンパイラ エラー C3532
ms.date: 11/04/2016
f1_keywords:
- C3532
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
ms.openlocfilehash: 91d8e28e053d8ce1b307f9345ab3249386bdf1ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568891"
---
# <a name="compiler-error-c3532"></a>コンパイラ エラー C3532

'type': 'auto' の不適切な使用方法

指定された型を宣言することはできません、`auto`キーワード。 たとえば、使用することはできません、`auto`配列またはメソッドを宣言するキーワードが型を取得します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 初期化式が有効な型を生成することを確認します。

1. 配列またはメソッドの戻り値の型を宣言していないことを確認します。

## <a name="example"></a>例

次の例では C3532 のため、`auto`キーワードがメソッドの戻り値の型を宣言できません。

```
// C3532a.cpp
// Compile with /Zc:auto
auto f(){}   // C3532
```

## <a name="example"></a>例

次の例では C3532 のため、`auto`キーワードは、配列を宣言できません。

```
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

[auto キーワード](../../cpp/auto-keyword.md)