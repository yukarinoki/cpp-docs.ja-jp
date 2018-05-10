---
title: -CLRTHREADATTRIBUTE (CLR スレッド属性を設定する) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
dev_langs:
- C++
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b83c3df380b07f125bad8426b9bf18b013b606c8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (CLR スレッド属性の設定)
CLR プログラムのエントリ ポイントにスレッド属性を明示的に指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### <a name="parameters"></a>パラメーター  
 MTA  
 MTAThreadAttribute 属性をプログラムのエントリ ポイントに適用します。  
  
 [なし]  
 /CLRTHREADATTRIBUTE を指定しないと同じです。  既定のスレッド属性を設定する共通言語ランタイム (CLR) を付与します。  
  
 STA  
 STAThreadAttribute 属性をプログラムのエントリ ポイントに適用します。  
  
## <a name="remarks"></a>コメント  
 スレッド属性設定のみです、.exe を構築するときに、メイン スレッドのエントリ ポイントに影響するため。  
  
 使用する場合は、(main または wmain など) の既定のエントリ ポイントを指定、スレッディング モデルを使用/CLRTHREADATTRIBUTE または配置することによって、スレッド処理属性 (STAThreadAttribute または MTAThreadAttribute) に既定のエントリ関数。  
  
 既定以外のエントリ ポイントを使用する場合は、既定以外のエントリの関数に属性を既定以外のエントリ ポイントを指定し、/CLRTHREADATTRIBUTE を使用するか、スレッド処理を配置することによって、スレッディング モデルを指定[/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
 ソース コードで指定されたスレッド モデルが/CLRTHREADATTRIBUTE で指定されたスレッド モデルと一致していない場合、リンカーは/CLRTHREADATTRIBUTE を無視して、ソース コードで指定されたスレッド モデルを適用します。  
  
 CLR プログラムは、シングル スレッドを使用する COM オブジェクトをホストしている場合はたとえば、シングル スレッドを使用するために必要になります。  マルチ スレッドを使用する CLR プログラム場合、シングル スレッドを使用する COM オブジェクトをホストできません。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、 **CLR スレッド属性**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)