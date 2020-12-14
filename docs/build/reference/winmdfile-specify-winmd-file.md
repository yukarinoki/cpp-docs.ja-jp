---
description: 詳細情報:/WINMDFILE (winmd ファイルの指定)
title: /WINMDFILE (winmd ファイルの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: fd10768c494bbedfbe650e0f0e3e72e8a062cdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259020"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd ファイルの指定)

[/Winmd](winmd-generate-windows-metadata.md)リンカーオプションによって生成される Windows ランタイムメタデータ (winmd) 出力ファイルのファイル名を指定します。

```
/WINMDFILE:filename
```

## <a name="remarks"></a>解説

に指定された値を使用して `filename` 、既定の winmd ファイル名 (winmd) をオーバーライドし `binaryname` ます。 に "winmd" を追加しないことに注意 `filename` してください。  **/WINMDFILE** コマンドラインに複数の値が指定されている場合は、最後の値が優先されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **Windows メタデータ** ] プロパティページを選択します。

1. [ **Windows メタデータファイル** ] ボックスに、ファイルの場所を入力します。

## <a name="see-also"></a>関連項目

[/WINMD (Windows メタデータの生成)](winmd-generate-windows-metadata.md)<br/>
[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
