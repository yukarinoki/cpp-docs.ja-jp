---
title: -ASSEMBLYMODULE (MSIL モジュールをアセンブリに追加する) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c1b5104a264a3fbeeada080b6c34a6b1c5e23ca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703938"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>引数

*ファイル名*<br/>
このアセンブリに追加するモジュールです。

## <a name="remarks"></a>Remarks

/ASSEMBLYMODULE オプションを使用すると、モジュールの参照をアセンブリに追加できます。 モジュールの種類の情報はモジュール参照を追加したアセンブリ プログラムを利用できません。 ただし、モジュール内の型情報は、アセンブリを参照するプログラムで使用可能になります。

使用[#using](../../preprocessor/hash-using-directive-cpp.md)アセンブリへのモジュール参照を追加して、モジュールの種類の情報をアセンブリのプログラムを使用できるようにします。

たとえば、次の場合を考えてください。

1. 作成して、モジュール[/LN](../../build/reference/ln-create-msil-module.md)します。

1. 別のプロジェクトで/ASSEMBLYMODULE を使用すると、現在のコンパイルでは、アセンブリを作成、モジュールを含めます。 このプロジェクトは使用して、モジュールを参照しない`#using`します。

1. また、このアセンブリを参照する任意のプロジェクトでは、モジュールから型を使用できますようになりました。

アセンブリの生成に影響するその他のリンカー オプションがあります。

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Visual C リンカー入力としての .netmodule ファイルを受け入れるし、リンカーによって生成された出力ファイルは、アセンブリまたは実行時の依存しない、リンカーに .netmodule のいずれかで .netmodule になります。  詳細については、「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**入力**プロパティ ページ。

1. 変更、**モジュールをアセンブリに追加**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)