---
title: コンパイラの警告 (レベル 1) C4441 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4441
dev_langs:
- C++
helpviewer_keywords:
- C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2abf64be0e9b80bb4158b0ed163906adc09945
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278230"
---
# <a name="compiler-warning-level-1-c4441"></a>コンパイラの警告 (レベル 1) C4441
無視されます。 'cc1' の呼び出し規約'、' cc2 代わりに  
  
 管理対象のユーザー定義型とグローバル関数のジェネリック メンバー関数を使用する必要があります、 [_ _clrcall](../../cpp/clrcall.md)呼び出し規約です。  使用されるコンパイラ`__clrcall`です。  
  
## <a name="example"></a>例  
 次の例では、C4441 を生成します。  
  
```  
// C4441.cpp  
// compile with: /clr /W1 /c  
generic <class ItemType>  
void __cdecl Test(ItemType item) {}   // C4441  
// try the following line instead  
// void Test(ItemType item) {}  
  
ref struct MyStruct {  
   void __cdecl Test(){}   // C4441  
   void Test2(){}   // OK  
};  
```