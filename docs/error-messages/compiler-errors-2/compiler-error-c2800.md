---
description: 詳細については、「コンパイラエラー C2800」を参照してください。
title: コンパイラ エラー C2800
ms.date: 11/04/2016
f1_keywords:
- C2800
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
ms.openlocfilehash: 7adcb8e24bd7b3f3941260a9cceaa5157334ae8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297506"
---
# <a name="compiler-error-c2800"></a>コンパイラ エラー C2800

' operator operator ' をオーバーロードすることはできません。

次の演算子はオーバーロードできません。クラスメンバーアクセス ( `.` )、メンバーへのポインター ( `.*` )、スコープ解決 ( `::` )、条件式 ( `? :` )、および **`sizeof`** 。

次の例では、C2800 が生成されます。

```cpp
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```
