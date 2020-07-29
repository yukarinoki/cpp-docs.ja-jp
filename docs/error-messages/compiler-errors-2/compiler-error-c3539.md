---
title: コンパイラ エラー C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 813da5a2fd79c191df731937e58100d749f8690c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223409"
---
# <a name="compiler-error-c3539"></a>コンパイラ エラー C3539

' type ': テンプレート引数に ' auto ' を含む型を指定することはできません

指定されたテンプレート引数の型にキーワードの使用を含めることはできません **`auto`** 。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. テンプレート引数は、キーワードを使用して指定しないでください **`auto`** 。

## <a name="example"></a>例

次の例では、C3539 が生成されます。

```cpp
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)
