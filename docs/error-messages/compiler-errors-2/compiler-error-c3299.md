---
title: コンパイラ エラー C3299 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3299
dev_langs:
- C++
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecaa0b8d3ee1a3d33a5d750cc559da63e036ff16
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3299"></a>コンパイラ エラー C3299
'member_function': 制約を指定できません。それらは基本メソッドから継承されています  
  
 汎用的なメンバー関数をオーバーライドする場合は、制約句を指定できません (制約を繰り返すことは、制約が継承されないことを意味します)。  
  
 オーバーライドするジェネリック関数の制約句が継承されます。  
  
 詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C + + CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では C3299 が生成されます。  
  
```  
// C3299.cpp  
// compile with: /clr /c  
public ref struct R {  
   generic<class T>   
   where T : R  
   virtual void f();  
};  
  
public ref struct S : R {  
   generic<class T>   
   where T : R   // C3299  
   virtual void f() override;  
};  
```