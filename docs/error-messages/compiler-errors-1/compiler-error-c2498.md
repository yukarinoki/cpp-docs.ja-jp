---
title: コンパイラ エラー C2498 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2498
dev_langs:
- C++
helpviewer_keywords:
- C2498
ms.assetid: 0839f12c-aaa4-4a02-bb33-7f072715dd14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c50596e4e5ca47a0f1bdf3f5ab25405139b66447
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196611"
---
# <a name="compiler-error-c2498"></a>コンパイラ エラー C2498
'function': 'novtable' は、クラス宣言または定義にのみ適用できます  
  
 使用してこのエラーは発生する`__declspec(novtable)`関数を使用します。  
  
## <a name="example"></a>例  
 次の例では、C2498 が生成されます。  
  
```  
// C2498.cpp  
// compile with: /c  
void __declspec(novtable) f() {}   // C2498  
class __declspec(novtable) A {};   // OK  
```