---
title: コンパイラ エラー C2762 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2762
dev_langs:
- C++
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2eebc34608a718e2e1a70f5d8c7e8f02193221cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086214"
---
# <a name="compiler-error-c2762"></a>コンパイラ エラー C2762

'class': 'argument' のテンプレート引数として式が無効です

使用する場合[/Za](../../build/reference/za-ze-disable-language-extensions.md)コンパイラでは、整数をポインターに変換されません。

次の例では、C2762 が生成されます。

```
// C2762.cpp
// compile with: /Za
template<typename T, T *pT>
class X2 {};

void f2() {
   X2<int, 0> x21;   // C2762
   // try the following line instead
   // X2<int, static_cast<int *>(0)> x22;
}
```