---
title: WINMDDELAYSIGN (部分的に winmd 記号) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs:
- C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c50480fae1f4f3e7421236615d059a642d1074f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375559"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd の部分署名)
ファイルの公開キーを設定することによって、Windows ランタイム メタデータ (.winmd) ファイルの部分に署名を使用できます。  
  
```  
/WINMDDELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 似ています、 [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) .winmd ファイルに適用されるリンカー オプション。 使用して**含める**.winmd ファイルの公開キーのみを配置する場合。 既定では、リンカーは、機能として **/WINMDDELAYSIGN:NO**が指定されました。 winmd ファイルを署名には、しません。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、 **Windows メタデータ**プロパティ ページ。  
  
4.  **Windows メタデータ遅延署名**ドロップダウン リスト ボックスで、目的のオプションを選択します。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)