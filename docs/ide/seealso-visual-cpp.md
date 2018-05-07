---
title: '&lt;seealso&gt; (Visual C) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <seealso>
- seealso
dev_langs:
- C++
helpviewer_keywords:
- seealso C++ XML tag
- <seealso> C++ XML tag
ms.assetid: cb33d100-9c50-4485-8d0c-573429eff155
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a726a2fa1694fd346a6632fdc5e40bd53547fc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ltseealsogt-visual-c"></a>&lt;seealso&gt; (Visual C)
\<seealso > タグを使用して、「See Also」セクションに表示するテキストを指定することができます。 [\<see>](../ide/see-visual-cpp.md) タグを使用すると、テキスト内からリンクを指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `member`  
 現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。  名前は、一重引用符または二重引用符で囲みます。  
  
 コンパイラは、指定されたコード要素が存在し、解決されることを確認`member`出力 XML 内の要素名にします。  コンパイラは、`member` が見つからない場合に警告を発行します。  
  
 ジェネリック型への cref 参照を作成する方法については、「[\<see>](../ide/see-visual-cpp.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
 \<seealso> の使用例については、[\<summary>](../ide/summary-visual-cpp.md) を参照してください。  
  
 Visual C++ コンパイラは、ドキュメント コメントを通じて 1 回渡すことで cref 参照の解決を試みます。  したがって、C++ のルックアップ規則を使用する場合、コンパイラによってシンボルが見つからないと、参照が未解決としてマークされます。  
  
## <a name="example"></a>例  
 次の例で、cref で未解決のシンボルが参照されます。 B::Test に cref の XML コメントはされます`<seealso cref="!:B::Test" />`A::Test への参照が整形式には、`<seealso cref="M:A.Test" />`です。  
  
```  
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
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)