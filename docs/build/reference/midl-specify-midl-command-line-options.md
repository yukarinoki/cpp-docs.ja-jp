---
title: -MIDL (MIDL コマンド ライン オプションの指定) |Microsoft Docs
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
ms.openlocfilehash: 7fc5e4b0b3e19f9a71e1ada445181bede68d65a5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222682"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL コマンド ライン オプションの指定)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>Remarks  
 それぞれの文字について以下に説明します。  
  
 `file`  
 含むファイルの名前[MIDL コマンド ライン オプション](/windows/desktop/Midl/general-midl-command-line-syntax)します。  
  
## <a name="remarks"></a>Remarks  
 IDL ファイル TLB ファイルへの変換のすべてのオプションを指定する必要があります`file`;MIDL コマンド ライン オプションは、リンカーのコマンドラインで指定できません。 /MIDL が指定されていない場合は、IDL ファイル名のみとしないその他のオプション、MIDL コンパイラが呼び出されます。  
  
 ファイルには、1 行につき 1 つの MIDL コマンド ライン オプションを含める必要があります。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。  
  
2.  をクリックして、**リンカー**フォルダー。  
  
3.  をクリックして、**埋め込み IDL**プロパティ ページ。  
  
4.  変更、 **MIDL コマンド**プロパティ。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [/IDLOUT (MIDL 出力ファイルの名前)](../../build/reference/idlout-name-midl-output-files.md)   
 [/IGNOREIDL (を MIDL に挿入に属性を処理しない)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/TLBOUT (名前です。TLB ファイル)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [属性付きプログラムの作成](../../windows/building-an-attributed-program.md)