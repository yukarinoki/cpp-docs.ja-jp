---
title: '&lt;param&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: ec570a1c8b66e12474a2d960ed1b4f4b5e21b219
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651335"
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)

\<param> タグは、メソッドのいずれか 1 つのパラメーターを説明するためにメソッドの宣言のコメントで使用する必要があります。

## <a name="syntax"></a>構文

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
メソッド パラメーターの名前です。  名前は、一重引用符または二重引用符で囲みます。  コンパイラは、`name` が見つからない場合に警告を発行します。

*description*<br/>
パラメーターの説明です。

## <a name="remarks"></a>コメント

\<param> タグのテキストは、IntelliSense、[オブジェクト ブラウザー](/visualstudio/ide/viewing-the-structure-of-code)、コード コメント Web レポートに表示されます。

コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

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

## <a name="see-also"></a>参照

[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)