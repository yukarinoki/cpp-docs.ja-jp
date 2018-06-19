---
title: コンパイラの警告 (レベル 4) C4510 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4510
dev_langs:
- C++
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b280a15381f53b6836b321e25717cbed19c7271
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297282"
---
# <a name="compiler-warning-level-4-c4510"></a>コンパイラの警告 (レベル 4) C4510
'class': 既定のコンス トラクターを生成できませんでした  
  
 コンパイラは、指定したクラスに対して既定のコンス トラクターを生成できませんし、ユーザー定義のコンス トラクターは作成されませんでした。 この型のオブジェクトを作成することはできません。  
  
 コンパイラの既定のコンス トラクターの生成を防ぐことがいくつかの状況があるなど。  
  
-   Const データ メンバーです。  
  
-   参照であるデータ メンバーです。  
  
 これらのメンバーを初期化するクラスのユーザー定義の既定コンス トラクターを作成する必要があります。  
  
 次の例では、C4510 が生成されます。  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```