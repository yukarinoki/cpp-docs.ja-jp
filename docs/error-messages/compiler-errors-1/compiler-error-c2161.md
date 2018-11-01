---
title: コンパイラ エラー C2161
ms.date: 11/04/2016
f1_keywords:
- C2161
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
ms.openlocfilehash: 366e848d566dbcbf9414565de604aa722f758456
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519432"
---
# <a name="compiler-error-c2161"></a>コンパイラ エラー C2161

マクロ定義がトークン連結演算子 (##) で終わっています。

マクロ定義がトークン連結演算子 (##) で終わっています。

次の例では C2161 が生成されます。

```
// C2161.cpp
// compile with: /c
#define mac(a,b) a   // OK
#define mac(a,b) a##   // C2161
```