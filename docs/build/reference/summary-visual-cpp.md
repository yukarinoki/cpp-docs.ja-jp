---
description: '詳細情報: &lt; 概要&gt;'
title: '&lt;概要> (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 3003a3226a67d864be1a07a47151e7003c5514a4
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126339"
---
# <a name="ltsummarygt"></a>&lt;summary&gt;

\<summary> タグは、型または型メンバーの説明に使用します。 型の説明に補足情報を追加するには、[\<remarks>](remarks-visual-cpp.md) を使用します。

## <a name="syntax"></a>構文

```
<summary>description</summary>
```

#### <a name="parameters"></a>パラメーター

*description*<br/>
オブジェクトの概要。

## <a name="remarks"></a>Remarks

タグのテキストは、 \<summary> IntelliSense の型に関する情報の唯一のソースであり、 [オブジェクトブラウザー](/visualstudio/ide/viewing-the-structure-of-code) およびコードコメント Web レポートにも表示されます。

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
