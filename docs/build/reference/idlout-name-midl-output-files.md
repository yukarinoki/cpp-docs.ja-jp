---
title: /IDLOUT (MIDL 出力ファイルの指定)
ms.date: 11/04/2016
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
ms.openlocfilehash: 91c1a3642f157390e5a0d5c7e2f36d7adf3ca118
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417633"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (MIDL 出力ファイルの指定)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>パラメーター

*path*<br/>
絶対パスまたは相対パス仕様では。 .Idl ファイルの場所のみに影響するパスを指定すると、その他のすべてのファイルは、プロジェクト ディレクトリに配置されます。

*ファイル名*<br/>
MIDL コンパイラによって作成された .idl ファイルの名前を指定します。 ファイル拡張子は想定されていません。指定*filename*.idl .idl 拡張する場合。

## <a name="remarks"></a>Remarks

/IDLOUT オプションは、.idl ファイルの拡張機能と名前を指定します。

あるプロジェクトをリンクするときに、MIDL コンパイラは、Visual C リンカーによって呼び出されます、[モジュール](../../windows/module-cpp.md)属性。

/IDLOUT には、MIDL コンパイラに関連付けられているその他の出力ファイルのファイル名も指定します。

- *ファイル名*.tlb

- *filename*_p.c

- *filename*_i.c

- *ファイル名*.h

*ファイル名*/IDLOUT に渡すパラメーターです。 場合[/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) /TLBOUT からその名前を取得、.tlb ファイル指定*filename*します。

/IDLOUT も/TLBOUT を指定する場合、リンカーは、vc70.tlb、vc70.idl、vc70_p.c、vc70_i.c、および vc70.h に作成されます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**埋め込み IDL**プロパティ ページ。

1. 変更、 **IDL ベース ファイル名のマージ**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)<br/>
[/IGNOREIDL (属性を MIDL に挿入しない)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (MIDL コマンド ライン オプションの指定)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[属性付きプログラムの作成](../../windows/building-an-attributed-program.md)
