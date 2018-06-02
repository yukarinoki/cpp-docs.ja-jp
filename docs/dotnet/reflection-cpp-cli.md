---
title: リフレクション (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d41d7f627a50dd1a09f4256fbd8448d82c6d5f27
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705245"
---
# <a name="reflection-ccli"></a>リフレクション (C++/CLI)

リフレクションでは、既知のデータ型を実行時に調査できます。 リフレクションでは、アセンブリに含まれているデータ型を列挙したり、クラス型や値型のメンバーを探索したりできます。 この処理は、コンパイル時に型が認識または参照された場合のどちらにも対応できます。 そのため、リフレクションは、開発およびコード管理ツール向けの便利な機能です。

指定されたアセンブリ名が厳密な名前に注意してください (を参照してください[作成と使用](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies))、アセンブリのバージョン、カルチャ、および署名情報が含まれます。 また、基底クラスの名前に加えて、データ型が定義されている名前空間の名前も取得できることに注目してください。

リフレクションの機能にアクセスする最も一般的な方法は、<xref:System.Object.GetType%2A> メソッドを使用することです。 このメソッドはによって提供される[system::object](https://msdn.microsoft.com/en-us/library/system.object.aspx)からガベージ コレクションのすべてのクラスが派生します。

> [!NOTE]
> .Exe がでビルドされた場合は、Visual C コンパイラでビルドした .exe でリフレクションを使用できるのみ、 **/clr: 純粋な**または **/clr:safe**コンパイラ オプション。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨と Visual Studio 2017 では使用できません。 参照してください[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)詳細についてはします。

詳細については、次を参照してください[System.Reflection Namespace。](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)

## <a name="example-gettype"></a>例: GetType

`GetType` メソッドは、オブジェクトが基になっている場合は型を表す <xref:System.Type> クラス オブジェクトへのポインターを返します。 (、**型**オブジェクトにすべてのインスタンスに固有の情報が含まれていません)。このメソッドで取得できる項目には、型の完全名があります。完全名は、次のように表示できます。

型名には、型が定義されている完全なスコープ (名前空間も含む) が含まれています。また、.NET 構文でスコープ解決演算子としてドット (.) が付けられている点にも注意してください。

```cpp
// vcpp_reflection.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^ s = "sample string";
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());
}
```

```Output
full type name of 'sample string' is 'System.String'
```

## <a name="example-boxed-value-types"></a>例: ボックス化された値型

値型を `GetType` 関数で使用する場合も、最初にボックス化する必要があります。

```cpp
// vcpp_reflection_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Int32 i = 100; 
   Object ^ o = i;
   Console::WriteLine("type of i = '{0}'", o->GetType());
}
```

```Output
type of i = 'System.Int32'
```

## <a name="example-typeid"></a>例: typeid

同様、 `GetType` 、メソッド、 [typeid](../windows/typeid-cpp-component-extensions.md)演算子へのポインターを返します、**型**オブジェクト、このコードは、型名を示すため**System.Int32**です。 型名を表示することは、リフレクションの最も基本的な機能ですが、より便利であると思われるのが、列挙型の有効な値を調査または探索できる点です。 静的なを使用してこれ行う**enum::getnames**関数は、それぞれがテキスト形式で列挙値を含む文字列の配列が返されます。  次の例の列挙の値を表す文字列の配列を取得する、**オプション**(CLR) 列挙され、ループ内に表示されます。

4 番目のオプションを追加する場合、**オプション**列挙型では、このコードには、列挙体が別のアセンブリで定義されている場合でも、再コンパイルせず新しいオプションが報告されます。

```cpp
// vcpp_reflection_3.cpp
// compile with: /clr
using namespace System;

enum class Options {   // not a native enum
   Option1, Option2, Option3
};

int main() {
   array<String^>^ names = Enum::GetNames(Options::typeid);

   Console::WriteLine("there are {0} options in enum '{1}'", 
               names->Length, Options::typeid);

   for (int i = 0 ; i < names->Length ; i++)
      Console::WriteLine("{0}: {1}", i, names[i]);

   Options o = Options::Option2;
   Console::WriteLine("value of 'o' is {0}", o);
}
```

```Output
there are 3 options in enum 'Options'
0: Option1
1: Option2
2: Option3
value of 'o' is Option2
```

## <a name="example-gettype-members-and-properties"></a>例: GetType メンバーおよびプロパティ

`GetType` オブジェクトは、型を調べるために使用できる多くのメンバーとプロパティをサポートします。 次のコードは、この情報の一部を取得して表示します。

```cpp
// vcpp_reflection_4.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine("type information for 'String':");
   Type ^ t = String::typeid;

   String ^ assemblyName = t->Assembly->FullName;
   Console::WriteLine("assembly name: {0}", assemblyName);

   String ^ nameSpace = t->Namespace;
   Console::WriteLine("namespace: {0}", nameSpace);

   String ^ baseType = t->BaseType->FullName;
   Console::WriteLine("base type: {0}", baseType);

   bool isArray = t->IsArray;
   Console::WriteLine("is array: {0}", isArray);

   bool isClass = t->IsClass;
   Console::WriteLine("is class: {0}", isClass);
}
```

```Output
type information for 'String':
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral, 
PublicKeyToken=b77a5c561934e089
namespace: System
base type: System.Object
is array: False
is class: True
```

## <a name="example-enumeration-of-types"></a>型の例: 列挙型

リフレクションを使用すると、アセンブリ内の型とクラス内のメンバーも列挙できます。 この機能の例を示すために、次のような単純なクラスを定義します。

```cpp
// vcpp_reflection_5.cpp
// compile with: /clr /LD
using namespace System;
public ref class TestClass {
   int m_i;
public:
   TestClass() {}
   void SimpleTestMember1() {}
   String ^ SimpleMember2(String ^ s) { return s; } 
   int TestMember(int i) { return i; }
   property int Member {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }
};
```

## <a name="example-inspection-of-assemblies"></a>アセンブリの例: 検査

このコードを vcpp_reflection_6.dll という DLL にコンパイルすると、リフレクションを使用してアセンブリの内容を確認できます。 これは、静的リフレクション API 関数を使用して[assembly::load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx)アセンブリを読み込みます。 この関数のアドレスを返します、**アセンブリ**モジュールおよび内の型は、クエリ可能なオブジェクトです。

リフレクション システム アセンブリの配列の読み込みが成功した後**型**でオブジェクトを取得、 [:gettypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx)関数。 各配列要素には、異なる型の情報が含まれています。ただし、この例で定義されているクラスは 1 つだけです。 ループを使用して各**型**この配列のクエリが実行を使用して型のメンバーについて、 **:getmembers**関数。 この関数の配列を返します**MethodInfo**オブジェクト、各オブジェクトのメンバー関数は、データ メンバー、または型のプロパティに関する情報を格納します。

定義されているメソッドの一覧に含まれている関数は、明示的に注**TestClass**関数を暗黙的に継承し、 **system::object**クラスです。 Visual C++ 構文ではなく .NET で記述されている部分では、プロパティは get 関数と set 関数でアクセスする基底のデータ メンバーとして表示されます。 get 関数と set 関数は、通常のメソッドとしてこのリストに表示されています。 リフレクションは、Visual C++ コンパイラではなく、共通言語ランタイムを通じてサポートされています。

このコードを使用すると、定義したアセンブリを調べるだけでなく、.NET アセンブリを調べることもできます。 たとえば、TestAssembly を mscorlib に置き換えると、mscorlib.dll に定義されているすべての型とメソッドのリストが表示されます。

```cpp
// vcpp_reflection_6.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;
using namespace System::Reflection;
int main() {
   Assembly ^ a = nullptr;
   try {
      // load assembly -- do not use file extension
      // will look for .dll extension first
      // then .exe with the filename
      a = Assembly::Load("vcpp_reflection_5");
   }
   catch (FileNotFoundException ^ e) {
      Console::WriteLine(e->Message);
      return -1;
   }

   Console::WriteLine("assembly info:");
   Console::WriteLine(a->FullName);
   array<Type^>^ typeArray = a->GetTypes();

   Console::WriteLine("type info ({0} types):", typeArray->Length);

   int totalTypes = 0;
   int totalMembers = 0;
   for (int i = 0 ; i < typeArray->Length ; i++) {
      // retrieve array of member descriptions
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();

      Console::WriteLine("  members of {0} ({1} members):", 
      typeArray[i]->FullName, member->Length);
      for (int j = 0 ; j < member->Length ; j++) {
         Console::Write("       ({0})", 
         member[j]->MemberType.ToString() );
         Console::Write("{0}  ", member[j]);
         Console::WriteLine("");
         totalMembers++;
      }
      totalTypes++;
   }
   Console::WriteLine("{0} total types, {1} total members",
   totalTypes, totalMembers);
}
```

## <a name="see-also"></a>関連項目

- [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
