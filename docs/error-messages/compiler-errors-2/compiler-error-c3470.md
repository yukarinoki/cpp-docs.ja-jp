---
title: コンパイラ エラー C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: 7d6c8627fe0904dd2fe81dd805d8f87bbebf29c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504457"
---
# <a name="compiler-error-c3470"></a>コンパイラ エラー C3470

'type' : クラスには、インデクサー (既定のインデックス付きプロパティ) および演算子 [] を同時に指定することはできません

型に既定のインデクサーと演算子 [] の両方を定義することはできません

## <a name="example"></a>例

次の例では C3470 が生成されます。

```
// C3470.cpp
// compile with: /clr
using namespace System;

ref class R {
public:
   property int default[int] {
      int get(int i) {
         return i+1;
      }
   }

   int operator[](String^ s) { return Convert::ToInt32(s); }   // C3470
};

int main() {
   R ^ r = gcnew R;
   // return r[9] + r["32"] - 42;
}
```