---
title: コンパイラ エラー C3155
ms.date: 11/04/2016
f1_keywords:
- C3155
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
ms.openlocfilehash: 85ee53dff7ae50717eabfd1ac6504ebb74deaa2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644363"
---
# <a name="compiler-error-c3155"></a>コンパイラ エラー C3155

属性は、プロパティ インデクサーでは使用できません。

インデックス付きプロパティの宣言が正しくありません。 詳細については、[方法: プロパティを使用して c++/cli CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)を参照してください。

## <a name="example"></a>例

次の例では、C3155 が生成されます。

```
// C3155.cpp
// compile with: /clr /c
using namespace System;
ref struct R {
   property int F[[ParamArray] int] {   // C3155
   // try the following line instead
   // property int F[ int] {   // OK
      int get(int i) {
         return 0;
      }
   }
};
```