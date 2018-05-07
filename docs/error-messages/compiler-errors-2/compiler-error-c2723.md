---
title: コンパイラ エラー C2723 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2723
dev_langs:
- C++
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01476218683205d0fb06e81847cfe9727b733158
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2723"></a>コンパイラ エラー C2723
'function' : 'specifier' 指定子が関数の定義で誤って指定されています  
  
 この指定子は、クラス宣言の外側にある関数定義では使用できません。 `virtual` 指定子は、クラス宣言内のメンバー関数宣言にしか指定できません。  
  
 次の例では、C2723 を生成し、その修正方法を示しています。  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```