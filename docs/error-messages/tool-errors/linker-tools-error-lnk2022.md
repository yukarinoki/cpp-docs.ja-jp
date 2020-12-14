---
description: 詳細については、「リンカツール Error LNK2022」を参照してください。
title: リンカ ツール エラー LNK2022
ms.date: 11/04/2016
f1_keywords:
- LNK2022
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
ms.openlocfilehash: ed609c47e67a4719f2447f9cdff35221ef157cf8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275842"
---
# <a name="linker-tools-error-lnk2022"></a>リンカ ツール エラー LNK2022

> メタデータ操作に失敗しました (*HRESULT*): *error_message*

メタデータのマージ中にリンカーでエラーが検出されました。 リンクに成功するには、メタデータエラーを解決する必要があります。

この問題を診断する方法の1つとして、オブジェクトファイルに対して **ildasm.exe** を実行して、に一覧表示されているトークンがある型を特定 `error_message` し、相違点を確認します。  メタデータでは、LayoutType 属性が異なる場合でも、同じ名前の2つの異なる型は無効です。

LNK2022 の1つの理由は、型 (構造体など) が同じ名前の複数の compilands に存在し、競合する定義がある場合、および [/clr](../../build/reference/clr-common-language-runtime-compilation.md)でコンパイルする場合です。  この場合は、すべての compilands で、型の定義が同一であることを確認してください。  型名は「」に記載されて `error_message` います。

LNK2022 のもう1つの原因としては、リンカーが、コンパイラに対して指定されたものとは異なる場所にあるメタデータファイルを検索する場合があります ( [#using](../../preprocessor/hash-using-directive-cpp.md) )。 リンカーに渡されたときと同じ場所にメタデータファイル (.dll または .netmodule) があることを確認します。これは、コンパイラに渡されたときと同じです。

ATL アプリケーションをビルドするとき、 `_ATL_MIXED` 少なくとも1つので使用されている場合は、すべての compilands でマクロを使用する必要があります。

## <a name="examples"></a>例

次の例では、空の型を定義しています。

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

このサンプルでは、同じ名前で定義が異なる2つのソースコードファイルをリンクすることはできないことを示しています。

次の例では、LNK2022 が生成されます。

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```
