---
title: コンパイラ エラー C3749 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3749
dev_langs:
- C++
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78de0c696123375c11e5c11e64223858b57451ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3749"></a>コンパイラ エラー C3749
'attribute': 関数内のカスタム属性で使用できません可能性があります  
  
 関数内のカスタム属性で使用できません。 カスタム属性の詳細については、トピックを参照してください。[属性](../../windows/attribute.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3749 が生成されます。  
  
```  
// C3749a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref struct ABC : public Attribute {  
   ABC() {}  
};  
  
void f1() { [ABC]; };  // C3749  
```  
