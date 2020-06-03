---
title: コンパイラの警告 (レベル 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 77efeae27a67ea844759fd9980801d3daf788e89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200260"
---
# <a name="compiler-warning-level-1-c4076"></a>コンパイラの警告 (レベル 1) C4076

> '*type modifier*': 型 '*typename*' と共に使用することはできません

## <a name="remarks"></a>解説

**符号付き**または**符号なし**のいずれの型修飾子でも、整数以外の型と共に使用することはできません。 *型修飾子*は無視されます。

## <a name="example"></a>例

次の例では、C4076 が生成されます。この問題を解決するには、**符号なし**の型修飾子を削除します。

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
