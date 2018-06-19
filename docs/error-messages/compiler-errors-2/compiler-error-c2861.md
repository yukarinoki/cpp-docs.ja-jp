---
title: コンパイラ エラー C2861 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e1f7010ca6d98c4c27f85ecc858cf7703a87e90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247101"
---
# <a name="compiler-error-c2861"></a>コンパイラ エラー C2861
'関数の name': インターフェイスのメンバー関数を定義することはできません  
  
 メンバーを検出し、コンパイラが、インターフェイスのキーワードを発生したか、またはインターフェイスとして構造体を推測が関数の定義。  インターフェイスは、メンバー関数の定義を含めることはできません。  
  
## <a name="example"></a>例  
 次の例では、C2861 が生成されます。  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```