---
title: コンパイラの警告 (レベル 4) C4710 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4710
dev_langs:
- C++
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1cc77d8ee5393fe600ceadd9c1335d76e32efe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4710"></a>コンパイラの警告 (レベル 4) C4710
'function': 関数のインライン関数ではありません  
  
 指定された関数がインライン展開を選択されましたが、コンパイラが実行されなかった、インライン展開されます。  
  
 コンパイラの裁量により、インライン展開が実行されます。 **インライン**キーワードなど、**登録**キーワードは、コンパイラのヒントとして使用します。 コンパイラでは、ヒューリスティックを使用して、インライン、速度にコンパイルするときに、コードを高速化する特定の関数が必要がありますか場合は領域にコンパイルするときは、コードを小さく、特定の関数をインラインにする必要がありますかを確認します。 コンパイラでは、領域用にコンパイルするときに、だけがインライン展開が非常に小規模関数には。  
  
 場合によっては、コンパイラはインライン展開されない特定の関数機械的上の理由からします。 参照してください[C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)一連の理由により、コンパイラがインライン関数ではない可能性があります。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。