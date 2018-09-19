---
title: コンパイラ エラー C2139 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2139
dev_langs:
- C++
helpviewer_keywords:
- C2139
ms.assetid: 31e047c0-5bf9-46c2-b6de-b627ea6a5768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8da6a8bb4ca7630a3deff3b1ec79ca512ae2e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090101"
---
# <a name="compiler-error-c2139"></a>コンパイラ エラー C2139

'type': 未定義のクラスがコンパイラの組み込み型の特徴である 'trait' への引数として許可されていません

型の特徴に無効な引数が渡されました。

詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)します。

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