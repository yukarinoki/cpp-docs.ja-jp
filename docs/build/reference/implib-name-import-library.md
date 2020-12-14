---
description: 詳細情報:/IMPLIB (Import Library という名前)
title: /IMPLIB (インポート ライブラリ名の設定)
ms.date: 11/04/2016
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
ms.openlocfilehash: 2a5ea590368d1bc3abbecf38845e97a99a0d1f96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191317"
---
# <a name="implib-name-import-library"></a>/IMPLIB (インポート ライブラリ名の設定)

> /IMPLIB:*ファイル名*

## <a name="parameters"></a>パラメーター

*filename*<br/>
インポートライブラリのユーザー指定の名前。 既定の名前を置き換えます。

## <a name="remarks"></a>解説

/IMPLIB オプションは、エクスポートを含むプログラムをビルドするときに、リンクによって作成されるインポートライブラリの既定の名前を上書きします。 既定の名前は、メイン出力ファイルの基本名と拡張子 .lib から形成されます。 次の1つまたは複数が指定されている場合は、プログラムにエクスポートが含まれます。

- ソースコード内の [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) キーワード

- .Def ファイル内の[エクスポート](exports.md)ステートメント

- リンクコマンドでの [/export](export-exports-a-function.md) の指定

インポートライブラリが作成されていない場合、LINK は/IMPLIB を無視します。 エクスポートが指定されていない場合、リンクはインポートライブラリを作成しません。 エクスポートファイルがビルドで使用されている場合、リンクは、インポートライブラリが既に存在していて、作成されていないことを前提としています。 インポートライブラリとエクスポートファイルの詳細については、「 [LIB リファレンス](lib-reference.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. **インポートライブラリ** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
