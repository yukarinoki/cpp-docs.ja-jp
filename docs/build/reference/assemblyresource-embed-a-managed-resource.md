---
description: 詳細情報:/assemblyresource (マネージリソースの埋め込み)
title: /ASSEMBLYRESOURCE (マネージド リソースの埋め込み)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: 3f79cc177df72bb83288a0a229fdf47adb0e7fc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182919"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (マネージド リソースの埋め込み)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>パラメーター

*filename*<br/>
このアセンブリに埋め込むマネージリソース。

*name*<br/>
省略可能。 リソースの論理名。リソースを読み込むために使用する名前。 既定値は、ファイルの名前です。

必要に応じて、ファイルをアセンブリマニフェスト内でプライベートにするかどうかを指定できます。 既定では、アセンブリ内の *名前* は public です。

## <a name="remarks"></a>解説

/Assemblyresource オプションを使用して、リソースをアセンブリに埋め込みます。

リンカーを使用して作成した場合、リソースはアセンブリでパブリックになります。 リンカーでは、アセンブリ内のリソースの名前を変更することはできません。

*Filename* が [リソースファイルジェネレーター (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator)や開発環境などによって作成された .NET Framework リソース (.resources) ファイルの場合は、 **system. .resources** 名前空間のメンバーを使用してアクセスできます (詳細については、「system.servicemodel」[を参照してください)](/dotnet/api/system.resources.resourcemanager) 。 その他のすべてのリソースについては、 \* 実行時にリソースにアクセスするために、System.object クラスの getmanifestresource メソッドを使用し **ます。**

アセンブリの生成に影響を与える他のリンカーオプションは次のとおりです。

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **入力** ] プロパティページをクリックします。

1. " **マネージリソースファイルの埋め込み** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
