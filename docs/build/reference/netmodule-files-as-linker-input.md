---
title: リンカー入力としての .netmodule ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
ms.openlocfilehash: fcba363cff567c69ac0fbd0a541953dfe2c8e910
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818103"
---
# <a name="netmodule-files-as-linker-input"></a>リンカー入力としての .netmodule ファイル

link.exe では、入力として MSIL .obj と .netmodule を今すぐ受け取ります。 リンカーによって生成された出力ファイルは、アセンブリまたは .netmodule をリンカーに入力した .netmodule または .obj のいずれかで実行時に依存せずします。

.netmodule は、MSVC コンパイラによって作成された[/LN (MSIL モジュールの作成)](ln-create-msil-module.md)またはのリンカーによって[/NOASSEMBLY (MSIL モジュールの作成)](noassembly-create-a-msil-module.md)します。 .obj は常に、Visual C のコンパイル時に作成されます。 その他の Visual Studio コンパイラを使用して、 **/target:module**コンパイラ オプション。

必要がありますリンカーに渡す .obj ファイルを .netmodule を作成した Visual C コンパイラから。 に、.netmodule を渡すことはサポートされなく、 **/clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

コマンドラインからリンカーを呼び出す方法については、次を参照してください[リンカーのコマンドライン構文](linking.md)、[コマンドラインから MSVC ツールセットを使用して](../building-on-the-command-line.md)、および[パスと環境変数の設定。コマンド ライン ビルドの](../setting-the-path-and-environment-variables-for-command-line-builds.md)します。

MSVC コンパイラをしてコンパイルされたリンカーに .netmodule または .dll ファイルを渡す **/clr**リンカー エラーが発生することができます。 詳細については、次を参照してください。 [.netmodule 入力ファイルの形式を選択する](choosing-the-format-of-netmodule-input-files.md)します。

リンカーは、ネイティブの .obj ファイルだけでコンパイルされた MSIL .obj ファイルを受け入れる **/clr**します。 同じビルドで混合の .obj を渡すと、生成される出力ファイルの検証可能性は、既定では、最低レベルの入力モジュールの検証可能性と等しくなります。

現在 2 つ以上のアセンブリで構成されるアプリケーションがある、1 つのアセンブリに含まれるよう、アプリケーションをたい場合は、、アセンブリを再コンパイルを .obj または 1 つのアセンブリを生成するために .netmodule をリンクする必要があります。

使用してエントリ ポイントを指定する必要があります[/ENTRY (エントリ ポイント シンボル)](entry-entry-point-symbol.md)実行可能イメージを作成するときにします。

MSIL .netmodule、または .obj ファイルを使用してリンクする場合を使用して、 [/LTCG (リンク時コード生成)](ltcg-link-time-code-generation.md)、それ以外の場合、リンカーには、MSIL .obj または .netmodule が検出されると、再起動されます/LTCG をリンクします。

MSIL .netmodule、または .obj ファイルは、cl.exe に渡すこともできます。

入力の MSIL .obj または .netmodule ファイルには、リソースを埋め込むことはできませんができます。 リソースは、出力ファイル (モジュールまたはアセンブリ) に組み込まれています[/ASSEMBLYRESOURCE (マネージ リソースの埋め込み)](assemblyresource-embed-a-managed-resource.md)リンカー オプション、または、 **/resource**他の Visual Studio コンパイラでコンパイラ オプション。

指定しない場合、MSIL は、次のリンクを実行するときに[/LTCG (リンク時コード生成)](ltcg-link-time-code-generation.md)リンクを再起動することを通知する情報メッセージが表示されます。 このメッセージに、MSIL リンクのリンカーのパフォーマンスを向上しますが、無視できるを明示的に指定 **/LTCG**します。

## <a name="example"></a>例

C++ コードで、**キャッチ**の対応するブロック**お試しください**システム以外の例外が呼び出されます。 ただし、既定では、CLR システム以外の例外をラップで<xref:System.Runtime.CompilerServices.RuntimeWrappedException>します。 Visual C および Visual C 以外のモジュールからアセンブリが作成されたときと、実行する、**キャッチ**、対応するから呼び出される C++ コードのブロック**お試しください**句と、 **をお試しください**ブロックが、システム以外の例外をスローする必要がありますを追加する、`[assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)]`属性以外の C++ モジュールのソース コードをします。

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

ブール値を変更することで、`WrapNonExceptionThrows`属性に、システム以外の例外をキャッチする Visual C コードの機能を変更します。

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
