---
description: '詳細情報: コンパイラの警告 (レベル 1) C4584'
title: コンパイラの警告 (レベル 1) C4584
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: 32a6b797f7fb0cf2c1a087999c8172e11686e27b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281627"
---
# <a name="compiler-warning-level-1-c4584"></a>コンパイラの警告 (レベル 1) C4584

' class1 ': 基底クラス ' class2 ' は既に ' class3 ' の基底クラスです

定義したクラスは2つのクラスから継承します。1つは他方のクラスを継承します。 次に例を示します。

```cpp
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

この場合、クラス C に対して警告が発行されます。これは、クラス a とクラス B の両方を継承し、クラス A からも継承するためです。この警告は、これらの基本クラスのメンバーの使用を完全に修飾する必要があること、または参照しているクラスメンバーがあいまいであるためにコンパイラエラーが生成されることを示す通知として機能します。
