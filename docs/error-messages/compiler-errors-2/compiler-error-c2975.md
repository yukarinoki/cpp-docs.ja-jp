---
title: コンパイラ エラー C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 70fc648de8bcf4f1e85edf3a12cc0b7d3d70625f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201566"
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

C2975 は、 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)を使用&#95; &#95;し&#95; &#95;てコンパイル時の定数として行を使用する場合にも発生します。 1つの解決策は、 **/zi**ではなく[/zi](../../build/reference/z7-zi-zi-debug-information-format.md)を使用してコンパイルすることです。

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
