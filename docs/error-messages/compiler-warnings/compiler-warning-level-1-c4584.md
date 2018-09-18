---
title: コンパイラの警告 (レベル 1) C4584 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9db97bf35034f7ca628f860924bfb9a1fccc942f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036255"
---
# <a name="compiler-warning-level-1-c4584"></a>コンパイラの警告 (レベル 1) C4584

'class1': 基底クラス 'class2' が 'class3' の基底クラスでは既に

定義したクラスは、うちの 1 つが継承、他の 2 つのクラスから継承します。 例えば:

```
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

この場合、警告がクラス C に発行されますクラス A と B で、クラス A からも継承クラスの両方から継承するためこの警告は、これらの基本クラスからメンバーの使用を完全に修飾する必要がありますか、参照するどのクラスのメンバーか、あいまいさのため、コンパイラ エラーが生成されることを知らせるリマインダーとして機能します。