---
description: '詳細情報: コンパイラの警告 (レベル 1) C4076'
title: コンパイラの警告 (レベル 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 0bae49d3af23e499851fbf70fb24fdeb817ee03c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198259"
---
# <a name="compiler-warning-level-1-c4076"></a>コンパイラの警告 (レベル 1) C4076

> '*type modifier*': 型 '*typename*' と共に使用することはできません

## <a name="remarks"></a>解説

型修飾子はまたはであるかどうかにかかわらず、 **`signed`** **`unsigned`** 整数以外の型と共に使用することはできません。 *型修飾子* は無視されます。

## <a name="example"></a>例

次の例では、C4076 が生成されます。この問題を解決するには、型修飾子を削除し **`unsigned`** ます。

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
