---
description: '詳細情報: コンパイラの警告 (レベル 1) C4436'
title: コンパイラの警告 (レベル 1) C4436
ms.date: 11/04/2016
f1_keywords:
- C4436
helpviewer_keywords:
- C4436
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
ms.openlocfilehash: 78d6ab1d6b80c06448b6dfdd8401cb9fd2d76b02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212598"
---
# <a name="compiler-warning-level-1-c4436"></a>コンパイラの警告 (レベル 1) C4436

コンストラクターまたはデストラクター内の仮想ベース ' class1 ' から ' class2 ' への dynamic_cast は、/vd2 を使用して部分的に構築されたオブジェクトで失敗するか、#pragma vtordisp (2) が有効な ' class2 ' を定義しています。

コンパイラで、 **`dynamic_cast`** 次の特性を持つ操作が検出されました。

- キャストは、基底クラスポインターから派生クラスポインターへのキャストです。

- 派生クラスは、実質的に基底クラスを継承します。

- 派生クラスに `vtordisp` 仮想ベースのフィールドがありません。

- キャストは、派生クラスのコンストラクターまたはデストラクター、または派生クラスからさらに継承するクラスにあります。

警告は、が **`dynamic_cast`** 部分的に構築されたオブジェクトで動作している場合に、が正しく動作しない可能性があることを示します。  これは、派生コンストラクターまたはデストラクターが、さらに派生したオブジェクトのサブオブジェクト上で動作している場合に発生します。  警告で指定された派生クラスがそれ以上派生していない場合は、警告を無視できます。

## <a name="example"></a>例

次の例では、C4436 を生成し、不足しているフィールドから発生するコード生成の問題を示し `vtordisp` ます。

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
