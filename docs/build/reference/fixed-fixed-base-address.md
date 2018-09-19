---
title: -FIXED (固定ベース アドレス) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 697f6ccfd98059175311cd04e4e82038877b2110
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723399"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (固定ベース アドレス)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Remarks

オペレーティング システムに、指定されたベース アドレスにだけプログラムを読み込むように指示します。 指定したベース アドレスが使用できない場合、オペレーティング システムはファイルを読み込みません。 詳細については、「[/BASE (ベース アドレス)](../../build/reference/base-base-address.md)」を参照してください。

DLL には /FIXED:NO が既定で使用されます。他のすべての種類のプロジェクトには /FIXED が既定で使用されます。

/FIXED オプションを指定すると、プログラム内に再配置セクションが作成されなくなります。 実行時にオペレーティング システムが指定されたアドレスにプログラムを読み込むことができない場合は、エラー メッセージが表示され、プログラムが読み込まれなくなります。

/FIXED:NO を指定すると、プログラム内に再配置セクションが生成されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**リンカー**フォルダー。

1. 選択、**コマンドライン**プロパティ ページ。

1. オプション名を入力し、設定、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)