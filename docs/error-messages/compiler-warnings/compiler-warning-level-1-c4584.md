---
title: コンパイラの警告 (レベル 1) C4584
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: 3c60575e766ea3490a40711fe26c3e402c41fbdd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397251"
---
# <a name="compiler-warning-level-1-c4584"></a>コンパイラの警告 (レベル 1) C4584

'class1': 基底クラス 'class2' が 'class3' の基底クラスでは既に

定義したクラスは、うちの 1 つが継承、他の 2 つのクラスから継承します。 例:

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