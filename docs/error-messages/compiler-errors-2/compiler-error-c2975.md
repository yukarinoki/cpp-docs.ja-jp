---
description: 詳細については、「コンパイラエラー C2975」を参照してください。
title: コンパイラ エラー C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 9f9108d1dc4e0fe61b6dd2135fb69bbaedfaedf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210349"
---
# <a name="compiler-error-c2975"></a>コンパイラ エラー C2975

> '*argument*': '*type*' の無効なテンプレート引数です。コンパイル時の定数式が必要です

テンプレート引数がテンプレート宣言と一致しません。山かっこ内に定数式が表示されます。 テンプレートの実際の引数として変数を使用することはできません。 テンプレートの定義を調べて正しい型が指定されていることをご確認ください。

## <a name="example"></a>例

次の例では、C2975 を生成し、正しい使用法も示しています。

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 は、 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してコンパイル時の定数として &#95;&#95;行&#95;&#95; を使用する場合にも発生します。 1つの解決策は、 **/zi** ではなく [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してコンパイルすることです。

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```
