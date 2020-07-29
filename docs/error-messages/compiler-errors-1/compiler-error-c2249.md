---
title: コンパイラ エラー C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: f50cb27a239e794b87a15920a36e96529bd6a466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212801"
---
# <a name="compiler-error-c2249"></a>コンパイラ エラー C2249

' member ': 仮想基底クラス ' class ' で宣言されているアクセスメンバーへのアクセス可能なパスがありません

は、非 `member` パブリックな **`virtual`** 基本クラスまたは構造体から継承されます。

## <a name="example"></a>例

次の例では、C2249 が生成されます。

```cpp
// C2249.cpp
class A {
private:
   void privFunc( void ) {};
public:
   void pubFunc( void ) {};
};

class B : virtual public A {} b;

int main() {
   b.privFunc();    // C2249, private member of A
   b.pubFunc();    // OK
}
```

## <a name="example"></a>例

C2249 は、C++ 標準ライブラリから別のストリームにストリームを割り当てようとした場合にも発生する可能性があります。  次の例では、C2249 が生成されます。

```cpp
// C2249_2.cpp
#include <iostream>
using namespace std;
int main() {
   cout = cerr;   // C2249
   #define cout cerr;   // OK
}
```
