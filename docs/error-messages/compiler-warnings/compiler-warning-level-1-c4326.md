---
title: コンパイラの警告 (レベル 1) C4326 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cee18a9ccc807370cf2fb40748939f211a4ba52f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211005"
---
# <a name="compiler-warning-level-1-c4326"></a>コンパイラの警告 (レベル 1) C4326

> 型を返す '*関数*'は'*type1*' の代わりに '*type2*'

## <a name="remarks"></a>Remarks

返される型を以外の関数*type1*します。 たとえばを使用して[/Za](../../build/reference/za-ze-disable-language-extensions.md)、**メイン**を返しませんでした、 **int**。

## <a name="example"></a>例

次の例では、C4326 を生成し、その修正方法を示しています。

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```