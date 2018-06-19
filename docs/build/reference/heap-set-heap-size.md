---
title: -HEAP (ヒープ サイズの設定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
dev_langs:
- C++
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b968b3c8e9063eea897c70d4ae2a62a9a232d6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374558"
---
# <a name="heap-set-heap-size"></a>/HEAP (ヒープ サイズの設定)
```  
/HEAP:reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 /HEAP オプションは、ヒープのサイズをバイト単位で設定します。 このオプションは、.exe ファイルを作成するときにのみで使用します。  
  
 *予約*引数は、仮想メモリの合計ヒープの割り当てを指定します。 既定のヒープ サイズは、1 MB です。 リンカーは、最も近い 4 バイトに指定した値を丸めます。  
  
 省略可能な`commit`引数は、一度に確保する物理メモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 高い`commit`値は、アプリケーションが複数のヒープ領域を必要がありますが、メモリの量と起動時間が増加時間を節約します。  
  
 指定して、*予約*と`commit`10 進数または C 言語表記の値。  
  
 この機能を利用し、モジュール定義ファイルにも[HEAPSIZE](../../build/reference/heapsize.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**システム**プロパティ ページ。  
  
4.  変更、**ヒープ コミット サイズ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)