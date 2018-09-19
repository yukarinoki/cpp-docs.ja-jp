---
title: コンパイラ エラー C2733 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42749c26f4a8a474f3dac076b80a1bfe71e89d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110446"
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