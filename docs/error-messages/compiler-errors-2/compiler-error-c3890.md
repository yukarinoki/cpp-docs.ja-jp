---
title: コンパイラ エラー C3890 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3890
dev_langs:
- C++
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e599150c1e8d62d751f9dca67cffc99fb079bd32
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104925"
---
# <a name="compiler-error-c3890"></a>コンパイラ エラー C3890

'var': リテラル データ メンバーのアドレスを取得することはできません

リテラル データ メンバーは、ガベージ コレクション ヒープに存在します。  アドレスは役に立ちませんため、ガベージ コレクション ヒープ上のオブジェクトを移動できます。

次の例では、C3890 が生成されます。

```
// C3890.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   int p = &Y1::staticConst;   // C3890
   int p2 = Y1::staticConst;   // OK
}
```