---
title: コンパイラ エラー C3699 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3699
dev_langs:
- C++
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ddbf6ac43b2a3d987faa86fab6d9862068fc0fe0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3699"></a>コンパイラ エラー C3699
'operator': 型 'type' でこの間接指定を使用することはできません  
  
 許可されていない間接指定を使用しようとしましたが`type`です。  
  
## <a name="example"></a>例  
 次の例では、C3699 を生成します。  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## <a name="example"></a>例  
 Trivial プロパティには、参照型を持つことはできません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。 次の例では、C3699 を生成します。  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## <a name="example"></a>例  
 「ポインターへのポインター」構文の該当するショートカットは、追跡参照にハンドルです。 次の例では、C3699 を生成します。  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```