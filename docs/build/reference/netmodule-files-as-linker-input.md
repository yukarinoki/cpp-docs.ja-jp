---
title: リンカー入力としての .netmodule ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbb2ab74e8c9d0285b9bec2f9979257d89797022
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704566"
---
# <a name="netmodule-files-as-linker-input"></a>リンカー入力としての .netmodule ファイル

link.exe では、入力として MSIL .obj と .netmodule を今すぐ受け取ります。 リンカーによって生成される出力ファイルは、アセンブリまたは依存せずに、実行時の .obj または .netmodule をリンカー入力した .netmodule です。

.netmodule がコンパイラによって作成された、Visual C で[/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)またはのリンカーによって[/NOASSEMBLY (MSIL モジュールの作成)](../../build/reference/noassembly-create-a-msil-module.md)です。 .obj は常に、Visual C のコンパイル時に作成されます。 他の Visual Studio コンパイラを使用して、 **/target:module**コンパイラ オプション。

渡す必要がありますをリンカーに .obj ファイル、.netmodule を作成した Visual C コンパイラからです。 .Netmodule に渡すことは現在サポートされていませんので、 **/clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

コマンドラインからリンカーを呼び出す方法については、次を参照してください[リンカーのコマンドライン構文](../../build/reference/linker-command-line-syntax.md)、[コマンドラインでビルドの c/c++ コード](../../build/building-on-the-command-line.md)、および[パスと環境変数の設定。コマンド ライン ビルド](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)です。

Visual C コンパイラでコンパイルされたリンカーに .netmodule または .dll ファイルを渡す **/clr**リンカー エラーが発生することができます。 詳細については、次を参照してください。 [.netmodule 入力ファイルの形式を選択する](../../build/reference/choosing-the-format-of-netmodule-input-files.md)です。

リンカーは、ネイティブ .obj ファイルだけでなくでコンパイルされた MSIL .obj ファイルを受け入れる **/clr**です。 同じビルドで混合の .obj を渡すと、結果として得られる出力ファイルの検証は、既定では、入力モジュールの検証可能性の最も低いレベルに等しくなります。

2 つ以上のアセンブリで構成されるアプリケーションが現在ある 1 つのアセンブリに含まれているアプリケーションで、使用する場合は、、アセンブリを再コンパイルを .obj または 1 つのアセンブリを生成するために .netmodule をリンクする必要があります。

エントリ ポイントを使用して、指定する必要があります[/ENTRY (エントリ ポイント シンボル)](../../build/reference/entry-entry-point-symbol.md)実行可能イメージを作成するときにします。

MSIL .obj または .netmodule ファイルを使用してリンクする場合を使用して[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)、それ以外の場合、リンカーには、MSIL .obj または .netmodule が検出されると、再起動が/LTCG をリンクします。

MSIL .obj または .netmodule ファイルは、cl.exe に渡すこともできます。

入力の MSIL .obj または .netmodule ファイルには、リソースが埋め込まれていることはできません。 リソースが (モジュールまたはアセンブリ) の出力ファイルに埋め込まれた[/ASSEMBLYRESOURCE (マネージ リソースを埋め込む)](../../build/reference/assemblyresource-embed-a-managed-resource.md)リンカー オプション、または、 **/resource**他の Visual Studio コンパイラでコンパイラ オプション。

MSIL リンクするを実行するも指定しない場合および[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)リンクが再起動することを通知する情報メッセージが表示されます。 このメッセージは、MSIL リンクでリンカーのパフォーマンスの向上をさせるのには、無視することができます、明示的に指定 **/LTCG**です。

## <a name="example"></a>例

C++ コードで、**キャッチ**の対応するブロック**再試行**システム以外の例外が呼び出されます。 ただし、既定では、CLR システム以外の例外をラップで<xref:System.Runtime.CompilerServices.RuntimeWrappedException>です。 Visual C、Visual C 以外のモジュールからアセンブリを作成するか、**キャッチ**対応から呼び出せるように C++ コードのブロック**を再試行してください**句と、 **を再試行してください**ブロックには、システム以外の例外がスローされた、追加する必要あります、`[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]`属性を非 C モジュールのソース コードにします。

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

ブール値を変更することによって、`WrapNonExceptionThrows`属性に、システム以外の例外をキャッチする Visual C コードの機能を変更します。

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

- [LINK の入力ファイル](../../build/reference/link-input-files.md)
- [リンカー オプション](../../build/reference/linker-options.md)
