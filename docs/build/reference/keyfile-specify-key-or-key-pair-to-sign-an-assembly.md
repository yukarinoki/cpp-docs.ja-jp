---
description: :/KEYFILE (アセンブリに署名するためのキーまたはキーペアの指定) に関する詳細情報
title: /KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定)
ms.date: 11/04/2016
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
ms.openlocfilehash: 23c4962ab57688f5d8c1af27fd412d7d36be01a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191161"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定)

```
/KEYFILE:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
キーが含まれるファイル。 空白が含まれている場合は、文字列を二重引用符 ("") で囲みます。

## <a name="remarks"></a>解説

リンカーは公開キーをアセンブリマニフェストに挿入し、秘密キーを使用して最終的なアセンブリに署名します。 キーファイルを生成するには、コマンドラインで「 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 」と入力します。 署名されたアセンブリには、厳密な名前が付いています。

[/LN](ln-create-msil-module.md)を使用してコンパイルする場合、キーファイルの名前はモジュールに保持され、モジュールへの明示的な参照を含むアセンブリをコンパイルするときに作成されるアセンブリに組み込まれます。または、 [#using](../../preprocessor/hash-using-directive-cpp.md)を使用するか、または[/assemblymodule](assemblymodule-add-a-msil-module-to-the-assembly.md)とリンクするときに作成されます。

[/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)を使用して、暗号化情報をリンカーに渡すこともできます。 部分署名されたアセンブリが必要な場合は、 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) を使用します。 アセンブリに署名する方法の詳細については、「 [厳密名アセンブリ (アセンブリ署名) (C++/cli)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 」を参照してください。

コマンドラインオプションまたはカスタム属性によって、 **/keyfile** と **/KEYCONTAINER** の両方が指定されている場合、リンカーは最初にキーコンテナーを試します。 それが成功すると、アセンブリはキー コンテナーの情報で署名されます。 リンカーがキーコンテナーを見つけられない場合は、/KEYFILE. で指定されたファイルを使用します。 ファイルが検出された場合、アセンブリはキー ファイルの情報で署名され、キー情報はキー コンテナーにインストールされるため (sn -i と同様)、次のコンパイル時にはキー コンテナーが有効になります。

キー ファイルには公開キーだけが含まれる場合があることに注意してください。

アセンブリの署名の詳細については、「[厳密な名前付きアセンブリの作成と使用](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)」を参照してください。

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
