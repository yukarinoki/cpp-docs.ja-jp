---
title: 致命的なエラー C1055 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07f0dc0e8dca08e8b0de47b73516d3fdfa21435b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225343"
---
# <a name="fatal-error-c1055"></a>致命的なエラー C1055
コンパイラの制限: キーが足りません  
  
 ソース ファイルには、多数のシンボルが含まれています。 コンパイラは、シンボル テーブルのハッシュ キー不足になりました。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  ソース ファイルを小さなファイルに分割します。  
  
2.  不要なヘッダー ファイルを削除します。  
  
3.  新しいファイルを作成する代わりに一時とグローバル変数を再利用できます。