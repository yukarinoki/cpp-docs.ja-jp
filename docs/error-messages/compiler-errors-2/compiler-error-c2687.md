---
title: コンパイラ エラー C2687 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2687
dev_langs:
- C++
helpviewer_keywords:
- C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b54c3be7a3706dd5471b21c2a1779e9990eae678
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233019"
---
# <a name="compiler-error-c2687"></a>コンパイラ エラー C2687
'type': 例外宣言の 'void' または不完全な型、ポインター、または不完全な型への参照を表すことはできません  
  
 例外宣言の一部である型の場合は、定義済みでない void があります。  
  
 次の例では、C2687 が生成されます。  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```