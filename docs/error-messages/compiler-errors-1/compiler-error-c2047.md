---
description: 詳細については、「コンパイラエラー C2047」を参照してください。
title: コンパイラ エラー C2047
ms.date: 11/04/2016
f1_keywords:
- C2047
helpviewer_keywords:
- C2047
ms.assetid: 686a5a81-3857-4753-84a0-5c2e7149cbee
ms.openlocfilehash: 40df340017b134a3d2abe092478658f92142298d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175119"
---
# <a name="compiler-error-c2047"></a>コンパイラ エラー C2047

'default' が正しくありません。

キーワードは、 **`default`** ステートメント内でのみ使用でき **`switch`** ます。

次の例では C2047 が生成されます。

```cpp
// C2047.cpp
int main() {
   int i = 0;
   default:   // C2047
   switch(i) {
      case 0:
      break;
   }
}
```

考えられる解決策:

```cpp
// C2047b.cpp
int main() {
   int i = 0;
   switch(i) {
      case 0:
      break;
      default:
      break;
   }
}
```
