---
description: 詳細については、「コンパイラエラー C2021」を参照してください。
title: コンパイラエラー C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 823d9c3d42f1df7bc6f6f398dafd804daef76110
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175639"
---
# <a name="compiler-error-c2021"></a>コンパイラエラー C2021

'character' でなく指数の値が必要です

浮動小数点定数の指数として使用されている文字が、有効な数値ではありません。 範囲内の指数を使用するようにしてください。

## <a name="examples"></a>例

次の例では、C2021 が生成されます。

```cpp
// C2021.cpp
float test1=1.175494351E;   // C2021
```

考えられる解決策:

```cpp
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```
