---
title: /MACHINE (ターゲット プラットフォームの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: e64aa7b2ca9e50ebdc0760f64a9b25e851b45310
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818129"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (ターゲット プラットフォームの指定)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Remarks

/MACHINE オプションは、プログラムのターゲット プラットフォームを指定します。

通常、/MACHINE オプションは指定する必要がありません。 LINK では、.obj ファイルからコンピューターの種類を推測するためです。 ただし、状況によっては、リンクかを判断できません、マシンの種類と問題を[リンカー ツール エラー LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md)します。 このようなエラー メッセージが出力された場合は、/MACHINE オプションを指定してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**詳細**プロパティ ページ。

1. 変更、**ターゲット マシン**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
