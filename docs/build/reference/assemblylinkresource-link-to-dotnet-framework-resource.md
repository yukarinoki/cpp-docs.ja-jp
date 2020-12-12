---
description: 詳細については、次を参照してください:/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)
title: /ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: 32761cb16e8428d5e3c18330dffb49a50a42903c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183010"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
アセンブリからリンクする .NET Framework のリソース ファイル。

## <a name="remarks"></a>解説

/ASSEMBLYLINKRESOURCE オプションを指定すると、出力ファイル内の .NET Framework リソースへのリンクが作成されます。リソースファイルは出力ファイルに配置されません。 [/Assemblyresource](assemblyresource-embed-a-managed-resource.md) は、リソースファイルを出力ファイルに埋め込みます。

リンカーを使用して作成した場合、リンクされたリソースはアセンブリでパブリックになります。

/ASSEMBLYLINKRESOURCE をコンパイルするには、 [/clr](clr-common-language-runtime-compilation.md)をインクルードする必要があります。 [/LN](ln-create-msil-module.md) または [/NOASSEMBLY](noassembly-create-a-msil-module.md) は、/assemblylinkresourceでは許可されていません。

*Filename* が、たとえば [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator)または開発環境で作成された .NET Framework のリソースファイルである場合は、 **System. .resources** 名前空間のメンバーを使用してアクセスできます。 詳細については、「system.servicemodel」[を参照してください。](/dotnet/api/system.resources.resourcemanager) その他のすべてのリソースについては、 \* 実行時にリソースにアクセスするために **、System.object** クラスの getmanifestresource メソッドを使用します。

ファイル *名* には任意のファイル形式を使用できます。 たとえば、アセンブリのネイティブ DLL を作成して、グローバルアセンブリキャッシュにインストールし、アセンブリ内のマネージコードからアクセスできるようにすることができます。

アセンブリの生成に影響を与える他のリンカーオプションは次のとおりです。

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

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
