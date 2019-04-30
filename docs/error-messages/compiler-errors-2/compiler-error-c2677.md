---
title: コンパイラ エラー C2677
ms.date: 11/04/2016
f1_keywords:
- C2677
helpviewer_keywords:
- C2677
ms.assetid: 76bc0b65-f52a-45a6-b6d6-0555f89da9a8
ms.openlocfilehash: 1be3701c2befbacc11d6a3dea4b99547375286d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395418"
---
# <a name="compiler-error-c2677"></a>コンパイラ エラー C2677

二項 'operator': 型 'type' 項グローバル演算子が見つかりません (または、変換はありません)

この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。

次の例では、C2677 が生成されます。

```
// C2677.cpp
class C {
public:
   C(){}
} c;

class D {
public:
   D(){}
   operator int(){return 0;}
} d;

int main() {
   int i = 1 >> c;   // C2677
   int j = 1 >> d;   // OK operator int() defined
}
```