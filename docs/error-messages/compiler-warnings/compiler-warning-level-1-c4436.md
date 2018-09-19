---
title: コンパイラの警告 (レベル 1) C4436 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2484b5420347f49a74d8eb3cdf65a8221741cc63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076503"
---
# <a name="compiler-warning-level-1-c4436"></a>コンパイラの警告 (レベル 1) C4436

仮想ベース 'class1' から 'class2' コンス トラクターまたはデストラクターでへの dynamic_cast は/vd2 を部分的に構築されたオブジェクト コンパイルに失敗したり、#pragma vtordisp(2) と ' class2' を有効な定義

コンパイラが検出されましたが、`dynamic_cast`次の特性を持つ操作。

- キャストは、基本クラスのポインターから派生クラスのポインターです。

- 派生クラスは、事実上、基本クラスを継承します。

- 派生クラスがない、`vtordisp`仮想ベースのフィールド。

- コンス トラクターまたは派生クラスのデストラクターで、キャストが見つかったか、さらにいくつかのクラスは、派生クラスから継承します。

警告を示します、`dynamic_cast`部分的に構築されたオブジェクトで動作している場合が、正しく実行されない可能性があります。  さらに派生オブジェクトの下位のオブジェクトで動作している派生コンス トラクターとデストラクターが発生します。  警告でという名前の派生クラスはさらにしない場合、派生した、警告は無視できます。

## <a name="example"></a>例

次の例は、C4436 を生成し、不足しているから発生するコード生成の問題を示します`vtordisp`フィールド。

```cpp
// C4436.cpp
// To see the warning and runtime assert, compile with: /W1
// To eliminate the warning and assert, compile with: /W1 /vd2
//       or compile with: /W1 /DFIX
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
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4436
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

[dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[コンパイラの警告 (レベル 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)