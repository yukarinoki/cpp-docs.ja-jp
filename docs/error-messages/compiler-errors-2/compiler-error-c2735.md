---
description: 詳細については、「コンパイラエラー C2735」を参照してください。
title: コンパイラエラー C2735
ms.date: 11/04/2016
f1_keywords:
- C2735
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
ms.openlocfilehash: 75596e403c118d17ee286a579a347f6793c30bbd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123150"
---
# <a name="compiler-error-c2735"></a>コンパイラエラー C2735

' keyword ' キーワードは、仮パラメーターの型指定子では使用できません

キーワードは、このコンテキストでは無効です。

次の例では、C2735 が生成されます。

```cpp
// C2735.cpp
void f(inline int){}   // C2735
```
