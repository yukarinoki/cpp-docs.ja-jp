---
title: コンパイラの警告 (レベル 1) C4910 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34ed2ec16f579b05a572cf6bfc236cd8d5743f63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910
'\<識別子 >': '関数' と 'extern' 明示的なインスタンス化に互換性がありません  
  
 という名前の明示的なテンプレート インスタンス化*\<識別子 >* 両方によって変更、`__declspec(dllexport)`と`extern`キーワード。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [明示的なインスタンス化](../../cpp/explicit-instantiation.md)   
 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)   
 [一般的な規則と制約](../../cpp/general-rules-and-limitations.md)