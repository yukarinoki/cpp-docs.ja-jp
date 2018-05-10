---
title: '方法: リフレクションを使用してデータの種類の列挙 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5a4b85cb5af9d390d92bcca3e0462b0ae5b4d832
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-data-types-in-assemblies-using-reflection-ccli"></a>方法: リフレクションを使用してアセンブリ内のデータ型を列挙する (C++/CLI)
次の例では、パブリック型とメンバーを使用しての列挙体<xref:System.Reflection>です。  
  
 ローカル ディレクトリまたは GAC にアセンブリの名前で指定された、次のコードは、アセンブリを開くし、説明の取得を試みます。 成功した場合は、種類ごとに、そのパブリック メンバーが表示されます。  
  
 なお<xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>ファイル拡張子が使用されていないことが必要です。 したがって、"mscorlib.dll"を使用して、コマンドライン引数は失敗、単なる"mscorlib"を使用すると、.NET Framework の型の表示中にします。 アセンブリ名が指定されていない場合、コードが検出され、現在のアセンブリ内の型 (このコードにより生成された EXE) を報告します。  
  
## <a name="example"></a>例  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [リフレクションの問題 (C++/CLI)](../dotnet/reflection-cpp-cli.md)