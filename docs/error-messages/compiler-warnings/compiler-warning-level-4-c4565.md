---
title: コンパイラの警告 (レベル 4) C4565 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c25f2f1fc16c6d45a7d1eddec8d3efe62db142f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211263"
---
# <a name="compiler-warning-level-4-c4565"></a>コンパイラの警告 (レベル 4) C4565

> '*関数*': 再定義; シンボルが以前に宣言されたを _ _declspec (*修飾子*)

## <a name="remarks"></a>Remarks

2 番目の定義または宣言の最初の定義または宣言とは異なり、ありませんでしたし、シンボルが再定義または再宣言、`__declspec`修飾子 (*修飾子*)。 これは、情報提供の警告です。 この警告を解決するには、定義を 1 つを削除します。

## <a name="example"></a>例

次の例では、C4565 が生成されます。

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```