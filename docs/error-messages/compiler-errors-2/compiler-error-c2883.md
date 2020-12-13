---
description: 詳細については、「コンパイラエラー C2883」を参照してください。
title: コンパイラ エラー C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 2ff905f5f1ca8fea4f175799e576e4538bbab164
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332343"
---
# <a name="compiler-error-c2883"></a>コンパイラ エラー C2883

' name ': 関数宣言は using 宣言で導入された ' identifier ' と競合しています。

関数を複数回定義しようとしました。 最初の定義は、宣言を使用して名前空間から作成されてい **`using`** ます。 2つ目はローカル定義です。

次の例では、C2883 が生成されます。

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
