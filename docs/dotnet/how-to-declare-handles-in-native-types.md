---
title: '方法: ネイティブ型のハンドルを宣言 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
f1_keywords:
- gcroot
dev_langs:
- C++
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4573aac37eedecceab861eb41a70fc858b409fec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130972"
---
# <a name="how-to-declare-handles-in-native-types"></a>方法: ネイティブ型のハンドルを宣言する
ネイティブ型のハンドル型を宣言することはできません。 vcclr.h の提供、タイプ セーフ ラッパー テンプレート`gcroot`C++ ヒープから CLR オブジェクトを参照します。 このテンプレートでは、ネイティブ型に仮想のハンドルを埋め込むし、基になる型の場合と同様に扱うことできます。 ほとんどの場合、使用することができます、`gcroot`キャストなし埋め込み型としてオブジェクト。 は、[ごとで](../dotnet/for-each-in.md)を使用する必要がある`static_cast`を基になるマネージ参照を取得します。  
  
 `gcroot`テンプレートは、ガベージ コレクトされたヒープに「ハンドル」を提供する System::Runtime::InteropServices::GCHandle 値クラスの機能を使用して実装されます。 ハンドル自身がガベージ コレクションし、のデストラクターによって使用されていないときに解放されます、`gcroot`クラス (このデストラクターは手動で呼び出すことはできません)。 インスタンス化する場合、`gcroot`呼び出す必要があります、ネイティブ ヒープのオブジェクトでそのリソースを削除します。  
  
 ランタイムは、ハンドルおよび参照する CLR オブジェクト間の関連付けを維持します。 CLR オブジェクトがガベージ コレクトされたヒープを使用して移動、ときに、ハンドルは、オブジェクトの新しいアドレスを返します。 変数に代入される前にピン留めする必要はありません、`gcroot`テンプレート。  
  
## <a name="example"></a>例  
 このサンプルを作成する方法を示しています、`gcroot`ネイティブ スタック上のオブジェクト。  
  
```  
// mcpp_gcroot.cpp  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
class CppClass {  
public:  
   gcroot<String^> str;   // can use str as if it were String^  
   CppClass() {}  
};  
  
int main() {  
   CppClass c;  
   c.str = gcnew String("hello");  
   Console::WriteLine( c.str );   // no cast required  
}  
```  
  
```Output  
hello  
```  
  
## <a name="example"></a>例  
 このサンプルを作成する方法を示しています、`gcroot`ネイティブ ヒープのオブジェクト。  
  
```  
// mcpp_gcroot_2.cpp  
// compile with: /clr  
// compile with: /clr  
#include <vcclr.h>  
using namespace System;  
  
struct CppClass {  
   gcroot<String ^> * str;  
   CppClass() : str(new gcroot<String ^>) {}  
  
   ~CppClass() { delete str; }  
  
};  
  
int main() {  
   CppClass c;  
   *c.str = gcnew String("hello");  
   Console::WriteLine( *c.str );  
}  
```  
  
```Output  
hello  
```  
  
## <a name="example"></a>例  
 このサンプルを使用する方法を示します`gcroot`を使用して、値型 (参照型ではなく) への参照をネイティブ型に保持するために`gcroot`ボックス化された型にします。  
  
```  
// mcpp_gcroot_3.cpp  
// compile with: /clr  
#include < vcclr.h >  
using namespace System;  
  
public value struct V {  
   String^ str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)