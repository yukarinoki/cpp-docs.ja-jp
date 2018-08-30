---
title: -ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
dev_langs:
- C++
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e23bd9e0816c10f41e298afc9e82edbdd27e7a5f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206489"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (.NET Framework リソースへのリンク)
```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## <a name="remarks"></a>Remarks  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 アセンブリからリンクする .NET Framework のリソース ファイル。  
  
## <a name="remarks"></a>Remarks  
 /ASSEMBLYLINKRESOURCE オプションは、出力ファイルで .NET Framework リソースへのリンクを作成します出力ファイルでは、リソース ファイルが配置されていません。 [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)リソース ファイル、出力ファイルに埋め込みます。  
  
 リンクされたリソースでは、リンカーで作成したアセンブリでパブリックです。  
  
 /ASSEMBLYLINKRESOURCE では、コンパイルが含まれている必要があります[/clr](../../build/reference/clr-common-language-runtime-compilation.md);[/LN](../../build/reference/ln-create-msil-module.md)または[/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) /ASSEMBLYLINKRESOURCE で許可されていません。  
  
 場合*filename*作成例についてでの .NET Framework リソース ファイルは、 [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator)または開発環境でアクセスできるメンバー間で、 **System.Resources**名前空間。 詳細については、次を参照してください。 [System.Resources.ResourceManager](https://msdn.microsoft.com/library/system.resources.resourcemanager.aspx)します。 他のすべてのリソースを使用して、**それ以外**\*メソッド、 **System.Reflection.Assembly**実行時にリソースにアクセスするクラス。  
  
 *ファイル名*任意のファイル形式を指定できます。 たとえば、グローバル アセンブリ キャッシュにインストールされているし、アセンブリ内のマネージ コードからアクセスできるように、ネイティブの DLL が、アセンブリの一部を作成したい場合があります。  
  
 アセンブリの生成に影響するその他のリンカー オプションがあります。  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。  
  
2.  をクリックして、**リンカー**フォルダー。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)