---
title: コンパイラの警告 (レベル 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: 031b32a03d93a51f6fa00041a5b0bdf99e6eacf1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401996"
---
# <a name="compiler-warning-level-3-c4373"></a>コンパイラの警告 (レベル 3) C4373

> '*関数*': 仮想関数のオーバーライド*base_function*'、const/volatile 修飾子によってのみと一致しませんパラメーターの場合、以前のバージョンのコンパイラはオーバーライドしませんでした。

## <a name="remarks"></a>Remarks

アプリケーションには、基底クラスの仮想メソッドをオーバーライドする派生クラスのメソッドが含まれ、オーバーライドする側のメソッドのパラメーターは、 [const](../../cpp/const-cpp.md) または [volatile](../../cpp/volatile-cpp.md) 修飾子についてのみ、仮想メソッドのパラメーターと異なります。 つまり、コンパイラでは、基底クラスまたは派生クラスのいずれかにおけるメソッドに、関数参照をバインドする必要があります。

バージョンの Visual Studio 2008 より前のコンパイラは、関数、基底クラスのメソッドをバインドし、警告メッセージを発行します。 以降のバージョンのコンパイラを無視する、`const`または`volatile`修飾子は、関数、派生クラスでメソッドをバインドし、警告を発行**C4373**します。 この後者の動作は、C++ 標準に準拠しています。

## <a name="example"></a>例

次のコード例では、警告 C4373 が生成されます。 この問題を解決するには、基本メンバー関数として同じ CV 修飾子を使用して、上書きを行うことができますか、または別の名前を派生クラスで関数を提供することができますに上書きを作成しなかった場合。

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```