---
title: '&lt;例外&gt;(Visual C) |Microsoft ドキュメント'
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
ms.openlocfilehash: 8d3d5b7a89a3725ae9dee2065bcd21d8f114ca00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ltexceptiongt-visual-c"></a>&lt;例外&gt;(Visual C)
\<exception> タグを使用すると、スローできる例外を指定できます。 このタグは、メソッドの定義に適用されます。  
  
## <a name="syntax"></a>構文  
  
```  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `member`  
 現在のコンパイル環境から使用できる例外の参照。 名前のルックアップ規則を使用するには、コンパイラをチェックする特定の例外が存在し、変換`member`出力 XML 内の標準要素名にします。  コンパイラは、`member` が見つからない場合に警告を発行します。  
  
 名前は、一重引用符または二重引用符で囲みます。  
  
 ジェネリック型への cref 参照を作成する方法については、「[\<see>](../ide/see-visual-cpp.md)」を参照してください。  
  
 `description`  
 説明です。  
  
## <a name="remarks"></a>コメント  
 コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
 Visual C++ コンパイラは、ドキュメント コメントを通じて 1 回渡すことで cref 参照の解決を試みます。  したがって、C++ のルックアップ規則を使用する場合、コンパイラによってシンボルが見つからないと、参照が未解決としてマークされます。 参照してください[ \<seealso >](../ide/seealso-visual-cpp.md)詳細についてはします。  
  
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
  
## <a name="see-also"></a>関連項目  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)