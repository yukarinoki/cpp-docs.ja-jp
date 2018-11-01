---
title: コンパイラの警告 (レベル 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 3a56e58d9bec1034a55f4e588dbddd0dba03f348
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437025"
---
# <a name="compiler-warning-level-1-c4076"></a>コンパイラの警告 (レベル 1) C4076

> '*型修飾子*': 型を使用することはできません'*typename*'

## <a name="remarks"></a>Remarks

型修飾子、かどうかは**署名**または**符号なし**、整数以外の型では使用できません。 *型修飾子*は無視されます。

## <a name="example"></a>例

次の例は C4076 が生成されます。これを修正するには、削除、**符号なし**型修飾子。

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```