---
description: 詳細情報:/MERGE (セクションの結合)
title: /MERGE (セクションのマージ)
ms.date: 11/04/2016
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
ms.openlocfilehash: 579e5432facd6deb8d2b26b997d9b61f167d2b3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199104"
---
# <a name="merge-combine-sections"></a>/MERGE (セクションのマージ)

```
/MERGE:from=to
```

## <a name="remarks"></a>解説

/MERGE オプションは、最初のセクション (*から*) と2番目のセクション (*に*) を結合し、結果のセクション *に* という名前を付けます。 たとえば、「 `/merge:.rdata=.text` 」のように入力します。

2番目のセクションが存在しない場合、LINK はセクションの名前を *から**に* 変更します。

/MERGE オプションは、Vxd を作成し、コンパイラによって生成されたセクション名をオーバーライドする場合に便利です。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. " **マージセクション** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
