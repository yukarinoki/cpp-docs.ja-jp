---
description: 詳細については、「コンパイラエラー C2159」を参照してください。
title: コンパイラ エラー C2159
ms.date: 11/04/2016
f1_keywords:
- C2159
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
ms.openlocfilehash: 045515ba964832de8821e048eac58b0ec507d830
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181216"
---
# <a name="compiler-error-c2159"></a>コンパイラ エラー C2159

2 つ以上のストレージ クラスが指定されています。

宣言に複数のストレージ クラスが含まれています。

次の例では C2159 が生成されます。

```cpp
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```
