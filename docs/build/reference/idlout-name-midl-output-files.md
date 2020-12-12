---
description: 詳細情報:/IDLOUT (MIDL 出力ファイルの名前の指定)
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
ms.openlocfilehash: 9835721d3e9b376feca51d87d375efa79dc43df7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199845"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (MIDL 出力ファイルの指定)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>パラメーター

*path*<br/>
絶対パスまたは相対パスを指定します。 パスを指定すると、.idl ファイルの場所のみに影響します。その他のすべてのファイルは、プロジェクトディレクトリに配置されます。

*filename*<br/>
MIDL コンパイラによって作成される .idl ファイルの名前を指定します。 ファイル拡張子は想定されていません。.idl 拡張子が必要な場合は、 *filename* を指定します。

## <a name="remarks"></a>解説

/IDLOUT オプションは、.idl ファイルの名前と拡張子を指定します。

MIDL コンパイラは、 [module](../../windows/attributes/module-cpp.md) 属性を持つプロジェクトをリンクするときに、MSVC リンカーによって呼び出されます。

/IDLOUT は、MIDL コンパイラに関連付けられている他の出力ファイルのファイル名も指定します。

- *ファイル名*.tlb

- *ファイル名* _p .c

- *ファイル名* _i .c

- *ファイル名*.h

*filename* は、/IDLOUT. に渡すパラメーターです。 [/TLBOUT](tlbout-name-dot-tlb-file.md)を指定した場合、.tlb ファイルの名前は/TLBOUT *filename* から取得されます。

/IDLOUT と/TLBOUT のどちらも指定しない場合、リンカーは vc70、vc70、vc70_p .c、vc70_i、および vc70 を作成します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **埋め込み IDL** ] プロパティページをクリックします。

1. **MERGE IDL Base File Name** プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[/IGNOREIDL (属性を MIDL に処理しない)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/Midl (MIDL コマンドラインオプションの指定)](midl-specify-midl-command-line-options.md)<br/>
[属性付きプログラムの作成](../../windows/attributes/cpp-attributes-com-net.md)
