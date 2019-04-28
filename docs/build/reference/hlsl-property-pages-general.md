---
title: '[HLSL] プロパティ ページ:全般'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
ms.openlocfilehash: 0fce8a3b2a43cf05024a028a9e3325a929922abb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291471"
---
# <a name="hlsl-property-pages-general"></a>[HLSL] プロパティ ページ:全般

HLSL コンパイラ (fxc.exe) の次のプロパティを構成するには、その **[全般]** プロパティ ページを使います。 アクセスする方法については、**全般**HLSL フォルダーで、プロパティ ページを参照してください[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

## <a name="uielement-list"></a>UIElement の一覧

- **追加のインクルード ディレクトリ**

   インクルード パスに 1 つ以上のディレクトリを追加します。 ディレクトリを区切るにはセミコロンを使います。

このプロパティは、**/I[path]** コマンド ライン引数に対応します。

- **エントリ ポイント名**

   シェーダーのエントリ ポイントを指定します。 既定値は **main** です。

このプロパティは、**/E[name]** コマンド ライン引数に対応します。

- **最適化を無効にする**

   最適化を有効にする場合は **[はい (/Od)]**、それ以外の場合は **[いいえ]** です。 既定値は、**デバッグ**構成の場合は **[はい (/Od)]**、**リリース**構成の場合は **[いいえ]** です。

HLSL コンパイラに対して **/Od** コマンド ライン引数を指定すると **/Gfp** コマンド ライン引数が暗黙的に適用されますが、その出力は、**/Od** と **/Gfp** 両方のコマンド ライン引数を明示的に渡すことによって生成される出力と同じでない場合があります。

- **デバッグ情報を有効にする**

   デバッグ情報を有効にする場合は **[はい (/Zi)]**、それ以外の場合は **[いいえ]** です。 既定値は、**デバッグ**構成の場合は **[はい (/Zi)]**、**リリース**構成の場合は **[いいえ]** です。

- **シェーダーの種類**

   シェーダーの種類を指定します。 異なる種類のシェーダーは、グラフィックス パイプラインの異なる部分を実装します。 一部のシェーダーの種類は、新しいシェーダー モデル (**[シェーダー モデル]** プロパティで指定されています) でのみ使用できます。たとえば、計算シェーダーはシェーダー モデル 5 で導入されました。

   このプロパティは、HLSL コンパイラに対する **/T \[type]_\[model]** コマンド ライン引数の **\[type]** 部分に対応します。 **[シェーダー モデル]** プロパティは、引数の **[model]** 部分を指定します。

- **シェーダー モデル**

   シェーダー モデルを指定します。 シェーダー モデルが異なると、機能が異なります。 一般に、シェーダー モデルが新しいほど機能は拡張されていますが、シェーダー コードを実行するにはより新しいグラフィックス ハードウェアが必要です。 一部のシェーダーの種類 (**[シェーダーの種類]** プロパティで指定されています) は、新しいシェーダー モデルでのみ使用できます。たとえば、計算シェーダーはシェーダー モデル 5 で導入されました。

   このプロパティは、HLSL コンパイラに対する **/T \[type]_\[model]** コマンド ライン引数の **\[model]** 部分に対応します。 **[シェーダーの種類]** プロパティは、引数の **[type]** 部分を指定します。

- **プリプロセッサの定義**

   HLSL のソース コード ファイルに適用する 1 つ以上のプリプロセッサ シンボル定義を追加します。 シンボル定義を区切るにはセミコロンを使います。

   このプロパティは、HLSL コンパイラに対する **/D \[definitions]** コマンド ライン引数に対応します。

## <a name="see-also"></a>関連項目

[[HLSL] プロパティ ページ](hlsl-property-pages.md)<br>
[[HLSL] プロパティ ページ: 詳細](hlsl-property-pages-advanced.md)<br>
[[HLSL] プロパティ ページ: 出力ファイル](hlsl-property-pages-output-files.md)
