---
description: 詳細については、「/TLBOUT (名前)」を参照してください。TLB ファイル)
title: /TLBOUT (.TLB ファイル名の指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
ms.openlocfilehash: 4e99f3b5a036ddbc424732e771f7bab27aeb228d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230004"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (.TLB ファイル名の指定)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>引数

*path*<br/>
.Tlb ファイルを作成する場所の絶対パスまたは相対パスを指定します。

*filename*<br/>
MIDL コンパイラによって作成される .tlb ファイルの名前を指定します。 ファイル拡張子は想定されていません。.tlb 拡張子を付ける場合は、 *ファイル名*.tlb を指定します。

## <a name="remarks"></a>解説

/TLBOUT オプションは、.tlb ファイルの名前と拡張子を指定します。

MIDL コンパイラは、 [module](../../windows/attributes/module-cpp.md) 属性を持つプロジェクトをリンクするときに、MSVC リンカーによって呼び出されます。

/TLBOUT が指定されていない場合、.tlb ファイルの名前は [/IDLOUT](idlout-name-midl-output-files.md) *filename* から取得されます。 /IDLOUT が指定されていない場合、.tlb ファイルは vc70 という名前になります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **埋め込み IDL** ] プロパティページをクリックします。

1. **タイプライブラリ** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[/IGNOREIDL (属性を MIDL に処理しない)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/Midl (MIDL コマンドラインオプションの指定)](midl-specify-midl-command-line-options.md)<br/>
[属性付きプログラムの作成](../../windows/attributes/cpp-attributes-com-net.md)
