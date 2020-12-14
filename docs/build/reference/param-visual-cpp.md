---
description: '詳細情報: &lt; param&gt;'
title: '&lt;param> (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: 7c3baabc6aef9a4cabdd7c7a9023fb628bd53793
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226143"
---
# <a name="ltparamgt"></a>&lt;param&gt;

\<param> タグは、メソッドのいずれかのパラメーターを記述するために、メソッド宣言のコメントで使用する必要があります。

## <a name="syntax"></a>構文

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
メソッド パラメーターの名前です。  名前は、一重引用符または二重引用符で囲みます。  コンパイラは、`name` が見つからない場合に警告を発行します。

*description*<br/>
パラメーターの説明です。

## <a name="remarks"></a>Remarks

タグのテキストは、 \<param> IntelliSense、 [オブジェクトブラウザー](/visualstudio/ide/viewing-the-structure-of-code)、およびコードコメント Web レポートに表示されます。

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_param_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_param_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <param name="Int1">Used to indicate status.</param>
   void MyMethod(int Int1) {
   }
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
