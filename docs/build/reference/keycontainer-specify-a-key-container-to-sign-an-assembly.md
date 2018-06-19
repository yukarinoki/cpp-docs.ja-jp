---
title: -KEYCONTAINER (アセンブリに署名するキー コンテナーの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13058978b0833a17abbbfb68a2ed753aacfb6d49
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377888"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定)
```  
/KEYCONTAINER:name  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 *name*  
 キーを格納するコンテナーです。 二重引用符で囲まれた文字列に配置 ("")、スペースが含まれている場合。  
  
## <a name="remarks"></a>コメント  
 リンカーは、アセンブリ マニフェストに公開キーを挿入し、秘密キーを含む、最終的なアセンブリの署名によって署名されたアセンブリを作成します。 キー ファイルを生成する入力[sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename*コマンドライン。 **sn-i**コンテナーにキーのペアをインストールします。  
  
 コンパイルする場合[/LN](../../build/reference/ln-create-msil-module.md)、キー ファイルの名前が、モジュール内に保持しを使用して、モジュールへの明示的な参照を含むアセンブリをコンパイルするときに作成されるアセンブリに組み込む[#using](../../preprocessor/hash-using-directive-cpp.md)とをリンクするとき、または[/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)です。  
  
 コンパイラに、暗号化情報を渡すことができますも[/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)です。 使用して[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)部分署名されているアセンブリを作成する場合。 参照してください[厳密な名前のアセンブリ (アセンブリ署名) (C + + CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)アセンブリに署名する方法についてです。  
  
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