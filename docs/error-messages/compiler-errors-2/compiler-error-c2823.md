---
title: コンパイラ エラー C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 5f9b60499fd3c3bd5f06834e3c4f6482031066d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469759"
---
# <a name="compiler-error-c2823"></a>コンパイラ エラー C2823

> typedef のテンプレートは無効です。

テンプレートはでは許可されていない`typedef`定義します。

## <a name="example"></a>例

次の例では、C2823 を生成し、その修正方法を示しています。

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```