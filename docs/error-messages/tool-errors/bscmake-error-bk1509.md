---
title: BSCMAKE エラー BK1509 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 825d1e1e119aa80445c5ae15804bbdde4a3d8bf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE エラー BK1509
ヒープ スペースがありません。  
  
 BSCMAKE は、仮想メモリを含め、メモリ不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ディスク領域を解放します。  
  
2.  スワップ ファイルのサイズを増やします。  
  
3.  Windows のスワップ ファイルのサイズが増加します。  
  
4.  による/Ei BSCMAKE が必要とするメモリを減らすか、一部を排除/Es 入力ファイルまたはマクロの本体を排除する/Em ください。