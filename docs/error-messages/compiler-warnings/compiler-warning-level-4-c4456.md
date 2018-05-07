---
title: コンパイラの警告 (レベル 4) C4456 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4456
dev_langs:
- C++
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ca4af4e7353595dc687b77fa87acf70861bcb6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4456"></a>コンパイラの警告 (レベル 4) C4456
  
> 宣言 '*識別子*' 上のローカル宣言を非表示になります
  
宣言*識別子*ローカル スコープでは、同じ名前の前のローカル宣言の宣言を非表示にします。 この警告を参照するを認識できます。*識別子*ローカル スコープで解決するにはローカルに宣言されたバージョンをいない以前ローカル、またはユーザーの意図ができない可能性があります。 この問題を修正するのには、その他のローカル名と競合しないローカル変数名を付けるお勧めします。  
    
## <a name="example"></a>例
  
次の例では、ループ制御変数のため C4456 が生成されます`int x`し、ローカル変数`double x`で`member_fn`名前が同じです。 この問題を解決するには、ローカル変数の別の名前を使用します。  
  
```cpp  
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        } 
        x += u; // uses local double x
    }
} s;
```  
