---
title: コンパイラの警告 (レベル 4) C4437 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: dc07e350-20eb-474c-a7ad-f841ae7ec339
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 748ba39d9c22a4071307b8df075eab233f3cfbb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298328"
---
# <a name="compiler-warning-level-4-c4437"></a>コンパイラの警告 (レベル 4) C4437
仮想ベース 'class1' から 'class2' への dynamic_cast でした/vd2 で一部のコンテキスト コンパイルに失敗または #pragma vtordisp(2) と ' class2' を有効に定義します。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 コンパイラが発生しました、`dynamic_cast`次の特性を持つ操作します。  
  
-   キャストは、基底クラスへのポインターから派生クラスへのポインターです。  
  
-   派生クラスは、事実上、基本クラスを継承します。  
  
-   派生クラスがない、`vtordisp`仮想ベースのフィールドです。  
  
-   コンス トラクターまたは、派生クラスのデストラクターでキャストすることが見つからないかをさらにいくつかのクラスは、派生クラス (それ以外の場合、コンパイラの警告 C4436 が発行される) から継承します。  
  
 警告には、ことを示します、`dynamic_cast`部分的に構築されるオブジェクトで動作している場合、正常に実行いない可能性があります。  このような状況では、外側の関数がコンス トラクターまたは、警告で指定されている派生クラスを継承するクラスのデストラクターから呼び出された場合に発生します。  警告で指定されている派生クラスがさらにされていない場合は、次の派生、またはオブジェクトの構築または破棄中に、外側の関数は呼び出されません、警告を無視することができます。  
  
## <a name="example"></a>例  
 次の例は、C4437 を生成し、欠落しているから発生するコードの生成の問題を示しています`vtordisp`フィールドです。  
  
```cpp  
// C4437.cpp  
// To see the warning and runtime assert, compile with: /W4  
// To eliminate the warning and assert, compile with: /W4 /vd2  
//       or compile with: /W4 /DFIX  
#pragma warning(default : 4437)  
#include <cassert>  
  
struct A  
{  
public:  
    virtual ~A() {}  
};  
  
#if defined(FIX)  
#pragma vtordisp(push, 2)  
#endif  
struct B : virtual A  
{  
    B()  
    {  
        func();  
    }  
  
    void func()  
    {  
        A* a = static_cast<A*>(this);  
        B* b = dynamic_cast<B*>(a);     // C4437  
        assert(this == b);              // assert unless compiled with /vd2  
    }  
};  
#if defined(FIX)  
#pragma vtordisp(pop)  
#endif  
  
struct C : B  
{  
    int i;  
};  
  
int main()  
{  
    C c;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)   
 [vtordisp](../../preprocessor/vtordisp.md)   
 [コンパイラの警告 (レベル 1) C4436](../../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)