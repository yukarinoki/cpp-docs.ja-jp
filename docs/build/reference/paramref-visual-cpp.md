---
title: '&lt;paramref> (C++ ドキュメントコメント)'
description: Paramref C++ XML ドキュメントタグの詳細については、こちらを参照してください。
ms.date: 11/04/2016
f1_keywords:
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: 393703e7816368fb80f71d962dc190a0db1cea03
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126157"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

\<paramref> タグは、単語がパラメーターであることを示す方法を提供します。 .xml ファイルを処理することで、いくつかの独自の方法でこのパラメーターの書式設定を行うことができます。

## <a name="syntax"></a>構文

```
<paramref name="name"/>
```

#### <a name="parameters"></a>パラメーター

*name*<br/>
参照されるパラメーターの名前です。  名前は、一重引用符または二重引用符で囲みます。  コンパイラは、`name` が見つからない場合に警告を発行します。

## <a name="remarks"></a>解説

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_paramref_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_paramref_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <summary>MyMethod is a method in the MyClass class.
   /// The <paramref name="Int1"/> parameter takes a number.
   /// </summary>
   void MyMethod(int Int1) {}
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
