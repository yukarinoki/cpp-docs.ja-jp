---
title: コンパイラ エラー C2814 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2814
dev_langs:
- C++
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75215a0df53606c8807cc275e86616c1ae8c6b42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2814"></a>コンパイラ エラー C2814
'member' : ネイティブ型をマネージ型または WinRT 型の 'type' の中に入れ子にすることはできません  
  
## <a name="example"></a>例  
 ネイティブ型を CLR 型または WinRT 型の中に入れ子にすることはできません。 次の例では、C2814 を生成し、その修正方法を示しています。  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
