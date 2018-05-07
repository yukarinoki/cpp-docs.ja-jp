---
title: コンパイラ エラー C2506 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2506
dev_langs:
- C++
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5369a6a5bf904f7a7492037fbad4df44de92e66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2506"></a>コンパイラ エラー C2506
'member': '__declspec(modifier)' はこのシンボルに適用することはできません  
  
 マネージ クラスの静的メンバーの場合は、プロセスごとまたは appdomain ごとを宣言できません。  
  
 詳細については、「 [appdomain](../../cpp/appdomain.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C2506 を生成します。  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```