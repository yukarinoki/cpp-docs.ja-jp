---
description: 詳細については、「コンパイラエラー C2823」を参照してください。
title: コンパイラ エラー C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 57dacaf144f23a1e8486d6a2849fffce0ff8be52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194671"
---
# <a name="compiler-error-c2823"></a>コンパイラ エラー C2823

> typedef テンプレートが正しくありません

テンプレートは定義では許可されていません **`typedef`** 。

## <a name="example"></a>例

次の例では、C2823 を生成し、その修正方法の1つを示しています。

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```
