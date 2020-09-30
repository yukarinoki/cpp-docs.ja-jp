---
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
ms.openlocfilehash: eac6209e0c34562254117d6ab9db5f47545037ea
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506888"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don&#39;t が MIDL に属性を処理する)

```
/IGNOREIDL
```

## <a name="remarks"></a>注釈

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
