---
description: 詳細情報:/MACHINE (ターゲットプラットフォームの指定)
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
ms.openlocfilehash: a1bf87142fb99577672391356a43a2771ea0b09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190810"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (ターゲット プラットフォームの指定)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>解説

/MACHINE オプションは、プログラムのターゲット プラットフォームを指定します。

通常、/MACHINE オプションは指定する必要がありません。 LINK では、.obj ファイルからコンピューターの種類を推測するためです。 ただし、状況によっては、リンクがマシンの種類を特定できず、 [リンカーツールのエラー LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md)を発行する場合があります。 このようなエラー メッセージが出力された場合は、/MACHINE オプションを指定してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. **ターゲットコンピューター** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
