---
title: コンパイラ エラー C3913
ms.date: 11/04/2016
f1_keywords:
- C3913
helpviewer_keywords:
- C3913
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
ms.openlocfilehash: 3a38f7bffd56f025510e092ad37b5f810cb11a9b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776952"
---
# <a name="compiler-error-c3913"></a>コンパイラ エラー C3913

既定のプロパティのインデックスを作成する必要があります。

既定のプロパティの定義が正しくありません。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md)」を参照してください。

次の例では、C3913 が生成されます。

```
// C3913.cpp
// compile with: /clr /c
ref struct X {
   property int default {   // C3913
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```