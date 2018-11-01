---
title: コンパイラ エラー C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: 1344bd8bde532d2e813ca03e173b995e935c76b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661319"
---
# <a name="compiler-error-c2569"></a>コンパイラ エラー C2569

'EnumOrUnion': 列挙および共用体は基底クラスとして使用できません

指定された共用体、または列挙型を派生させる必要があります、クラスまたは構造体を union または列挙型を変更します。

次の例では、C2569 が生成されます。

```
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```