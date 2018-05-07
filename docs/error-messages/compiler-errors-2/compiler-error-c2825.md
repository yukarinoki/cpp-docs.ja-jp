---
title: コンパイラ エラー C2825 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2825
dev_langs:
- C++
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5352901d50e011229ed9aa4715923881c26a8fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2825"></a>コンパイラ エラー C2825
var: クラスまたは名前空間が続くと必要があります ':: '  
  
 失敗したときは、修飾名を形成するしました。  
  
 たとえば、コードに関数名が始まる関数宣言が含まれていないことを確認:: です。  
  
## <a name="example"></a>例  
 次の例では、C2825 が生成されます。  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```