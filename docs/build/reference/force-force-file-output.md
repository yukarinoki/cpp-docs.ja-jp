---
title: /FORCE (ターゲットを強制的に出力)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: af7962a4b3b5805e7e0c4d59752254c8ade17f7b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814307"
---
# <a name="force-force-file-output"></a>/FORCE (ターゲットを強制的に出力)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Remarks

/FORCE オプション、リンカーは有効な .exe ファイルを作成する、または DLL のシンボルが参照されている場合でも定義されているまたは複数回定義されました。

/FORCE オプションは、省略可能な引数を実行できます。

- /Force:multiple をリンク、シンボルの 1 つ以上の定義を検索するかどうかは、出力ファイルを作成します。

- /Force:unresolved: 未解決のリンクに未定義のシンボルを検索するかどうかは、出力ファイルを作成します。 /強制: 未解決のエントリ ポイント シンボルが解決しない場合は無視されます。

/FORCE 引数なしでは、両方の複数のことを意味し、未解決のします。

このオプションで作成されたファイルは、正常に動作しない可能性があります。 /FORCE オプションを指定した場合、リンカーはインクリメンタル リンクされません。

モジュールをコンパイルした場合 **/clr**、 **/force**イメージは作成されません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. オプションを入力、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
