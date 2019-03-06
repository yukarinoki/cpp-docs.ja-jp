---
title: /FIXED (固定ベース アドレス)
ms.date: 11/04/2016
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
ms.openlocfilehash: ccb89b7dfed78ddebf73aaf6e2a1a8529b065042
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423041"
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
