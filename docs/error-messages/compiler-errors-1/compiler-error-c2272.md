---
title: コンパイラ エラー C2272 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2272
dev_langs:
- C++
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e969e7cadadf1102dadfb8089a847046731b568f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171768"
---
# <a name="compiler-error-c2272"></a>コンパイラ エラー C2272
'function': 修飾子の静的メンバー関数では使用できません  
  
 A`static`などメンバー関数が、メモリ モデルの指定子で宣言されて[const](../../cpp/const-cpp.md)または[揮発性](../../cpp/volatile-cpp.md)でそのような修飾子は使用できません、`static`メンバー関数。  
  
 次の例では、C2272 が生成されます。  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```