---
title: -WINMD (Windows メタデータの生成) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs:
- C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25b8b34e55fc0814653f4c44be50e545633be373
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705730"
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (Windows メタデータの生成)

Windows ランタイム メタデータ (.winmd) ファイルの生成を有効にします。

```
/WINMD[:{NO|ONLY}]
```

## <a name="remarks"></a>Remarks

**/WINMD**<br/>
ユニバーサル Windows プラットフォーム アプリの既定の設定。 リンカーは、バイナリ実行可能ファイルと .winmd のメタデータ ファイルの両方を生成します。

**/WINMD:NO**<br/>
のみ、バイナリ実行可能ファイルですが .winmd ファイルではなく、リンカーが生成されます。

**/WINMD: のみ**<br/>
.Winmd ファイルのみが、バイナリ実行可能ファイルではなく、リンカーが生成されます。

既定では、出力ファイル名には、フォーム`binaryname`.winmd します。 別のファイル名を指定するには、使用、 [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)オプション。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**リンカー**フォルダー。

1. 選択、 **Windows メタデータ**プロパティ ページ。

1. **Windows メタデータの生成**ドロップダウン リスト ボックスで、目的のオプションを選択します。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)