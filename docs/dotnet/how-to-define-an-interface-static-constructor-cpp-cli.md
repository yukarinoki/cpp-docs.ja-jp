---
title: '方法: インターフェイス静的コンス トラクターを定義 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- static constructors, interface
- interface static constructor
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c47efbf364f5ddacb7ce534b0dfd7853534acb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-an-interface-static-constructor-ccli"></a>方法: インターフェイス静的コンストラクターを定義する (C++/CLI)
インターフェイスは、静的データ メンバーの初期化に使用できる静的コンス トラクターを持つことができます。  静的コンス トラクターは、最大でも 1 回呼び出されが初めての静的なインターフェイス メンバーにアクセスする前に呼び出されます。  
  
## <a name="example"></a>例  
  
```  
// mcppv2_interface_class2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct MyInterface {  
   static int i;  
   static void Test() {  
      Console::WriteLine(i);  
   }  
  
   static MyInterface() {   
      Console::WriteLine("in MyInterface static constructor");  
      i = 99;  
   }  
};  
  
ref class MyClass : public MyInterface {};  
  
int main() {  
   MyInterface::Test();  
   MyClass::MyInterface::Test();  
  
   MyInterface ^ mi = gcnew MyClass;  
   mi->Test();  
}  
```  
  
```Output  
in MyInterface static constructor  
99  
99  
99  
```  
  
## <a name="see-also"></a>関連項目  
 [インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)