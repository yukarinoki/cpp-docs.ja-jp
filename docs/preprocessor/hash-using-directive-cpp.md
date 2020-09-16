---
title: '#using ディレクティブ (C++/CLI)'
ms.date: 08/29/2019
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
ms.openlocfilehash: 0245eb15219585421be83def0258415ab4b573b6
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684262"
---
# <a name="using-directive-ccli"></a>#using ディレクティブ (C++/CLI)

[/Clr](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルされたプログラムにメタデータをインポートします。

## <a name="syntax"></a>構文

> **`#using`***ファイル*[ **`as_friend`** ]

### <a name="parameters"></a>パラメーター

*拡張子*\
Microsoft 中間言語 (MSIL) *`.dll`* 、 *`.exe`* 、、 *`.netmodule`* または *`.obj`* ファイル。 たとえば、次のように入力します。

`#using <MyComponent.dll>`

**`as_friend`**\
*ファイル*内のすべての型がアクセス可能であることを指定します。 詳細については、「 [フレンドアセンブリ (C++)](../dotnet/friend-assemblies-cpp.md)」を参照してください。

## <a name="remarks"></a>注釈

*ファイル* は、マネージデータとマネージコンストラクト用にインポートする Microsoft 中間言語 (MSIL) ファイルにすることができます。 DLL にアセンブリマニフェストが含まれている場合は、マニフェストで参照されるすべての Dll がインポートされます。 作成中のアセンブリによって、メタデータ内の *ファイル* がアセンブリ参照として一覧表示されます。

*ファイル*にアセンブリが含まれていない (*ファイル*がモジュールである) 場合、現在の (アセンブリ) アプリケーションのモジュールからの型情報を使用しないことが考えられます。 [/Assemblymodule](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)を使用して、モジュールがアセンブリの一部であることを示すことができます。 その場合、アセンブリを参照するすべてのアプリケーションで、そのモジュール内の型を使用できます。

使用する代わりに、 **`#using`** [/fu](../build/reference/fu-name-forced-hash-using-file.md) コンパイラオプションを使用することもできます。

に渡される .exe アセンブリは **`#using`** 、.Net Visual Studio コンパイラ (Visual Basic または Visual C# など) のいずれかを使用してコンパイルする必要があります。  でコンパイルされた .exe アセンブリからメタデータをインポートしようとすると **`/clr`** 、ファイル読み込み例外が発生します。

> [!NOTE]
> で参照されるコンポーネントは、 **`#using`** コンパイル時にインポートされた別のバージョンのファイルで実行できます。これにより、クライアントアプリケーションで予期しない結果が発生します。

コンパイラがアセンブリ (モジュールではありません) 内の型を認識できるようにするには、型を強制的に解決する必要があります。 これは、たとえば、型のインスタンスを定義することによって強制的に行うことができます。 コンパイラのアセンブリの型名を解決する方法は他にもあります。 たとえば、アセンブリ内の型から継承する場合、型名はコンパイラに認識されます。

使用するソースコードからビルドされたメタデータをインポートする場合 [`__declspec(thread)`](../cpp/thread.md) 、スレッドのセマンティクスはメタデータに保存されません。 たとえば、として宣言 **`__declspec(thread)`** され、.NET Framework 共通言語ランタイム用に構築されたプログラムでコンパイルされた変数と、を使用してインポートされた変数には、 **`#using`** **`__declspec(thread)`** 変数に対するセマンティクスがありません。

によって参照されるファイル内のインポートされたすべての型 (マネージとネイティブの両方) **`#using`** は使用できますが、コンパイラはネイティブ型を定義ではなく宣言として扱います。

mscorlib.dll は、を使用してコンパイルするときに自動的に参照され **`/clr`** ます。

LIBPATH 環境変数は、コンパイラがに渡されたファイル名を解決するときに検索するディレクトリを指定し **`#using`** ます。

コンパイラは、次のパスに従って参照を検索します。

- ステートメントで指定されたパス **`#using`** 。

- 現在のフォルダー。

- .NET Framework のシステム ディレクトリ。

- コンパイラオプションを使用して追加されたディレクトリ [`/AI`](../build/reference/ai-specify-metadata-directories.md) 。

- LIBPATH 環境変数のディレクトリ。

## <a name="examples"></a>例

第3のアセンブリを参照する2番目のアセンブリを参照するアセンブリを構築できます。 型のいずれかを明示的に使用する場合にのみ、最初のアセンブリから3番目のアセンブリを明示的に参照する必要があります。

```cpp
// using_assembly_A.cpp
// compile with: /clr /LD
public ref class A {};
```

```cpp
// using_assembly_B.cpp
// compile with: /clr /LD
#using "using_assembly_A.dll"
public ref class B {
public:
   void Test(A a) {}
   void Test() {}
};
```

次の例では、コンパイラは、 *using_assembly_A.dll*の参照に関するエラーを報告しません。これは、プログラムが *using_assembly_A .cpp*で定義されている型を使用しないためです。

```cpp
// using_assembly_C.cpp
// compile with: /clr
#using "using_assembly_B.dll"
int main() {
   B b;
   b.Test();
}
```

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
