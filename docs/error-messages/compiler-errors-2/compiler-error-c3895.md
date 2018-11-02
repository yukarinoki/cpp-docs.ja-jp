---
title: コンパイラ エラー C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: 61dd280caa3c8c9b28dd77ecab2ed50ab9532d4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501285"
---
# <a name="compiler-error-c3895"></a>コンパイラ エラー C3895

'var': 型のデータ メンバーを 'volatile' にすることはできません

特定の種類の例では、データ メンバーの[リテラル](../../windows/literal-cpp-component-extensions.md)または[initonly](../../dotnet/initonly-cpp-cli.md)、することはできません[揮発性](../../cpp/volatile-cpp.md)します。

次の例では、C3895 が生成されます。

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```