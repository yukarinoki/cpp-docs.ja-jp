---
description: 詳細については、「コンパイラエラー C2570」を参照してください。
title: コンパイラ エラー C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: faebc117991262c8fff94ef75f18d6e59c884315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209023"
---
# <a name="compiler-error-c2570"></a>コンパイラ エラー C2570

' identifier ': 共用体に基底クラスを含めることはできません

共用体は、クラス、構造体、または共用体から派生します。 これは認められていません。 代わりに、派生型をクラスまたは構造体として宣言してください。

次の例では、C2570 が生成されます。

```cpp
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
