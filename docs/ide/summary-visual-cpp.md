---
title: '&lt;summary&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <summary>
- summary
dev_langs:
- C++
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47b7063dc9156e8feb41d447283ee457a13f1f4d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692303"
---
# <a name="ltsummarygt-visual-c"></a>&lt;summary&gt; (Visual C++)
\<summary> タグは、型または型のメンバーの説明に使用します。 型の説明に補足情報を追加するには、[\<remarks>](../ide/remarks-visual-cpp.md) タグを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `description`  
 オブジェクトの概要。  
  
## <a name="remarks"></a>コメント  
 \<summary> タグのテキストは、IntelliSense の型に関する唯一のソースで、[オブジェクト ブラウザー](/visualstudio/ide/viewing-the-structure-of-code)とコード コメント Web レポートにも表示されます。  
  
 コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
## <a name="example"></a>例  
  
```  
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
  
## <a name="see-also"></a>参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)