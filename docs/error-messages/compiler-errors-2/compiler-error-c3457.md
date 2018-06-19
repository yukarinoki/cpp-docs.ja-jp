---
title: コンパイラ エラー C3457 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3457
dev_langs:
- C++
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99621cfd4f1827763be8ec84d82871290a04652b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249468"
---
# <a name="compiler-error-c3457"></a>コンパイラ エラー C3457
'attribute': 属性は、名前が指定されていない引数をサポートしていません  
  
 CLR カスタム属性やコンパイラ属性とは異なり、ソースの注釈属性は名前付き引数のみをサポートします。  
  
## <a name="example"></a>例  
 次の例では C3457 が生成されます。  
  
```  
#include "SourceAnnotations.h"  
[vc_attributes::Post( 1 )] int f();   // C3457  
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK  
```