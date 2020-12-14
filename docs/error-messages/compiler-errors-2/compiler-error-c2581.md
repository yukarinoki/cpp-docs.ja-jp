---
description: 詳細については、「コンパイラエラー C2581」を参照してください。
title: コンパイラ エラー C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: 9de6c48c2ade71af238cc62a0f92e642e1262d3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282121"
---
# <a name="compiler-error-c2581"></a>コンパイラ エラー C2581

' type ': 静的 ' operator = ' 関数は無効です

代入 ( `=` ) 演算子がとして正しく宣言されてい **`static`** ません。 代入演算子をにすることはできません **`static`** 。 詳細については、「 [ユーザー定義の演算子 (C++/cli)](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2581 が生成されます。

```cpp
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```
