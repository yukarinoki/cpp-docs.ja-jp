---
title: コンパイラ エラー C3387 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3387
dev_langs:
- C++
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5469088b6707faa31e1d49157dcbc9991ffb7060
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3387"></a>コンパイラ エラー C3387
'member': 関数/\__declspec(dllimport) は WinRT 型またはマネージのメンバーに適用できません  
  
 `dllimport`と[dllexport](../../cpp/dllexport-dllimport.md) `__declspec`修飾子は、管理対象のメンバーまたは Windows ランタイム型では有効でありません。  
  
 次の例では C3387 を生成し、その修正方法を示しています。  
  
```  
// C3387a.cpp  
// compile with: /clr /c  
ref class X2 {  
   void __declspec(dllexport) mf() {   // C3387  
   // try the following line instead  
   // void mf() {  
   }  
};  
```