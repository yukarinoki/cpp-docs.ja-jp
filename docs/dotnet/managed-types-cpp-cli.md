---
title: マネージド型 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], managed
- managed data types [C++]
- .NET Framework [C++], managed types
- data types [C++], .NET feature access
- main function, in managed applications
- managed code, main() function
- .NET Framework [C++], C++ equivalents
- __nogc type declarations
- __value keyword, issues when nesting
- equality, testing for
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 679b8ed3-d966-4a0c-b627-2a3f3ec96b74
ms.openlocfilehash: c542151bda780e5306db35049d988e6514fffd62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225606"
---
# <a name="managed-types-ccli"></a>マネージド型 (C++/CLI)

Visual C++ を使用すると、共通言語ランタイムの機能をサポートするマネージ型を使用して .NET 機能にアクセスでき、ランタイムの利点と制限が適用されます。

## <a name="managed-types-and-the-main-function"></a><a name="main_functions"></a>マネージ型と main 関数

を使用してアプリケーションを作成する場合 **`/clr`** 、 **main ()** 関数の引数をマネージ型にすることはできません。

適切な署名の例を次に示します。

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="net-framework-equivalents-to-c-native-types"></a><a name="dotnet"></a>.NET Framework C++ ネイティブ型に相当します。

次の表は、**システム**名前空間の定義済みの型のエイリアスである組み込み Visual C++ 型のキーワードを示しています。

|Visual C++ の種類|.NET Framework 型|
|-----------------------|-------------------------|
|**`void`**|<xref:System.Void?displayProperty=nameWithType>|
|**`bool`**|<xref:System.Boolean?displayProperty=nameWithType>|
|**`signed char`** |<xref:System.SByte?displayProperty=nameWithType>|
|**`unsigned char`**|<xref:System.Byte?displayProperty=nameWithType>|
|**`wchar_t`**|<xref:System.Char?displayProperty=nameWithType>|
|**`short`** および **`signed short`**|<xref:System.Int16?displayProperty=nameWithType>|
|**`unsigned short`**|<xref:System.UInt16?displayProperty=nameWithType>|
|**`int`**、 **`signed int`** 、 **`long`** 、および**`signed long`**|<xref:System.Int32?displayProperty=nameWithType>|
|**`unsigned int`** および **`unsigned long`**|<xref:System.UInt32?displayProperty=nameWithType>|
|**`__int64`** および **`signed __int64`**|<xref:System.Int64?displayProperty=nameWithType>|
|**`unsigned __int64`**|<xref:System.UInt64?displayProperty=nameWithType>|
|**`float`**|<xref:System.Single?displayProperty=nameWithType>|
|**`double`** および **`long double`**|<xref:System.Double?displayProperty=nameWithType>|

コンパイラオプションの既定値をまたはに設定する方法の詳細につい **`signed char`** **`unsigned char`** ては、「 [ `/J` (既定 **`char`** の型は **`unsigned`** )](../build/reference/j-default-char-type-is-unsigned.md)」を参照してください。

## <a name="version-issues-for-value-types-nested-in-native-types"></a><a name="version_issues"></a>ネイティブ型で入れ子になっている値型のバージョンの問題

クライアントアセンブリを構築するために使用される署名済みの (厳密な名前の) アセンブリコンポーネントを考えてみます。 コンポーネントには、ネイティブ共用体、クラス、または配列のメンバーの型としてクライアントで使用される値の型が含まれています。 コンポーネントの将来のバージョンで値の型のサイズまたはレイアウトが変更された場合は、クライアントを再コンパイルする必要があります。

[sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) () を使用してキーキーを作成 `sn -k mykey.snk` します。

### <a name="example"></a>例

コンポーネントの例を次に示します。

```cpp
// nested_value_types.cpp
// compile with: /clr /LD
using namespace System::Reflection;
[assembly:AssemblyVersion("1.0.0.*"),
assembly:AssemblyKeyFile("mykey.snk")];

public value struct S {
   int i;
   void Test() {
      System::Console::WriteLine("S.i = {0}", i);
   }
};
```

### <a name="example"></a>例

このサンプルは、クライアントです。

```cpp
// nested_value_types_2.cpp
// compile with: /clr
#using <nested_value_types.dll>

struct S2 {
   S MyS1, MyS2;
};

int main() {
   S2 MyS2a, MyS2b;
   MyS2a.MyS1.i = 5;
   MyS2a.MyS2.i = 6;
   MyS2b.MyS1.i = 10;
   MyS2b.MyS2.i = 11;

   MyS2a.MyS1.Test();
   MyS2a.MyS2.Test();
   MyS2b.MyS1.Test();
   MyS2b.MyS2.Test();
}
```

### <a name="output"></a>出力

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>説明

ただし、別のメンバーを `struct S` nested_value_types .cpp (など) に追加し、クライアントを `double d;` 再コンパイルせずにコンポーネントを再コンパイルした場合、結果はハンドルされない例外 (型) になり <xref:System.IO.FileLoadException?displayProperty=fullName> ます。

## <a name="how-to-test-for-equality"></a><a name="test_equality"></a>方法: 等しいかどうかをテストする

次の例では、Managed Extensions for C++ を使用する等しいかどうかのテストは、ハンドルが参照している内容に基づいています。

### <a name="example"></a>例

```cpp
// mcppv2_equality_test.cpp
// compile with: /clr /LD
using namespace System;

bool Test1() {
   String ^ str1 = "test";
   String ^ str2 = "test";
   return (str1 == str2);
}
```

このプログラムの IL は、op_Equality の呼び出しを使用して戻り値が実装されていることを示しています。

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="how-to-diagnose-and-fix-assembly-compatibility-problems"></a><a name="diagnose_fix"></a>方法: アセンブリの互換性の問題を診断および修正する

このトピックでは、コンパイル時に参照されるアセンブリのバージョンが、実行時に参照されるアセンブリのバージョンと一致しない場合に発生する可能性があることと、この問題を回避する方法について説明します。

アセンブリがコンパイルされると、他のアセンブリが構文で参照される可能性があり `#using` ます。 コンパイル中に、これらのアセンブリはコンパイラによってアクセスされます。 これらのアセンブリからの情報は、最適化に関する決定を行うために使用されます。

ただし、参照されたアセンブリを変更して再コンパイルした場合、それに依存している参照元のアセンブリを再コンパイルしないと、アセンブリに互換性がない可能性があります。 最初に有効であった最適化の決定は、新しいアセンブリバージョンに対して正しくない可能性があります。 これらの非互換性のために、さまざまなランタイムエラーが発生する可能性があります。 このような場合に生成される特定の例外はありません。 実行時にエラーが報告される方法は、問題の原因となったコードの変更の性質によって異なります。

製品のリリース版に対してアプリケーション全体が再構築されている限り、これらのエラーは最終的な運用コードでは問題にならないようにしてください。 パブリックにリリースされるアセンブリは、正式なバージョン番号でマークする必要があります。これにより、これらの問題が回避されます。 詳細については、「[アセンブリのバージョン管理](/dotnet/framework/app-domains/assembly-versioning)」を参照してください。

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>非互換性エラーの診断と修正

1. 別のアセンブリを参照するコードで発生するランタイム例外またはその他のエラー条件が発生し、その他の原因が特定されない場合は、古いアセンブリを処理している可能性があります。

1. まず、例外またはその他のエラー状態を特定し、再現します。 古い例外が原因で発生する問題は、再現できます。

1. アプリケーションで参照されているアセンブリのタイムスタンプを確認します。

1. 参照されたアセンブリのタイムスタンプがアプリケーションの前回のコンパイルのタイムスタンプよりも後である場合、アプリケーションは最新ではありません。 このような場合は、最新のアセンブリを使用してアプリケーションを再コンパイルし、コードを変更する必要があります。

1. アプリケーションを再実行し、問題を再現する手順を実行して、例外が発生していないことを確認します。

### <a name="example"></a>例

次のプログラムは、メソッドのアクセシビリティを減らし、再コンパイルせずに別のアセンブリのメソッドにアクセスしようとすることで、この問題を示しています。 最初にコンパイルしてみてください `changeaccess.cpp` 。 これは、変更される参照アセンブリです。 次に、をコンパイル `referencing.cpp` します。 コンパイルは成功します。 ここで、呼び出されたメソッドのアクセシビリティを下げます。 `changeaccess.cpp`フラグを使用して再コンパイル `/DCHANGE_ACCESS` します。 これにより、メソッドはプライベートではなく、保護されるため、合法的に呼び出すことができます。 再コンパイルせず `referencing.exe` に、アプリケーションを再実行します。 例外 <xref:System.MethodAccessException> が発生します。

```cpp
// changeaccess.cpp
// compile with: /clr:safe /LD
// After the initial compilation, add /DCHANGE_ACCESS and rerun
// referencing.exe to introduce an error at runtime. To correct
// the problem, recompile referencing.exe

public ref class Test {
#if defined(CHANGE_ACCESS)
protected:
#else
public:
#endif

  int access_me() {
    return 0;
  }

};
```

```cpp
// referencing.cpp
// compile with: /clr:safe
#using <changeaccess.dll>

// Force the function to be inline, to override the compiler's own
// algorithm.
__forceinline
int CallMethod(Test^ t) {
  // The call is allowed only if access_me is declared public
  return t->access_me();
}

int main() {
  Test^ t = gcnew Test();
  try
  {
    CallMethod(t);
    System::Console::WriteLine("No exception.");
  }
  catch (System::Exception ^ e)
  {
    System::Console::WriteLine("Exception!");
  }
  return 0;
}
```

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[他の .NET 言語との相互運用性 (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)<br/>
[マネージ型 (C++/CLI)](../dotnet/managed-types-cpp-cli.md)<br/>
[#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)
