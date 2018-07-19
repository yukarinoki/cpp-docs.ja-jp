---
title: コンパイラ エラー C2045 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2045
dev_langs:
- C++
helpviewer_keywords:
- C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f81e22214cf9f89a2b2bcabe1bc484647d7f9c0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172837"
---
# <a name="compiler-error-c2045"></a>コンパイラ エラー C2045
'identifier' : ラベルが再定義されました  
  
 このラベルは同じ関数内の複数のステートメントの前にあります。  
  
 次の例では C2045 が生成されます。  
  
```  
// C2045.cpp  
int main() {  
   label: {  
   }  
   goto label;  
   label: {}   // C2045  
}  
```