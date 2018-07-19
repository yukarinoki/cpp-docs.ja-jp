---
title: コンパイラ エラー C3254 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e58976b1562e6cca9aa343401b5d2c3f856de1a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255609"
---
# <a name="compiler-error-c3254"></a>コンパイラ エラー C3254
'明示的なオーバーライド': クラスは、明示的なオーバーライド 'override' が含まれていますが、関数の宣言を格納しているインターフェイスから派生していません  
  
 ときに、[を明示的にオーバーライド](../../cpp/explicit-overrides-cpp.md)メソッド オーバーライドを含むクラス必要があります、直接または間接的に派生、オーバーライドする関数を含む型からです。  
  
 次の例では、C3254 が生成されます。  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```