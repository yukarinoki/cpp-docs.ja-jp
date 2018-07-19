---
title: -KEYFILE (アセンブリに署名するには、キーまたはキー ペアの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
dev_langs:
- C++
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 476fd1e49a8c93363f00215d422a79eda808c321
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378822"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定)
```  
/KEYFILE:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 キーを含むファイルです。 二重引用符で囲まれた文字列に配置 ("")、スペースが含まれている場合。  
  
## <a name="remarks"></a>コメント  
 リンカーは、アセンブリ マニフェストに公開キーを挿入し、最終的なアセンブリを秘密キーで署名します。 キー ファイルを生成する入力[sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename*コマンドライン。 署名されたアセンブリでは、厳密な名前と呼ばれます。  
  
 コンパイルする場合[/LN](../../build/reference/ln-create-msil-module.md)、キー ファイルの名前が、モジュール内に保持しを使用して、モジュールへの明示的な参照を含むアセンブリをコンパイルするときに作成されるアセンブリに組み込む[#using](../../preprocessor/hash-using-directive-cpp.md)とをリンクするとき、または[/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)です。  
  
 リンカーに暗号化の情報を渡すことも[/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)です。 使用して[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)部分署名されているアセンブリを作成する場合。 参照してください[厳密な名前のアセンブリ (アセンブリ署名) (C + + CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)アセンブリに署名する方法についてです。  
  
 場合両方 **/KEYFILE**と **/KEYCONTAINER**が指定されて、リンカーは、キー コンテナーをまず (コマンド ライン オプションまたはカスタム属性によって)、します。 それが成功すると、アセンブリはキー コンテナーの情報で署名されます。 リンカーが、キー コンテナーを見つけられない場合/KEYFILE で指定されたファイルを検索します。 ファイルが検出された場合、アセンブリはキー ファイルの情報で署名され、キー情報はキー コンテナーにインストールされるため (sn -i と同様)、次のコンパイル時にはキー コンテナーが有効になります。  
  
 キー ファイルには公開キーだけが含まれる場合があることに注意してください。  
  
 参照してください[作成と使用](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)アセンブリに署名する方法についてです。  
  
 アセンブリの生成に影響するその他のリンカー オプションは次のとおりです。  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)