---
description: 詳細情報:/KEYCONTAINER (アセンブリに署名するためのキーコンテナーの指定)
title: /KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
ms.openlocfilehash: 5f32fdc5400103d4038139fa2dfe9409c9740236
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199585"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>引数

*name*<br/>
キーを格納しているコンテナー。 空白が含まれている場合は、文字列を二重引用符 ("") で囲みます。

## <a name="remarks"></a>解説

リンカーは、公開キーをアセンブリマニフェストに挿入し、秘密キーを使用して最終的なアセンブリに署名することで、署名されたアセンブリを作成します。 キーファイルを生成するには、コマンドラインで「 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 」と入力します。 **sn-i** キーペアをコンテナーにインストールします。

[/LN](ln-create-msil-module.md)を使用してコンパイルする場合、キーファイルの名前はモジュールに保持され、モジュールへの明示的な参照を含むアセンブリをコンパイルするときに作成されるアセンブリに組み込まれます。または、 [#using](../../preprocessor/hash-using-directive-cpp.md)を使用するか、または[/assemblymodule](assemblymodule-add-a-msil-module-to-the-assembly.md)とリンクするときに作成されます。

また、暗号化情報を [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)でコンパイラに渡すこともできます。 部分署名されたアセンブリが必要な場合は、 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) を使用します。 アセンブリに署名する方法の詳細については、「 [厳密名アセンブリ (アセンブリ署名) (C++/cli)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 」を参照してください。

アセンブリの生成に影響を与える他のリンカーオプションは次のとおりです。

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [ **追加オプション** ] ボックスにオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
