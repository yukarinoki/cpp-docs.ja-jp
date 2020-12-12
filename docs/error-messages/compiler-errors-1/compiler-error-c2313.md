---
description: 詳細については、「コンパイラエラー C2313」を参照してください。
title: コンパイラ エラー C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 455bc3a833f576c051ff1531d921f8504789810e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282159"
---
# <a name="compiler-error-c2313"></a>コンパイラ エラー C2313

'type1': 行番号の参照 ('type2') でキャッチされます

例外の型には 2 つのハンドラーがあります。 2 番目の catch の型は、最初の型への参照です。

次の例では C2313 が生成されます。

```cpp
// C2313.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
    try {
        throw "ooops!";
    }
    catch( C& ) {}
    catch( C ) {}   // C2313
}
```
