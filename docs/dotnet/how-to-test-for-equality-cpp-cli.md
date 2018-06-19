---
title: '方法: 等価性をテスト (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- equality, testing for
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c32bd9c73b7251f311593b547d4f3abdd33d7c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127982"
---
# <a name="how-to-test-for-equality-ccli"></a>方法: 等価性をテストする (C++/CLI)
次の例では、c++ マネージ拡張を使用する等値のテストはハンドルの参照先に基づいています。  
  
## <a name="example"></a>例  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 このプログラムの IL では、戻り値が op_Equality への呼び出しを使用して実装されることを示します。  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## <a name="see-also"></a>関連項目  
 [マネージ型 (C++/CLI)](../dotnet/managed-types-cpp-cli.md)