---
title: コンパイラの警告 (レベル 2) C4285 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4285
dev_langs:
- C++
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27ad828e25f647bddcc8a9ebe9662e2ba61f48d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040696"
---
# <a name="compiler-warning-level-2-c4285"></a>コンパイラの警告 (レベル 2) C4285

戻り値の型の 'identifier::operator ->' は再帰挿入辞表記を使用して適用されている場合

指定した**演算子**関数の型を返すことは定義されているかが定義されている型への参照。

次の例では、C4285 が生成されます。

```
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```