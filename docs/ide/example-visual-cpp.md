---
title: '&lt;example&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: b1511bb77b35b054d83a64c1a832843e62a8daa9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744011"
---
# <a name="ltexamplegt-visual-c"></a>&lt;example&gt; (Visual C++)

\<example> タグでは、メソッドまたはその他のライブラリ メンバーの使用例を指定できます。 この場合、通常は [\<code>](../ide/code-visual-cpp.md) タグも使用する必要があります。

## <a name="syntax"></a>構文

```
<example>description</example>
```

#### <a name="parameters"></a>パラメーター

*description*<br/>
コード例の説明です。

## <a name="remarks"></a>解説

コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

## <a name="example"></a>例

```
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

[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
