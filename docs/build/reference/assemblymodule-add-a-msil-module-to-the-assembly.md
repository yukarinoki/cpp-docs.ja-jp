---
description: 詳細情報:/assemblymodule (アセンブリに MSIL モジュールを追加)
title: /ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加)
ms.date: 11/04/2016
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
ms.openlocfilehash: d56895b6bec05efda1104e319e93a040f818e06e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182945"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>引数

*filename*<br/>
このアセンブリに含めるモジュール。

## <a name="remarks"></a>解説

/Assemblymodule オプションを使用すると、モジュール参照をアセンブリに追加できます。 モジュール参照を追加したアセンブリプログラムでは、モジュールの型情報を使用できません。 ただし、モジュールの型情報は、アセンブリを参照するすべてのプログラムで使用できます。

アセンブリにモジュール参照を追加し、アセンブリプログラムでモジュールの型情報を使用できるようにするには、 [#using](../../preprocessor/hash-using-directive-cpp.md) を使用します。

ここでは、次のシナリオを例に説明します。

1. [/LN](ln-create-msil-module.md)を使用してモジュールを作成します。

1. 別のプロジェクトで/assemblymodule を使用して、現在のコンパイルにモジュールを含めます。これにより、アセンブリが作成されます。 このプロジェクトは、でモジュールを参照しません `#using` 。

1. このアセンブリを参照するプロジェクトでも、モジュールの型を使用できるようになりました。

アセンブリの生成に影響を与える他のリンカーオプションは次のとおりです。

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

MSVC リンカーは、入力として .netmodule ファイルを受け入れます。リンカーによって生成される出力ファイルは、リンカーに対して入力された netmodule のいずれにも実行時の依存関係がないアセンブリまたは .netmodule になります。  詳細については、「 [リンカー入力としての .netmodule ファイル](netmodule-files-as-linker-input.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **入力** ] プロパティページをクリックします。

1. [ **モジュールをアセンブリに追加するプロパティを** 変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
