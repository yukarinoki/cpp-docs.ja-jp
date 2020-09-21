---
title: コンパイラ エラー C2249
ms.date: 11/04/2016
f1_keywords:
- C2249
helpviewer_keywords:
- C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
ms.openlocfilehash: ac396fe5fa3505311f5a45ebb49dae283e35248c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741416"
---
# <a name="compiler-error-c2249"></a>コンパイラ エラー C2249

' member ': 仮想基底クラス ' class ' で宣言されているアクセスメンバーへのアクセス可能なパスがありません

は、非 `member` パブリックな **`virtual`** 基本クラスまたは構造体から継承されます。

## <a name="examples"></a>例

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
