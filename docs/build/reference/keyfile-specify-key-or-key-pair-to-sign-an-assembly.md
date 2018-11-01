---
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
ms.openlocfilehash: 6896993f7be8e088242e8a2e3279aa1f6c9a721d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524957"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定)

```
/KEYFILE:filename
```

## <a name="arguments"></a>引数

*ファイル名*<br/>
キーを含むファイルです。 二重引用符で区切る文字列を配置 ("")、スペースが含まれている場合。

## <a name="remarks"></a>Remarks

リンカーはアセンブリ マニフェストに公開キーを挿入し、秘密キーで最終アセンブリに署名します。 キー ファイルを生成する入力[sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename*コマンドライン。 署名されたアセンブリは、厳密な名前と呼ばれます。

使用してコンパイルする場合[/LN](../../build/reference/ln-create-msil-module.md)、キー ファイルの名前がモジュールに保持されを使用して、モジュールを明示的に参照を含むアセンブリをコンパイルするときに作成されるアセンブリに組み込む[#using](../../preprocessor/hash-using-directive-cpp.md)とをリンクするときまたは[/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)します。

リンカーに、暗号化情報を渡すことができますも[/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)します。 使用[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)部分的に署名されたアセンブリを作成する場合。 参照してください[厳密な名前のアセンブリ (アセンブリ署名) (C +/cli CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)アセンブリへの署名の詳細についてはします。

場合両方 **/KEYFILE**と **/KEYCONTAINER**が指定されて、リンカーは、キー コンテナーをまず (コマンド ライン オプションまたはカスタム属性によって)、します。 それが成功すると、アセンブリはキー コンテナーの情報で署名されます。 リンカーがキー コンテナーを見つけられない場合/KEYFILE で指定されたファイルが試みられます。 ファイルが検出された場合、アセンブリはキー ファイルの情報で署名され、キー情報はキー コンテナーにインストールされるため (sn -i と同様)、次のコンパイル時にはキー コンテナーが有効になります。

キー ファイルには公開キーだけが含まれる場合があることに注意してください。

参照してください[の作成と using strong-named Assemblies](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)アセンブリへの署名の詳細についてはします。

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