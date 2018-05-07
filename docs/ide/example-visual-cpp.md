---
title: '&lt;例&gt;(Visual C) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <example>
- example
dev_langs:
- C++
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cefd38a18447d0e8c9121d61c0ba963e9da39187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ltexamplegt-visual-c"></a>&lt;例&gt;(Visual C)
\<example> タグでは、メソッドまたはその他のライブラリ メンバーの使用例を指定できます。 一般的には、これも含まれるを使用して、 [\<コード >](../ide/code-visual-cpp.md)タグ。  
  
## <a name="syntax"></a>構文  
  
```  
<example>description</example>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `description`  
 コード例の説明です。  
  
## <a name="remarks"></a>コメント  
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