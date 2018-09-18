---
title: コンパイラ エラー C2267 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2267
dev_langs:
- C++
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 080f6ebfda8dbdaa1f0bf70faa3b6d5c7545d66e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035267"
---
# <a name="compiler-error-c2267"></a>コンパイラ エラー C2267

'function': ブロック スコープを持つ静的関数は無効です

ローカル関数が宣言されている`static`します。 静的関数は、グローバル スコープを設定する必要があります。

次の例では、C2267 が生成されます。

```
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```