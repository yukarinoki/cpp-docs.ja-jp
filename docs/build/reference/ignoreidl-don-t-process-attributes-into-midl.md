---
title: /IGNOREIDL (Don&#39;t プロセスの属性を MIDL に挿入)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: f6c5fcbae52ed695f2d0c389607ac4231f069788
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534356"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don&#39;t プロセスの属性を MIDL に挿入)

```
/IGNOREIDL
```

## <a name="remarks"></a>Remarks

/IGNOREIDL オプションを指定する[IDL 属性](../../windows/idl-attributes.md)ソース コードを .idl ファイルに処理するされません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**埋め込み IDL**プロパティ ページ。

1. 変更、**埋め込み IDL の無視**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[/IDLOUT (MIDL 出力ファイルの指定)](../../build/reference/idlout-name-midl-output-files.md)<br/>
[/TLBOUT (.TLB ファイル名の指定)](../../build/reference/tlbout-name-dot-tlb-file.md)<br/>
[/MIDL (MIDL コマンド ライン オプションの指定)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[属性付きプログラムの作成](../../windows/building-an-attributed-program.md)