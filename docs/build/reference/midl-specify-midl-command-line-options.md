---
title: -MIDL (MIDL コマンド ライン オプションの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d125042041af1e20b6dfc4a02197c2124adbeb9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375189"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL コマンド ライン オプションの指定)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 `file`  
 格納しているファイルの名前[MIDL コマンド ライン オプション](http://msdn.microsoft.com/library/windows/desktop/aa366839)です。  
  
## <a name="remarks"></a>コメント  
 IDL ファイルの TLB ファイルへの変換のすべてのオプションを指定する必要があります`file`です。MIDL コマンド ライン オプションは、リンカーのコマンドラインで指定できません。 /MIDL が指定されていない場合は、IDL ファイル名のみとその他のオプションはなし MIDL コンパイラが呼び出されます。  
  
 ファイルは、1 行につき 1 つの MIDL コマンド ライン オプションを含める必要があります。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**埋め込み IDL**プロパティ ページ。  
  
4.  変更、 **MIDL コマンド**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [/IDLOUT (MIDL の出力ファイルの名前を付ける)](../../build/reference/idlout-name-midl-output-files.md)   
 [/IGNOREIDL (しない属性の処理を MIDL に挿入)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/TLBOUT (名前です。TLB ファイル)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [属性付きプログラムの作成](../../windows/building-an-attributed-program.md)