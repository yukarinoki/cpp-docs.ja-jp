---
description: '詳細情報: リフレクション (C++/CLI)'
title: リフレクション (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
ms.openlocfilehash: a3a9a33a239ec678279455ea41b7c60749cc0189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245799"
---
# <a name="reflection-ccli"></a>リフレクション (C++/CLI)

リフレクションでは、既知のデータ型を実行時に調査できます。 リフレクションでは、アセンブリに含まれているデータ型を列挙したり、クラス型や値型のメンバーを探索したりできます。 この処理は、コンパイル時に型が認識または参照された場合のどちらにも対応できます。 そのため、リフレクションは、開発およびコード管理ツール向けの便利な機能です。

指定されたアセンブリ名が厳密な名前であることに注意してください (「 [Strong-Named アセンブリの作成と使用](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)」を参照してください)。これには、アセンブリのバージョン、カルチャ、および署名情報が含まれます。 また、基底クラスの名前に加えて、データ型が定義されている名前空間の名前も取得できることに注目してください。

リフレクションの機能にアクセスする最も一般的な方法は、<xref:System.Object.GetType%2A> メソッドを使用することです。 このメソッドは <xref:System.Object?displayProperty=nameWithType> 、すべてのガベージコレクションクラスの派生元であるによって提供されます。

> [!NOTE]
> Microsoft C++ コンパイラでビルドされた .exe のリフレクションは、.exe が **/clr: pure** または **/clr: safe** コンパイラオプションを使用してビルドされている場合にのみ許可されます。 **/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 では使用できません。 詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md) 」を参照してください。

詳細については、「<xref:System.Reflection>」を参照してください。

## <a name="example-gettype"></a>例: GetType

`GetType` メソッドは、オブジェクトが基になっている場合は型を表す <xref:System.Type> クラス オブジェクトへのポインターを返します。 ( **型** オブジェクトには、インスタンス固有の情報が含まれていません)。このような項目の1つに、型の完全名があります。これは次のように表示できます。

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

メソッドと同様に、 `GetType` [typeid](../extensions/typeid-cpp-component-extensions.md)演算子は **型** オブジェクトへのポインターを返すため、このコードは型名 system.string を示します。 型名を表示することは、リフレクションの最も基本的な機能ですが、より便利であると思われるのが、列挙型の有効な値を調査または探索できる点です。 これを行うには、static **Enum:: GetNames** 関数を使用します。この関数は、文字列の配列を返します。各文字列には、テキスト形式の列挙値が含まれています。  次の例では、 **Options** (CLR) 列挙型の値の列挙値を記述する文字列の配列を取得し、それらをループに表示します。

4番目のオプションを **Options** 列挙に追加した場合、列挙が別のアセンブリで定義されていても、このコードは再コンパイルせずに新しいオプションを報告します。

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

## <a name="example-gettype-members-and-properties"></a>例: GetType のメンバーとプロパティ

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

## <a name="example-enumeration-of-types"></a>例: 型の列挙体

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

## <a name="example-inspection-of-assemblies"></a>例: アセンブリの検査

このコードを vcpp_reflection_6.dll という DLL にコンパイルすると、リフレクションを使用してアセンブリの内容を確認できます。 これには、静的なリフレクション API 関数 xref: system.object% 2A? displayProperty = nameWithType を使用したアセンブリの読み込みが含まれます。 この関数は、内のモジュールと型についてクエリを実行できる **アセンブリ** オブジェクトのアドレスを返します。

リフレクションシステムによってアセンブリが正常に読み込まれると、 **型** オブジェクトの配列が関数を使用して取得され <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> ます。 各配列要素には、異なる型の情報が含まれています。ただし、この例で定義されているクラスは 1 つだけです。 ループを使用すると、この配列内の各 **型** は、 **Type:: getmembers** 関数を使用して型のメンバーについてクエリを実行します。 この関数は、 **MethodInfo** オブジェクトの配列を返します。各オブジェクトには、メンバー関数、データメンバー、または型のプロパティに関する情報が含まれています。

メソッドの一覧には、 **TestClass** で明示的に定義された関数と、 **System:: Object** クラスから暗黙的に継承される関数が含まれていることに注意してください。 Visual C++ 構文ではなく .NET で記述されている部分では、プロパティは get 関数と set 関数でアクセスする基底のデータ メンバーとして表示されます。 get 関数と set 関数は、通常のメソッドとしてこのリストに表示されています。 リフレクションは、Microsoft C++ コンパイラではなく、共通言語ランタイムによってサポートされています。

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

## <a name="how-to-implement-a-plug-in-component-architecture-using-reflection"></a><a name="implement"></a> 方法: リフレクションを使用して Plug-In コンポーネントアーキテクチャを実装する

次のコード例は、単純な "プラグイン" アーキテクチャを実装するためのリフレクションの使用方法を示しています。 最初の一覧はアプリケーションで、2つ目はプラグインです。 アプリケーションは、コマンドライン引数として提供されたプラグイン DLL 内のフォームベースのクラスを使用して、それ自体を作成する複数のドキュメント形式です。

アプリケーションは、メソッドを使用して、指定されたアセンブリを読み込もうとし <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> ます。 成功した場合、アセンブリ内の型は、メソッドを使用して列挙され <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> ます。 その後、メソッドを使用して、各型の互換性がチェックされ <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> ます。 この例では、提供されたアセンブリ内のクラスは、 <xref:System.Windows.Forms.Form> プラグインとして修飾されるクラスから派生する必要があります。

互換性のあるクラスは、メソッドを使用してインスタンス化され <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> ます。このメソッドは、を <xref:System.Type> 引数として受け取り、新しいインスタンスへのポインターを返します。 次に、新しいインスタンスがフォームにアタッチされて表示されます。

メソッドでは、 <xref:System.Reflection.Assembly.Load%2A> ファイル拡張子を含むアセンブリ名を使用できないことに注意してください。 アプリケーションの main 関数は、指定されたすべての拡張機能をトリミングします。そのため、次のコード例はいずれの場合でも機能します。

### <a name="example"></a>例

次のコードは、プラグインを受け入れるアプリケーションを定義します。最初の引数としてアセンブリ名を指定する必要があります。 このアセンブリには、少なくとも1つのパブリック派生型が含まれている必要があり <xref:System.Windows.Forms.Form> ます。

```cpp
// plugin_application.cpp
// compile with: /clr /c
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;

ref class PluggableForm : public Form  {
public:
   PluggableForm() {}
   PluggableForm(Assembly^ plugAssembly) {
      Text = "plug-in example";
      Size = Drawing::Size(400, 400);
      IsMdiContainer = true;

      array<Type^>^ types = plugAssembly->GetTypes( );
      Type^ formType = Form::typeid;

      for (int i = 0 ; i < types->Length ; i++) {
         if (formType->IsAssignableFrom(types[i])) {
            // Create an instance given the type description.
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));
            if (f) {
               f->Text = types[i]->ToString();
               f->MdiParent = this;
               f->Show();
            }
         }
      }
   }
};

int main() {
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");
   Application::Run(gcnew PluggableForm(a));
}
```

### <a name="example"></a>例

次のコードは、から派生した3つのクラスを定義し <xref:System.Windows.Forms.Form> ます。 生成されたアセンブリ名の名前が前の一覧の実行可能ファイルに渡されると、コンパイル時にそれらの3つのクラスがすべて検出され、インスタンス化されます。

```cpp
// plugin_assembly.cpp
// compile with: /clr /LD
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;
using namespace System::Drawing;

public ref class BlueForm : public Form {
public:
   BlueForm() {
      BackColor = Color::Blue;
   }
};

public ref class CircleForm : public Form {
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);
   }
};

public ref class StarburstForm : public Form {
public:
   StarburstForm(){
      BackColor = Color::Black;
   }
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      Pen^ p = gcnew Pen(Color::Red, 2);
      Random^ r = gcnew Random( );
      Int32 w = ClientSize.Width;
      Int32 h = ClientSize.Height;
      for (int i=0; i<100; i++) {
         float x1 = w / 2;
         float y1 = h / 2;
         float x2 = r->Next(w);
         float y2 = r->Next(h);
         args->Graphics->DrawLine(p, x1, y1, x2, y2);
      }
   }
};
```

## <a name="how-to-enumerate-data-types-in-assemblies-using-reflection"></a><a name="enumerate"></a> 方法: リフレクションを使用してアセンブリ内のデータ型を列挙する

次のコードは、を使用したパブリック型とメンバーの列挙を示して <xref:System.Reflection> います。

ローカルディレクトリまたは GAC にアセンブリの名前が指定されている場合、次のコードはアセンブリを開き、説明を取得しようとします。 成功した場合、各型はパブリックメンバーと共に表示されます。

で <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> は、ファイル拡張子を使用しないことが必要です。 したがって、コマンドライン引数として "mscorlib.dll" を使用すると失敗しますが、"mscorlib" だけを使用すると、.NET Framework の種類が表示されます。 アセンブリ名が指定されていない場合、コードは現在のアセンブリ内の型を検出して報告します (このコードによって生成される EXE)。

### <a name="example"></a>例

```cpp
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

- [C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
