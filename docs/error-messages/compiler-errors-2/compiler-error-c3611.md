---
title: コンパイラ エラー C3611 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3611
dev_langs:
- C++
helpviewer_keywords:
- C3611
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdd09d86eac5e6182adb9f012c0e450b92d410b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252013"
---
# <a name="compiler-error-c3611"></a>コンパイラ エラー C3611
'function': シール関数は純粋指定子を持つことはできません  
  
 封印された関数の宣言が正しくありません。  詳細については、次を参照してください。[シール](../../windows/sealed-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3611 を生成します。  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```