---
title: コンパイラ エラー C3320 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08810d38b74081cfb8573d1e33ea3a8ec4dabd4c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254577"
---
# <a name="compiler-error-c3320"></a>コンパイラ エラー C3320
'type': 型には、モジュール 'name' プロパティと同じ名前を指定することはできません  
  
渡されるパラメーターとして、エクスポートされたユーザー定義型 (UDT)、構造体型、クラス、列挙型、または共用体の場合が、同じ名前を持つことはできません、[モジュール](../../windows/module-cpp.md)属性の name プロパティです。  
  
## <a name="example"></a>例  
次の例では C3320 が生成されます。  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```