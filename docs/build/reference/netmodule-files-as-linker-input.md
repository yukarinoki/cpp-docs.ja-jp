---
title: リンカー入力としての .netmodule ファイル
ms.date: 05/16/2019
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: 50a0f0a1ff5f65a7512e8372de2fe5296c866dca
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837425"
---
# <a name="netmodule-files-as-linker-input"></a>リンカー入力としての .netmodule ファイル

link.exe は MSIL の .obj と .netmodules を入力として受け取るようになりました。 リンカーによって生成される出力ファイルは、リンカーに入力された .obj または .netmodules のいずれにも実行時の依存関係がないアセンブリまたは .netmodule です。

.netmodule を作成するには、MSVC コンパイラで [/LN (MSIL モジュールの作成)](ln-create-msil-module.md) を使用するか、リンカーで [/NOASSEMBLY (MSIL モードの作成)](noassembly-create-a-msil-module.md) を使用します。 .obj は常に Visual C++ コンパイルで作成されます。 他の Visual Studio コンパイラの場合は、 **/target:module** コンパイラ オプションを使用します。

リンカーには、.netmodule を作成した Visual C++ コンパイルからの .obj ファイルを渡す必要があります。 .netmodule で渡す方法はサポートされなくなりました。 **/clr:pure** および **/clr:safe** コンパイラ オプションは Visual Studio 2015 では非推奨とされており、Visual Studio 2017 以降ではサポートされなくなったためです。

コマンド ラインからリンカーを呼び出す方法については、「[リンカー コマンドラインの構文](linking.md)」、「[Use the MSVC toolset from the command line](../building-on-the-command-line.md)」(コマンド ラインから MSVC ツールセットを使用する)、および「[Set the Path and Environment Variables for Command-Line Builds](../setting-the-path-and-environment-variables-for-command-line-builds.md)」(コマンドライン ビルドのパスと環境変数を設定する) を参照してください。

**/clr** を指定して MSVC コンパイラでコンパイルされたリンカーに .netmodule または .dll ファイルを渡すと、リンカー エラーが発生する可能性があります。 詳細については、「[.netmodule 入力ファイルの形式の選択](choosing-the-format-of-netmodule-input-files.md)」を参照してください。

リンカーは、ネイティブの .obj ファイルだけでなく、 **/clr** を指定してコンパイルされた MSIL .obj ファイルも受け入れます。 同じビルドに混在する .objs を渡すと、生成される出力ファイルの検証可能性は、既定で入力モジュールの最低レベルの検証可能性と等しくなります。

現在、複数のアセンブリで構成されるアプリケーションがあり、そのアプリケーションを 1 つのアセンブリに含める場合は、アセンブリを再コンパイルしてから、.objs または .netmodules をリンクして 1 つのアセンブリを作成する必要があります。

実行可能イメージを作成するときは、[/ENTRY (エントリポイント シンボル)](entry-entry-point-symbol.md) を使用してエントリ ポイントを指定する必要があります。

MSIL の .obj または .netmodule ファイルとリンクする場合は [/LTCG (リンク時コード生成)](ltcg-link-time-code-generation.md) を使用します。それ以外の場合、リンカーで MSIL の .obj または .netmodule が検出されると、/LTCG を使用してリンクが再起動されます。

MSIL の .obj または .netmodule ファイルも cl.exe に渡すことができます。

入力 MSIL の .obj または .netmodule ファイルに埋め込みリソースを含めることはできません。 リソースは、[/ASSEMBLYRESOURCE (管理対象リソースの埋め込み)](assemblyresource-embed-a-managed-resource.md) リンカー オプション、または他の Visual Studio コンパイラの **/resource** コンパイラ オプションを使用して、出力ファイル (モジュールまたはアセンブリ) に埋め込まれます。

MSIL のリンク処理を実行するときに [/LTCG (リンク時コード生成)](ltcg-link-time-code-generation.md) も指定しないと、リンクが再開されていることを通知する情報メッセージが表示されます。 このメッセージは無視してもかまいませんが、MSIL リンク処理に関するリンカーのパフォーマンスを向上するには、明示的に **/LTCG** を指定してください。

## <a name="example"></a>例

C++ コードでは、対応する **try** の **catch** ブロックが非システム例外に対して呼び出されます。 ただし、既定で非システム例外は CLR によって <xref:System.Runtime.CompilerServices.RuntimeWrappedException> でラップされます。 アセンブリが Visual C++ および Visual C++ 以外のモジュールから作成されており、**try** ブロックから非システム例外がスローされたときに C++ コード内の **catch** ブロックを対応する **try** 句から呼び出すようにする場合、C++ 以外のモジュールのソース コードに `[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]` 属性を追加する必要があります。

```cpp
// MSIL_linking.cpp
// compile with: /c /clr
value struct V {};

ref struct MCPP {
   static void Test() {
      try {
         throw (gcnew V);
      }
      catch (V ^) {
         System::Console::WriteLine("caught non System exception in C++ source code file");
      }
   }
};

/*
int main() {
   MCPP::Test();
}
*/
```

## <a name="example"></a>例

`WrapNonExceptionThrows` 属性のブール値を変更することで、Visual C++ コードの機能が非システム例外をキャッチするように変更されます。

```cpp
// MSIL_linking_2.cs
// compile with: /target:module /addmodule:MSIL_linking.obj
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console
using System.Runtime.CompilerServices;

// enable non System exceptions
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]

class MLinkTest {
   public static void Main() {
      try {
         MCPP.Test();
      }
      catch (RuntimeWrappedException) {
         System.Console.WriteLine("caught a wrapped exception in C#");
      }
   }
}
```

```Output
caught non System exception in C++ source code file
```

## <a name="see-also"></a>関連項目

- [LINK の入力ファイル](link-input-files.md)
- [MSVC リンカー オプション](linker-options.md)
