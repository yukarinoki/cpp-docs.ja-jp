---
title: コンパイラ エラー C3645 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3645
dev_langs:
- C++
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a711f37e3ab54de5e3cfad77b82fbd603edfaf6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263828"
---
# <a name="compiler-error-c3645"></a>コンパイラ エラー C3645
'function': _ _clrcall は、ネイティブ コードにコンパイルされた関数では使用できません  
  
 関数内のいくつかのキーワードの有無をネイティブにコンパイルする関数となります。  
  
## <a name="example"></a>例  
 次の例では、C3645 を生成します。  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```