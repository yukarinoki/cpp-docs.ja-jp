---
description: 詳細については、「/OUT (出力ファイル名)」を参照してください。
title: /OUT (出力ファイル名)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
ms.openlocfilehash: 1773b4b2dd340bc105495c1b05211c018548976f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226403"
---
# <a name="out-output-file-name"></a>/OUT (出力ファイル名)

```
/OUT:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
ユーザーが指定した出力ファイルの名前。 既定の名前を置き換えます。

## <a name="remarks"></a>解説

/OUT オプションは、リンカーによって作成されるプログラムの既定の名前と場所をオーバーライドします。

既定では、リンカーは、指定された最初の .obj ファイルの基本名と、適切な拡張子 (.exe または .dll) を使用して、ファイル名を形成します。

このオプションは、mapfile またはインポートライブラリの既定の基本名です。 詳細については、「Mapfile (/Map) と[/IMPLIB](implib-name-import-library.md)の[生成](map-generate-mapfile.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **全般** ] プロパティページをクリックします。

1. " **出力ファイル** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
