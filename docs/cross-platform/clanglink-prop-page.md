---
title: Clang のリンカーのプロパティ (Android C++)
ms.date: 10/23/2017
ms.assetid: 66e88848-116c-4eb0-bc57-183394d35b57
f1_keywords:
- VC.Project.VCLinkerTool.Clang.OutputFile
- VC.Project.VCLinkerTool.Clang.Soname
- VC.Project.VCLinkerTool.Clang.ShowProgress
- VC.Project.VCLinkerTool.Clang.Version
- VC.Project.VCLinkerTool.Clang.VerboseOutput
- VC.Project.VCLinkerTool.Clang.IncrementalLink
- VC.Project.VCLinkerTool.Clang.SharedLibrarySearchPath
- VC.Project.VCLinkerTool.Clang.AdditionalLibraryDirectories
- VC.Project.VCLinkerTool.Clang.UnresolvedReferences
- VC.Project.VCLinkerTool.Clang.OptimizeForMemory
- VC.Project.VCLinkerTool.Clang.IgnoreDefaultLibraryNames
- VC.Project.VCLinkerTool.Clang.ForceSymbolReferences
- VC.Project.VCLinkerTool.Clang.ForceFileOutput
- VC.Project.VCLinkerTool.Clang.OmitDebuggerSymbolInformation
- VC.Project.VCLinkerTool.Clang.GenerateMapFile
- VC.Project.VCLinkerTool.Clang.Relocation
- VC.Project.VCLinkerTool.Clang.FunctionBinding
- VC.Project.VCLinkerTool.Clang.NoExecStackRequired
- VC.Project.VCLinkerTool.Clang.WholeArchive
- VC.Project.VCLinkerTool.Clang.AdditionalOptionsPage
- VC.Project.VCLinkerTool.Clang.AdditionalDependencies
- VC.Project.VCLinkerTool.Clang.LibraryDependencies
ms.openlocfilehash: 55b944040157d13741b992f4ec66c35d1b117d95
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79470251"
---
# <a name="clang-linker-properties-android-c"></a>Clang のリンカーのプロパティ (Android C++)

| プロパティ | 説明 | 選択 |
|--|--|--|
| 出力ファイル | このオプションは、リンカーによって作成されるプログラムの既定の名前と場所をオーバーライドします。 (-o) |
| 進行状況の表示 | リンカーの進行状況メッセージを出力します。 |
| バージョン | -version オプションは、実行ファイルのヘッダーにバージョン番号を付けるようにリンカーを設定します。 |
| 詳細出力の有効にする | -verbose オプションは、デバッグ用に詳細メッセージを出力するようにリンカーを設定します。 |
| インクリメンタル リンクを有効にする | このオプションは、インクリメンタル リンクを有効にするようにリンカーを設定します。 |
| 共有ライブラリの検索パス | 共有ライブラリの検索パスをユーザーが設定できるようにします。 |
| 追加のライブラリ ディレクトリ | 環境のライブラリ パスをユーザーがオーバーライドできるようにします。 (-L フォルダー)。 |
| 未解決のシンボル参照の報告 | このオプションは、有効になっている場合、未解決のシンボル参照を報告します。 |
| メモリ使用量の最適化 | 必要に応じてシンボル テーブルを再度読み取ることでメモリの使用量を最適化します。 |
| 特定の既定のライブラリの無視 | 無視する既定のライブラリの名前を 1 つ以上指定します。 |
| シンボル参照の強制 | 出力ファイルに未定義のシンボルとしてシンボルを入力するように強制します。 |
| デバッガー シンボル情報 | 出力ファイルのデバッガー シンボル情報。 | **すべて含む**<br /><br />**再配置処理に不要なシンボルを除外**<br /><br />**デバッガー シンボル情報のみを除外**<br /><br />**すべてのシンボル情報を除外** |
| デバッガー シンボル情報のパッケージ化 | パッケージ化の前にデバッガー シンボル情報を削除してください。  元のバイナリのコピーがデバッグに使用されます。 |
| マップ ファイル名 | マップ オプションは、ユーザーが指定した名前を使用してマップ ファイルを作成するようにリンカーを設定します。 |
| 再配置後に変数を読み取り専用としてマーク | このオプションは、再配置後に変数を読み取り専用としてマークします。 |
| 即時関数バインディングの有効化 | このオプションは、即時関数バインディング用にオブジェクトをマークします。 |
| 実行可能スタックの要求 | このオプションは、実行可能スタックを必要としないものとして出力をマークします。 |
| アーカイブ全体 | アーカイブ全体は、ソースおよびその他の依存関係のすべてのコードを使用します。 |
| 追加オプション | その他のオプションです。 |
| [追加の依存ファイル] | リンク コマンド ラインに追加する項目を指定します。 |
| ライブラリの依存ファイル | このオプションでは、リンカー コマンド ラインに追加する追加ライブラリを指定できます。 追加のライブラリは、 *lib*で始まるリンカーコマンドラインの最後に追加され、 *. a*または *. so*拡張子で終わります。  (-lFILE) |
