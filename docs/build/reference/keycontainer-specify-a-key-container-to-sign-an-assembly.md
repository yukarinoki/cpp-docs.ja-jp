---
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
ms.openlocfilehash: 3467350602d0e5b4fbb7df5f92238e18e39532bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616568"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>引数

*name*<br/>
キーを含むコンテナーです。 二重引用符で区切る文字列を配置 ("")、スペースが含まれている場合。

## <a name="remarks"></a>Remarks

リンカーは、公開キーをアセンブリ マニフェストに挿入し、秘密キーで最終アセンブリに署名により署名されたアセンブリを作成します。 キー ファイルを生成する入力[sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename*コマンドライン。 **sn-i**をコンテナーにキー ペアをインストールします。

使用してコンパイルする場合[/LN](../../build/reference/ln-create-msil-module.md)、キー ファイルの名前がモジュールに保持されを使用して、モジュールを明示的に参照を含むアセンブリをコンパイルするときに作成されるアセンブリに組み込む[#using](../../preprocessor/hash-using-directive-cpp.md)とをリンクするときまたは[/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)します。

コンパイラに、暗号化情報を渡すことができますも[/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)します。 使用[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)部分的に署名されたアセンブリを作成する場合。 参照してください[厳密な名前のアセンブリ (アセンブリ署名) (C +/cli CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)アセンブリへの署名の詳細についてはします。

アセンブリの生成に影響するその他のリンカー オプションがあります。

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. オプションを入力、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)