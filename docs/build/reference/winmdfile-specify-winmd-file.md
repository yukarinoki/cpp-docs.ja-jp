---
title: -WINMDFILE (winmd ファイルの指定) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
dev_langs:
- C++
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d34bdfd2d80690efae8efbc1f95ba0c50a530af3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425785"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd ファイルの指定)

によって生成される Windows ランタイム メタデータ (.winmd) 出力ファイルのファイル名を指定します、 [/WINMD](../../build/reference/winmd-generate-windows-metadata.md)リンカー オプション。

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Remarks

指定されている値を使用して`filename`既定の .winmd ファイル名を上書きする (`binaryname`.winmd)。 ".Winmd"を追加しないことに注意してください。`filename`します。  複数の値が表示されている場合、 **/WINMDFILE**コマンドライン、最後の 1 つが優先されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**リンカー**フォルダー。

1. 選択、 **Windows メタデータ**プロパティ ページ。

1. **Windows メタデータ ファイル**ボックスに、ファイルの場所を入力します。

## <a name="see-also"></a>関連項目

[/WINMD (Windows メタデータの生成)](../../build/reference/winmd-generate-windows-metadata.md)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)