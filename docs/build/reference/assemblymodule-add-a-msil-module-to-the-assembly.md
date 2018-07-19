---
title: -ASSEMBLYMODULE (MSIL モジュールをアセンブリに追加) |Microsoft ドキュメント
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
ms.openlocfilehash: f408bcf58808f64c652f0b1715c47aba7237c160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373856"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加)
```  
/ASSEMBLYMODULE:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 このアセンブリに追加するモジュールです。  
  
## <a name="remarks"></a>コメント  
 /ASSEMBLYMODULE オプションでは、モジュールの参照をアセンブリに追加することができます。 モジュールの型情報はモジュール参照を追加したアセンブリ プログラムを利用できません。 ただし、モジュール内の型情報は、アセンブリを参照するプログラムで使用可能になります。  
  
 使用して[#using](../../preprocessor/hash-using-directive-cpp.md)アセンブリへのモジュール参照を追加およびモジュールの種類の情報をアセンブリのプログラムを利用できるようにします。  
  
 たとえば、次の場合を考えてください。  
  
1.  持つモジュールを作成する[/LN](../../build/reference/ln-create-msil-module.md)です。  
  
2.  別のプロジェクトにモジュールをアセンブリの作成は、現在のコンパイルに含める/ASSEMBLYMODULE を使用します。 このプロジェクトでは、モジュールでは参照されません`#using`です。  
  
3.  また、このアセンブリを参照する他のプロジェクトでは、モジュールから型を使用できますようになりました。  
  
 アセンブリの生成に影響するその他のリンカー オプションは次のとおりです。  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 Visual C リンカーは、入力として .netmodule ファイルを受け入れるし、アセンブリまたは .netmodule ない実行時の依存をリンカー入力した .netmodule のいずれかのリンカーによって生成される出力ファイルが表示されます。  詳細については、「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**入力**プロパティ ページ。  
  
4.  変更、**モジュールをアセンブリに追加**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)