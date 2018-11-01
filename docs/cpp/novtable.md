---
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 9dcca6ec07a19d53da238020805299b652cbf919
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630244"
---
# <a name="novtable"></a>novtable

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

これは、 **_ _declspec**拡張属性。

この形式の **_ _declspec**任意のクラス宣言に適用できますが、自分でインスタンス化されないクラスを示す、純粋なインターフェイス クラスにのみ適用する必要があります。 **_ _Declspec**のコンス トラクターおよびクラスのデストラクターの vfptr を初期化するコードの生成を停止します。 多くの場合、これは、クラスに関連付けられている vtable への参照のみを削除するので、リンカーはこれを削除します。 このような形態を使用して **_ _declspec**コードのサイズが大幅に短縮されることができます。

マークされたクラスをインスタンス化しようとした場合**novtable**およびクラス メンバーにアクセスし、アクセス違反 (AV) が表示されます。

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

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)