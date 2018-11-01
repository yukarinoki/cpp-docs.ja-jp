---
title: コンパイラ エラー C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 26819f1928223b5fa96d275290105f32787057f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518847"
---
# <a name="compiler-error-c2733"></a>コンパイラ エラー C2733

C リンケージの 2 つ目のオーバー ロードされた関数 'function' が許可されていません

1 つ以上のオーバー ロードされた関数は C リンケージで宣言します。 C リンケージを使用する場合、指定された関数の 1 つだけの形式は外部できます。 装飾されていない名前が同じであるオーバー ロードされた関数からは、C プログラムで使用できません。

次の例では、C2733 が生成されます。

```
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```