---
description: 詳細については、「コンパイラエラー C2334」を参照してください。
title: コンパイラ エラー C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: 875520c55550aa8507f28567b56b4fd83f53912a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234866"
---
# <a name="compiler-error-c2334"></a>コンパイラ エラー C2334

': または {' の前に予期しないトークンがあります。明らかに見える関数本体をスキップします

次の例では、C2334 が生成されます。 このエラーは、エラー C2059 の後に発生します。

```cpp
// C2334.cpp
// compile with: /c
// C2059 expected
struct s1 {
   s1   {}   // C2334
   s1() {}   // OK
};
```
