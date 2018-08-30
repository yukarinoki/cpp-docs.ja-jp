---
title: コンパイラの警告 (レベル 4) C4559 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4559
dev_langs:
- C++
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5743b33f62aa954c3765b729ab5c0297b20e32
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195577"
---
# <a name="compiler-warning-level-4-c4559"></a>コンパイラの警告 (レベル 4) C4559

> '*関数*': 再定義; 関数が _ _declspec (*修飾子*)

## <a name="remarks"></a>Remarks

2 番目の定義または宣言を追加し、関数が再定義または再宣言、 **_ _declspec**修飾子 (*修飾子*)。 これは、情報提供の警告です。 この警告を解決するには、定義を 1 つを削除します。

## <a name="example"></a>例

次の例では、C4559 が生成されます。

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```