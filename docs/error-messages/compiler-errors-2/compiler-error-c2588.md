---
title: コンパイラ エラー C2588 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67eb6362ff55e09b05349d10fcdc2377d8ff2996
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2588"></a>コンパイラ エラー C2588
':: ~ identifier': 無効なグローバル デストラクター  
  
 デストラクターは、クラス、構造体、または共用体以外のものに対して定義されます。 これは認められていません。  
  
 このエラーは、不足しているクラス、構造体、または共用体の名前スコープ解決演算子の左側にあるによって発生することができます (`::`) 演算子。  
  
 次の例では、C2588 が生成されます。  
  
```  
// C2588.cpp  
~F();   // C2588  
```