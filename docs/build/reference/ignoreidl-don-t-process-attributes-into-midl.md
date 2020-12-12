---
description: 詳細情報:/IGNOREIDL (Don&#39;t の属性を MIDL に処理する)
title: /IGNOREIDL (Don&#39;t が MIDL に属性を処理する)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: c68b3ec2f9bd5607ef523667bcddc68b22d3c34c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199819"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don&#39;t が MIDL に属性を処理する)

```
/IGNOREIDL
```

## <a name="remarks"></a>解説

/IGNOREIDL オプションは、ソースコード内の [idl 属性](../../windows/attributes/idl-attributes.md) を .idl ファイルに処理しないように指定します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **埋め込み IDL** ] プロパティページをクリックします。

1. " **埋め込み IDL の無視** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)<br/>
[/IDLOUT (MIDL 出力ファイルの名前の指定)](idlout-name-midl-output-files.md)<br/>
[/TLBOUT (名前。TLB ファイル)](tlbout-name-dot-tlb-file.md)<br/>
[/Midl (MIDL コマンドラインオプションの指定)](midl-specify-midl-command-line-options.md)<br/>
[属性付きプログラムの作成](../../windows/attributes/cpp-attributes-com-net.md)
