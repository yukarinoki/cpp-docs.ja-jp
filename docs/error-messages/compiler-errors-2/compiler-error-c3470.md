---
description: 詳細については、「コンパイラエラー C3470」を参照してください。
title: コンパイラ エラー C3470
ms.date: 11/04/2016
f1_keywords:
- C3470
helpviewer_keywords:
- C3470
ms.assetid: 170c7a9d-214d-41b1-8f15-d4a4fc38aaa5
ms.openlocfilehash: 1b8310a8bf7f4d69590baeebfc9e49ec01ad9d05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168437"
---
# <a name="compiler-error-c3470"></a>コンパイラ エラー C3470

'type' : クラスには、インデクサー (既定のインデックス付きプロパティ) および演算子 [] を同時に指定することはできません

型に既定のインデクサーと演算子 [] の両方を定義することはできません

## <a name="example"></a>例

次の例では C3470 が生成されます。

```cpp
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
