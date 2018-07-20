---
title: '#using ディレクティブ (C +/cli CLI) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
dev_langs:
- C++
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2255f5de9cc26505bb07110da6368a039009c6c
ms.sourcegitcommit: b8b1cba85ff423142d73c888be26baa8c33f3cdc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2018
ms.locfileid: "39093034"
---
# <a name="using-directive-ccli"></a>#using ディレクティブ (C +/cli CLI)
コンパイルされたプログラムにメタデータをインポート[/clr](../build/reference/clr-common-language-runtime-compilation.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
#using file [as_friend]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `file`  
 MSIL .dll、.exe、.netmodule、または .obj。たとえば、オブジェクトに適用された  
  
 `#using <MyComponent.dll>`  
  
 as_friend  
 `file` のすべての型にアクセスできることを指定します。  詳細については、次を参照してください。[フレンド アセンブリ (C++)](../dotnet/friend-assemblies-cpp.md)します。  
  
## <a name="remarks"></a>Remarks  
 `file` は、マネージ データとマネージ構造のためにインポートする Microsoft Intermediate Language (MSIL) ファイルにすることができます。 ビルドしているアセンブリが一覧表示の .dll ファイルには、アセンブリ マニフェストが含まれていて、マニフェストで参照されているすべての .dll がインポートされる場合*ファイル*アセンブリ参照としてメタデータ内で。  
  
 場合`file`アセンブリが含まれていない (場合`file`モジュール) だけモジュールが一部であることを示すオプションが現在の (アセンブリ) アプリケーションで、モジュールから型情報を使用する予定がない場合、アセンブリとを使用してください[/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)します。 その場合、アセンブリを参照するすべてのアプリケーションで、そのモジュール内の型を使用できます。  
  
 使用する代わりに`#using`は、 [/FU](../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプション。  
  
 渡される .exe アセンブリ`#using`コンパイルする必要があります、Visual Studio の .NET コンパイラ (Visual Basic または Visual c#、たとえば) のいずれかを使用します。  コンパイルされた .exe アセンブリからメタデータをインポートしようとしています。 **/clr**ファイルの読み込み例外が発生します。  
  
> [!NOTE]
>  `#using` で参照されるコンポーネントは、コンパイル時にインポートされる別バージョンのファイルで実行することもできるため、クライアント アプリケーションで予期しない結果になります。  
  
 モジュールではなくアセンブリ内の型をコンパイラで認識するには、型の解決を強制する必要があります。型の解決を実行するには、たとえば、型のインスタンスを定義します。 アセンブリの型名を解決する方法は他にもあります。たとえば、アセンブリの型を継承すると、コンパイラで型名が認識されます。  
  
 使用するソース コードから構築されたメタデータをインポートするときに[_declspec](../cpp/thread.md)スレッドのセマンティクスはメタデータで保持されません。 たとえば、変数を使用して宣言 **_declspec**では、.NET Framework 共通言語ランタイムのビルドを使用して、インポートするプログラムをコンパイル`#using`はなくなります **_ _declspec (スレッド)** 変数のセマンティクスです。  
  
 `#using` によって参照されるファイル内のインポートされるすべての型 (マネージドとネイティブの両方) を使用できますが、コンパイラはネイティブ型を定義ではなく宣言として扱います。  
  
 コンパイルすると、mscorlib.dll が自動的に参照 **/clr**します。  
  
 LIBPATH 環境変数は、`#using` に渡されたファイル名をコンパイラが解決しようとするときに検索されるディレクトリを指定します。  
  
 コンパイラは、次のパスに従って参照を検索します。  
  
-   `#using` ステートメントで指定されたパス。  
  
-   現在のフォルダー。  
  
-   .NET Framework のシステム ディレクトリ。  
  
-   追加されたディレクトリ、 [/AI](../build/reference/ai-specify-metadata-directories.md)コンパイラ オプション。  
  
-   LIBPATH 環境変数のディレクトリ。  
  
## <a name="example"></a>例  
 アセンブリ (C) をビルドし、他のアセンブリ (A) を参照しているアセンブリ (B) を参照する場合、C で A のいずれかの型を明示的に使用するのでない限り、アセンブリ A を明示的に参照する必要はありません。  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>例  
  
```  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};  
  
```  
  
## <a name="example"></a>例  
 次の例では、using_assembly_A.cpp で定義されている型をプログラムが使用しないため、using_assembly_A.dll を参照していないことによるコンパイラ エラーは発生しません。  
  
```  
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
