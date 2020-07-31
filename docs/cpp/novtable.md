---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: ccf544608bcba83af17702767562ef93d775b5a9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227258"
---
# <a name="novtable"></a>novtable

**Microsoft 固有の仕様**

これは **`__declspec`** 拡張属性です。

この形式のは **`__declspec`** 任意のクラス宣言に適用できますが、純粋なインターフェイスクラス、つまり独自にインスタンス化されないクラスにのみ適用する必要があります。 は、 **`__declspec`** クラスのコンストラクターとデストラクターの vfptr を初期化するコードを生成しないようにします。 多くの場合、これは、クラスに関連付けられている vtable への参照のみを削除するので、リンカーはこれを削除します。 この形式のを使用する **`__declspec`** と、コードサイズが大幅に削減されます。

でマークされたクラスをインスタンス化し **`novtable`** てからクラスメンバーにアクセスしようとすると、アクセス違反 (AV) が発生します。

## <a name="example"></a>例

```cpp
// novtable.cpp
#include <stdio.h>

struct __declspec(novtable) X {
   virtual void mf();
};

struct Y : public X {
   void mf() {
      printf_s("In Y\n");
   }
};

int main() {
   // X *pX = new X();
   // pX->mf();   // Causes a runtime access violation.

   Y *pY = new Y();
   pY->mf();
}
```

```Output
In Y
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`__declspec`](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
