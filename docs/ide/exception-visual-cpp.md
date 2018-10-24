---
title: '&lt;exception&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- exception
- <exception>
dev_langs:
- C++
helpviewer_keywords:
- <exception> C++ XML tag
- exception C++ XML tag
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb7b5f4e153ca892cf10f8c5cbe6fe1bebbd20f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419969"
---
# <a name="ltexceptiongt-visual-c"></a>&lt;exception&gt; (Visual C++)

\<exception> タグを使用すると、スローできる例外を指定できます。 このタグは、メソッドの定義に適用されます。

## <a name="syntax"></a>構文

```
<exception cref="member">description</exception>
```

#### <a name="parameters"></a>パラメーター

*member*<br/>
現在のコンパイル環境から使用できる例外の参照。 名前参照ルールを使用し、コンパイラは、指定された例外が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。  コンパイラは、`member` が見つからない場合に警告を発行します。

名前は、一重引用符または二重引用符で囲みます。

ジェネリック型への cref 参照を作成する方法については、「[\<see>](../ide/see-visual-cpp.md)」を参照してください。

*description*<br/>
説明です。

## <a name="remarks"></a>コメント

コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。

Visual C++ コンパイラは、ドキュメント コメントを通じて 1 回渡すことで cref 参照の解決を試みます。  したがって、C++ のルックアップ規則を使用する場合、コンパイラによってシンボルが見つからないと、参照が未解決としてマークされます。 詳細については、「[\<seealso>](../ide/seealso-visual-cpp.md)」を参照してください。

## <a name="example"></a>例

```
// xml_exception_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_exception_tag.dll
using namespace System;

/// Text for class EClass.
public ref class EClass : public Exception {
   // class definition ...
};

/// <exception cref="System.Exception">Thrown when... .</exception>
public ref class TestClass {
   void Test() {
      try {
      }
      catch(EClass^) {
      }
   }
};
```

## <a name="see-also"></a>参照

[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)