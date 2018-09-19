---
title: -ASSEMBLYRESOURCE (マネージ リソースの埋め込み) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec883aa1b6d9fb6ea354e218f5924e9c3562c585
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720604"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (マネージド リソースの埋め込み)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>パラメーター

*ファイル名*<br/>
このアセンブリに埋め込む管理対象リソース。

*name*<br/>
任意。 リソースの論理名リソースの読み込みに使用する名前。 既定値は、ファイルの名前です。

必要に応じて、ファイルをプライベート アセンブリ マニフェストである必要があるかどうかを指定できます。 既定では、*名前*アセンブリ内でパブリックです。

## <a name="remarks"></a>Remarks

/ASSEMBLYRESOURCE オプションを使用して、アセンブリにリソースを埋め込みます。

リソースは、リンカーで作成したアセンブリの公開。 リンカーでは、アセンブリ内のリソースの名前を変更できません。

場合*filename*は、.NET Framework のリソース (.resources) ファイルをたとえば、によって作成、[リソース ファイル ジェネレーター (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator)または開発環境でアクセスできるメンバー間で、**System.Resources**名前空間 (を参照してください[System.Resources.ResourceManager](https://msdn.microsoft.com/library/system.resources.resourcemanager.aspx)詳細については)。 他のすべてのリソースを使用して、**それ以外**\*メソッド**System.Reflection.Assembly**実行時にリソースにアクセスするクラス。

アセンブリの生成に影響するその他のリンカー オプションがあります。

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**入力**プロパティ ページ。

1. 変更、**埋め込みマネージ リソース ファイル**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)