---
description: 詳細については、「コンパイラエラー C2733」を参照してください。
title: コンパイラエラー C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: f957be13b8c1de1ee3ada98ffd42f0d89fc7755c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123202"
---
# <a name="compiler-error-c2733"></a>コンパイラエラー C2733

オーバーロードされた関数 ' function ' の2番目の C リンケージは使用できません

複数のオーバーロードされた関数が C リンケージで宣言されています。 C リンケージを使用する場合、指定された関数の1つの形式のみが外部になることができます。 オーバーロードされた関数は、同じ非装飾名を持つため、C プログラムでは使用できません。

次の例では、C2733 が生成されます。

```cpp
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
