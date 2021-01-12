---
description: '詳細情報: &lt; 例&gt;'
title: '&lt;> の例 (C++ ドキュメントコメント)'
ms.date: 11/04/2016
f1_keywords:
- <example>
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 61624efd34c02d75c7109a3211914b2018c513ae
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "98125884"
---
# <a name="ltexamplegt"></a>&lt;example&gt;

\<example> タグを使用すると、メソッドまたは他のライブラリ メンバーの使用例を指定できます。 一般的に、これにはタグの使用も含ま [\<code>](code-visual-cpp.md) れます。

## <a name="syntax"></a>構文

```
<example>description</example>
```

#### <a name="parameters"></a>パラメーター

*description*<br/>
コード例の説明です。

## <a name="remarks"></a>Remarks

ドキュメントコメントをファイルに処理するために、 [/doc](doc-process-documentation-comments-c-cpp.md) を使用してコンパイルします。

## <a name="example"></a>例

```cpp
// xml_example_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_example_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>
   /// GetZero method
   /// </summary>
   /// <example> This sample shows how to call the GetZero method.
   /// <code>
   /// int main()
   /// {
   ///    return GetZero();
   /// }
   /// </code>
   /// </example>
   static int GetZero() {
      return 0;
   }
};
```

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
