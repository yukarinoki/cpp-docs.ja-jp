---
title: リンカー ツールの警告 LNK4197 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfef7f0fe2d9cd50fa6a18ad682c3e4d80df99c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4197"></a>リンカー ツールの警告 LNK4197
'exportname' が複数回; 指定のエクスポートします。最初の仕様を使用してください。  
  
 エクスポートが複数の指定とさまざまな方法です。 リンカーは、最初の仕様を使用し、残りの部分を無視します。  
  
 C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。  
  
 エクスポートが複数回にまったく同じ方法を指定する場合、リンカーは警告を発行しません。  
  
 たとえば、.def ファイルの次の内容では、この警告が発生します。  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  同じエクスポートが指定されているコマンドラインで両方 (エクスポートによって:) および .def ファイル  
  
2.  同じエクスポートは、異なる属性を持つ .def ファイルに 2 回表示されます。