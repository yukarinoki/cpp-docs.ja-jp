---
title: コンパイラ エラー C2892
ms.date: 11/04/2016
f1_keywords:
- C2892
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
ms.openlocfilehash: 296224532b19d9ff85c8644aa653b6d842205213
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622821"
---
# <a name="compiler-error-c2892"></a>コンパイラ エラー C2892

ローカル クラス メンバー テンプレートことはできません。

Template 宣言されたメンバー関数は、関数で定義されているクラスでは有効ではありません。

次の例では、C2892 が生成されます。

```
// C2892.cpp
int main() {
   struct local {
      template<class T>   // C2892
      void f() {}
   };
}
```