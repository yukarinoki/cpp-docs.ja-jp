---
description: '詳細情報: &lt; seealso&gt;'
title: '&lt;seealso> (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- <seealso>
- seealso
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
ms.openlocfilehash: 70f5f0147ff56dd6327e99f073f80c28a7cce539
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224726"
---
# <a name="ltseealsogt"></a>&lt;seealso&gt;

\<seealso> タグを使用して、「関連項目」セクションに表示するテキストを指定することができます。 [\<see>](see-visual-cpp.md) を使用すると、テキスト内からリンクを指定できます。

## <a name="syntax"></a>構文

```
<seealso cref="member"/>
```

#### <a name="parameters"></a>パラメーター

*レプリカ*<br/>
現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。  名前は、一重引用符または二重引用符で囲みます。

コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に解決します。  コンパイラは、`member` が見つからない場合に警告を発行します。

ジェネリック型への cref 参照を作成する方法については、「」を参照してください [\<see>](see-visual-cpp.md) 。

## <a name="remarks"></a>解説

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

\<seealso> の使用例については、[\<summary>](summary-visual-cpp.md) を参照してください。

MSVC コンパイラは、ドキュメントコメント内の1回のパスで cref 参照の解決を試みます。  したがって、C++ のルックアップ規則を使用する場合、コンパイラによってシンボルが見つからないと、参照が未解決としてマークされます。

## <a name="example"></a>例

次のサンプルでは、cref で未解決のシンボルが参照されます。 B::Test の cref の XML コメントは `<seealso cref="!:B::Test" />` になり、A::Test の参照は整形式 `<seealso cref="M:A.Test" />` です。

```cpp
// xml_seealso_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_seealso_tag.dll

/// Text for class A.
public ref struct A {
   /// <summary><seealso cref="A::Test"/>
   /// <seealso cref="B::Test"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void Test() {}
};

/// Text for class B.
public ref struct B {
   void Test() {}
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
