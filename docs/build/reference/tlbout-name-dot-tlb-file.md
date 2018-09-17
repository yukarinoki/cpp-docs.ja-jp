---
title: -TLBOUT (名前です。TLB ファイル) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
dev_langs:
- C++
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c44028f834d2b3200b970fdc613d0bf4d4efd29
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702859"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (.TLB ファイル名の指定)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>引数

*path*<br/>
.Tlb ファイルを作成する必要があります絶対または相対パス仕様。

*ファイル名*<br/>
MIDL コンパイラによって作成された .tlb ファイルの名前を指定します。 ファイル拡張子は想定されていません。指定*filename*.tlb 拡張子 .tlb を付加する場合。

## <a name="remarks"></a>Remarks

/TLBOUT オプションは、.tlb ファイルの拡張子と名前を指定します。

あるプロジェクトをリンクするときに、MIDL コンパイラは、Visual C リンカーによって呼び出されます、[モジュール](../../windows/module-cpp.md)属性。

.Tlb ファイルから、その名前を受け取ります/TLBOUT が指定されていない場合[/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*します。 /IDLOUT が指定されていない場合、.tlb ファイルには、vc70.tlb が呼び出されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**埋め込み IDL**プロパティ ページ。

1. 変更、**タイプ ライブラリ**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[/IGNOREIDL (を MIDL に挿入に属性を処理しない)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)
[/MIDL (MIDL コマンド ライン オプションの指定)](../../build/reference/midl-specify-midl-command-line-options.md)
[属性付きプログラムの作成](../../windows/building-an-attributed-program.md)