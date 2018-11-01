---
title: コンパイラ エラー C3892
ms.date: 11/04/2016
f1_keywords:
- C3892
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
ms.openlocfilehash: 07f34efa4ecf1445665fccf60dba10ea12dbff3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468667"
---
# <a name="compiler-error-c3892"></a>コンパイラ エラー C3892

'var': const である変数に割り当てることはできません

Const 変数は、宣言および初期化後に変更することはできません。

次の例では、C3892 が生成されます。

```
// C3892.cpp
// compile with: /clr
ref struct Y1 {
   static const int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3892
}
```