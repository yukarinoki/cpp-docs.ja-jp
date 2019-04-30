---
title: コンパイラ エラー C2139
ms.date: 11/04/2016
f1_keywords:
- C2139
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
ms.openlocfilehash: 15813216399c0f00fea036cd95443235e7acf4c3
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344898"
---
# <a name="compiler-error-c2139"></a>コンパイラ エラー C2139

'type': 未定義のクラスがコンパイラの組み込み型の特徴である 'trait' への引数として許可されていません

型の特徴に無効な引数が渡されました。

詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、に対して C2139 が生成されます。

```
// C2139.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class C;
class D {};

class E {
public:
   virtual void Test() {}
};

int main() {
   cout << is_polymorphic<C>::value << endl;   // C2139
   cout << is_polymorphic<D>::value << endl;   // OK
   cout << is_polymorphic<E>::value << endl;   // OK
}
```