---
description: 詳細については、「コンパイラエラー C2458」を参照してください。
title: コンパイラ エラー C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 7f705511c14da19b125868c1b34d907d6b5f220e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262855"
---
# <a name="compiler-error-c2458"></a>コンパイラ エラー C2458

' identifier ': 定義内で再定義します

クラス、構造体、共用体、または列挙型は、独自の宣言で再定義されます。

次の例では、C2458 が生成されます。

```cpp
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```
