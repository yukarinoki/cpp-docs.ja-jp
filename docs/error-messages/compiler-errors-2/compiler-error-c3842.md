---
title: コンパイラ エラー C3842 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c29878f7d64bfe1ed444130c77461dece6d20302
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3842"></a>コンパイラ エラー C3842
WinRT またはマネージ型のメンバー関数に対する 'function': 'const' および 'volatile' 修飾子はサポートされていません  
  
 [const](../../cpp/const-cpp.md)と[揮発性](../../cpp/volatile-cpp.md)は、Windows ランタイムまたはマネージ型のメンバー関数ではサポートされていません。  
  
 次の例では C3842 が生成されます。  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
```