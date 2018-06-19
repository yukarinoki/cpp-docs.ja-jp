---
title: リソース コンパイラの致命的なエラー RC1002 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1002
dev_langs:
- C++
helpviewer_keywords:
- RC1002
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 886b44d0a51df10295428daa69c8ea358660fd25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321666"
---
# <a name="resource-compiler-fatal-error-rc1002"></a>リソース コンパイラの致命的なエラー RC1002
ヒープ スペースがありません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  Windows のスワップ ファイルの領域を増やします。 詳細については、スワップ ファイルの容量を増やすと、Windows のヘルプ内の仮想メモリを参照してください。  
  
2.  小さなファイルに現在のファイルに分割し、個別にコンパイルします。  
  
3.  その他のプログラムまたはシステムで実行されているドライバーを削除します。