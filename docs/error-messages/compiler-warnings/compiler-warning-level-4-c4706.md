---
title: コンパイラの警告 (レベル 4) C4706 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1131147a9600525746cb3e89119189ed9e5026a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296970"
---
# <a name="compiler-warning-level-4-c4706"></a>コンパイラの警告 (レベル 4) C4706
条件式内の割り当て  
  
 条件式のテスト値を代入式の結果をでした。  
  
 代入式では、法的なテスト式など、別の式で使用できる値 (割り当ての左側にある値) があります。  
  
 次の例では、C4706 が生成されます。  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 この警告は、テスト条件を囲むかっこは 2 倍にする場合でも発生します。  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 リレーションシップをテストし、割り当てを行うが使用する場合、`==`演算子。 たとえば、次のようにするかどうか、b が等しいとします。  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 値を代入式の結果、テストを作成する場合は、割り当てが 0 以外、または null でないことを確認するテストします。 たとえば、次のコードには、この警告は生成されません。  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```