---
description: 詳細については、「/MAP (Mapfile の生成)」を参照してください。
title: /MAP (マップ ファイルの生成)
ms.date: 11/04/2016
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
ms.openlocfilehash: 28e3823099b4893dcf344a0b1aae99577d850821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176432"
---
# <a name="map-generate-mapfile"></a>/MAP (マップ ファイルの生成)

```
/MAP[:filename]
```

## <a name="arguments"></a>引数

*filename*<br/>
マップされたユーザー指定の名前。 既定の名前を置き換えます。

## <a name="remarks"></a>解説

/MAP オプションは、マップを作成するようにリンカーに指示します。

既定では、リンカーは、プログラムのベース名と拡張子 .map を使用して、mapfile に名前を付けます。 省略可能な *ファイル名* を使用すると、mapfile の既定の名前をオーバーライドできます。

マップファイルは、リンクされているプログラムに関する次の情報を含むテキストファイルです。

- モジュール名。ファイルのベース名です。

- プログラムファイルヘッダーからのタイムスタンプ (ファイルシステムからのものではない)

- プログラム内のグループのリスト。各グループの開始アドレス ( *セクション*:*offset*)、長さ、グループ名、クラス

- パブリックシンボルのリスト。各アドレス ( *セクション*:*offset*)、シンボル名、フラットアドレス、およびシンボルが定義されている .obj ファイル

- エントリポイント ( *セクション*:*offset*)

[/Mapinfo](mapinfo-include-information-in-mapfile.md)オプションは、mapfile に含める追加情報を指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **デバッグ** ] プロパティページをクリックします。

1. " **マップファイルの生成** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> と <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A> を参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
