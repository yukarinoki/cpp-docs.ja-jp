---
title: コンパイラの警告 (レベル 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 1958aec4d6642188af1467ab4cab1ecf55c29165
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223318"
---
# <a name="compiler-warning-level-1-c4076"></a>コンパイラの警告 (レベル 1) C4076

> '*type modifier*': 型 '*typename*' と共に使用することはできません

## <a name="remarks"></a>解説

型修飾子はまたはであるかどうかにかかわらず、 **`signed`** **`unsigned`** 整数以外の型と共に使用することはできません。 *型修飾子*は無視されます。

## <a name="example"></a>例

次の例では、C4076 が生成されます。この問題を解決するには、型修飾子を削除し **`unsigned`** ます。

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
