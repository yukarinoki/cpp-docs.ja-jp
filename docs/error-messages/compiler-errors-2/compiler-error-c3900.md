---
title: コンパイラ エラー C3900 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3900
dev_langs:
- C++
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc940d174edc337422818bc233c1ef9952b66276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3900"></a>コンパイラ エラー C3900
'member': 現在のスコープで許可されていません  
  
 プロパティ ブロックには、関数の宣言とインライン関数の定義のみを含めることができます。 プロパティ ブロックでは、関数以外のメンバーは許可されません。 Typedef、演算子、または friend 関数は許可されません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
 イベントの定義には、アクセス メソッドおよび関数のみを含めることができます。  
  
 次の例では、C3900 が生成されます。  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 次の例では、C3900 が生成されます。  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```