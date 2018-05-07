---
title: コンパイラ エラー C2570 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2570
dev_langs:
- C++
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b870ddd8bb162f4f65bd3200c397f912249304b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2570"></a>コンパイラ エラー C2570
'identifier': 共用体は基底クラスを持つことはできません  
  
 共用体は、クラス、構造体、または共用体から派生します。 これは認められていません。 代わりに、クラスまたは構造体として、派生型を宣言します。  
  
 次の例では、C2570 が生成されます。  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```