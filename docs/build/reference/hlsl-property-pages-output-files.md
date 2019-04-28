---
title: '[HLSL] プロパティ ページ:出力ファイル'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
ms.openlocfilehash: 6ee8042fccf2e0b635535a77d9c9a6bc68bd9999
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291549"
---
# <a name="hlsl-property-pages-output-files"></a>[HLSL] プロパティ ページ:出力ファイル

HLSL コンパイラ (fxc.exe) の次のプロパティを構成するには、その **[出力ファイル]** プロパティを使用します。 アクセスする方法については、**出力ファイル**HLSL フォルダーで、プロパティ ページを参照してください[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

## <a name="uielement-list"></a>UIElement の一覧

- **ヘッダー変数名**

   エンコードされた HLSL オブジェクト コードに使用される配列の名前を指定します。 この配列は、HLSL コンパイラによって出力されるヘッダー ファイルに含まれます。 ヘッダー ファイルの名前は、**ヘッダー ファイル名**プロパティで指定されます。

このプロパティは、**/Vn[name]** コマンドライン引数に対応します。

- **ヘッダー ファイル名**

   HLSL コンパイラによって出力されるヘッダー ファイルの名前を指定します。 ヘッダーには、配列にエンコードされた HLSL オブジェクト コードが含まれています。 配列の名前は、**ヘッダー変数名**プロパティで指定されます。

このプロパティは、**/Fh[name]** コマンドライン引数に対応します。

- **オブジェクト ファイル名**

   HLSL コンパイラによって出力されるオブジェクト ファイルの名前を指定します。 既定では、値は **$(OutDir)%(Filename).cso** です。

このプロパティは、**/Fo[name]** コマンドライン引数に対応します。

- **アセンブラー出力**

   アセンブリ言語のステートメントだけを出力する**アセンブリ コードのみ (/Fc)**。 アセンブリ言語ステートメントと、対応するオペコードの両方を 16 進数で出力する**アセンブリ コードと 16 進数 (/Fx)**。 既定では、リストは出力されません。

- **アセンブラー出力ファイル**

   HLSL コンパイラによって出力されるアセンブリ リスト ファイルの名前を指定します。

   このプロパティは、**/Fo[name]** と **/Fx [name]** のコマンドライン引数に対応します。

## <a name="see-also"></a>関連項目

[[HLSL] プロパティ ページ](hlsl-property-pages.md)<br>
[[HLSL] プロパティ ページ: 全般](hlsl-property-pages-general.md)<br>
[[HLSL] プロパティ ページ: 詳細](hlsl-property-pages-advanced.md)
