---
title: -固定 (固定ベース アドレス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08b1193b7cfe58aed45e4feec598a49227eafc87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374162"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (固定ベース アドレス)
```  
/FIXED[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 オペレーティング システムに、指定されたベース アドレスにだけプログラムを読み込むように指示します。 指定したベース アドレスが使用できない場合、オペレーティング システムはファイルを読み込みません。 詳細については、「[/BASE (ベース アドレス)](../../build/reference/base-base-address.md)」を参照してください。  
  
 DLL には /FIXED:NO が既定で使用されます。他のすべての種類のプロジェクトには /FIXED が既定で使用されます。  
  
 /FIXED オプションを指定すると、プログラム内に再配置セクションが作成されなくなります。 実行時にオペレーティング システムが指定されたアドレスにプログラムを読み込むことができない場合は、エラー メッセージが表示され、プログラムが読み込まれなくなります。  
  
 /FIXED:NO を指定すると、プログラム内に再配置セクションが生成されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  オプション名を入力し、設定、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)