---
title: コンパイラの警告 (レベル 1) C4182 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4182
dev_langs:
- C++
helpviewer_keywords:
- C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79e86076a9d8218d08bd7437e2a06878b6ee91ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278182"
---
# <a name="compiler-warning-level-1-c4182"></a>コンパイラの警告 (レベル 1) C4182
\#入れ子のレベルは 'number' です無限再帰の可能性  
  
 コンパイラがヒープ上の領域を使い切りました。入れ子になっているインクルード ファイルの数が原因です。 インクルード ファイルは、別のインクルード ファイルに含められると入れ子になります。  
  
 このメッセージは情報目的で、エラー [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)に先だって表示されます。