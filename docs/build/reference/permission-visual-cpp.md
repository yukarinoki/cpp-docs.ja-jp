---
title: '&lt;アクセス許可 > (ドキュメント コメントの C++)'
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: 764048f7bc579afa6862bdff40968588955dc307
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826998"
---
# <a name="ltpermissiongt"></a>&lt;permission&gt;

\<permission> タグを使用すると、メンバーのアクセスを文書化できます。 <xref:System.Security.PermissionSet> を使用すると、メンバーへのアクセスを指定できます。

## <a name="syntax"></a>構文

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>パラメーター

*member*<br/>
現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。 コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。  名前は、一重引用符または二重引用符で囲みます。

コンパイラは、`member` が見つからない場合に警告を発行します。

ジェネリック型への cref 参照を作成する方法については、「[\<see>](see-visual-cpp.md)」を参照してください。

*description*<br/>
メンバーへのアクセスの説明です。

## <a name="remarks"></a>Remarks

コンパイル時に [/doc](doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

MSVC コンパイラは、ドキュメント コメントを通じて 1 つのパスで cref 参照を解決しようとします。  したがって、C++ のルックアップ規則を使用する場合、コンパイラによってシンボルが見つからないと、参照が未解決としてマークされます。 詳細については、「[\<seealso>](seealso-visual-cpp.md)」を参照してください。

## <a name="example"></a>例

```
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
