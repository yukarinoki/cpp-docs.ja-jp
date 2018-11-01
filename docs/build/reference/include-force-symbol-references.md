---
title: /INCLUDE (シンボルの明示的な参照)
ms.date: 11/04/2016
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
ms.openlocfilehash: 418b66cb16954f23036eaa65e07a4abf80fdba79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439339"
---
# <a name="include-force-symbol-references"></a>/INCLUDE (シンボルの明示的な参照)

```
/INCLUDE:symbol
```

## <a name="parameters"></a>パラメーター

*シンボル*<br/>
シンボル テーブルに追加する記号を指定します。

## <a name="remarks"></a>Remarks

/INCLUDE オプションを使用すると、リンカーは、指定されたシンボルをシンボル テーブルに追加します。

複数のシンボルを指定するには、コンマ (,)、セミコロン (;)、またはシンボル名の間にスペースを入力します。 コマンドラインで指定/INCLUDE:`symbol`シンボルごとに 1 回です。

リンカーを解決`symbol`プログラムにシンボルの定義を含むオブジェクトを追加します。 この機能は、それ以外の場合、プログラムにはリンクいないライブラリ オブジェクトを含む場合に便利です。

このオプションでシンボルを指定することによって、そのシンボルの削除よりも優先されます[/OPT:REF](../../build/reference/opt-optimizations.md)します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**入力**プロパティ ページ。

1. 変更、**シンボル参照の強制**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)