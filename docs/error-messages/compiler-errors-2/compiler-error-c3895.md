---
title: コンパイラ エラー C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: c4b1cad9ef48f1f16b411aab46e1bb9285d69ff3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768395"
---
# <a name="compiler-error-c3895"></a>コンパイラ エラー C3895

'var': 型のデータ メンバーを 'volatile' にすることはできません

特定の種類の例では、データ メンバーの[リテラル](../../extensions/literal-cpp-component-extensions.md)または[initonly](../../dotnet/initonly-cpp-cli.md)、することはできません[揮発性](../../cpp/volatile-cpp.md)します。

次の例では、C3895 が生成されます。

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```