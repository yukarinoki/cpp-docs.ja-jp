---
title: -LARGEADDRESSAWARE (大きいアドレスの処理) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
dev_langs:
- C++
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f81424c49c5d67713cf478f69701c52504cfa8c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372127"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (大きいアドレスの処理)
```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 /LARGEADDRESSAWARE オプションは、アプリケーションが、2 ギガバイトを超えるアドレスを処理できることをリンカーに指示します。 64 ビット コンパイラでは、このオプションは既定で有効にします。 32 ビットのコンパイラでは、リンカーのコマンドラインで/LARGEADDRESSAWARE が指定されない場合/LARGEADDRESSAWARE:NO が有効にします。  
  
 アプリケーションが/LARGEADDRESSAWARE、DUMPBIN にリンクされているかどうかは[/HEADERS](../../build/reference/headers.md)それを情報が表示されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**システム**プロパティ ページ。  
  
4.  変更、**大きいサイズのアドレスを有効にする**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)