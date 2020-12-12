---
description: 詳細情報:/FIXED (固定ベースアドレス)
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
ms.openlocfilehash: 08b781b7fbeaf43d6c7e0e82da7bf8319cf77953
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192058"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (固定ベース アドレス)

```
/FIXED[:NO]
```

## <a name="remarks"></a>解説

オペレーティング システムに、指定されたベース アドレスにだけプログラムを読み込むように指示します。 指定したベース アドレスが使用できない場合、オペレーティング システムはファイルを読み込みません。 詳細については、「 [/base (ベースアドレス)](base-base-address.md)」を参照してください。

DLL には /FIXED:NO が既定で使用されます。他のすべての種類のプロジェクトには /FIXED が既定で使用されます。

/FIXED オプションを指定すると、プログラム内に再配置セクションが作成されなくなります。 実行時にオペレーティング システムが指定されたアドレスにプログラムを読み込むことができない場合は、エラー メッセージが表示され、プログラムが読み込まれなくなります。

/FIXED:NO を指定すると、プログラム内に再配置セクションが生成されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション** ] ボックスにオプション名と設定を入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
