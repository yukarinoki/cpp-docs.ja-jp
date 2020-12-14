---
description: 詳細については、「コンパイラエラー C2531」を参照してください。
title: コンパイラ エラー C2531
ms.date: 11/04/2016
f1_keywords:
- C2531
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
ms.openlocfilehash: 1ab3f18ca91f1dd77a1d06ee43adcb1cc52e05e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302236"
---
# <a name="compiler-error-c2531"></a>コンパイラ エラー C2531

' identifier ': ビットフィールドへの参照が無効です

ビットフィールドへの参照は許可されていません。

次の例では、C2531 が生成されます。

```cpp
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```
