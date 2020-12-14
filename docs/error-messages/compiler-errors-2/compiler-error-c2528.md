---
description: 詳細については、「コンパイラエラー C2528」を参照してください。
title: コンパイラ エラー C2528
ms.date: 11/04/2016
f1_keywords:
- C2528
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
ms.openlocfilehash: de07867f48843be76ff5b8d74dda9725b50a2560
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302180"
---
# <a name="compiler-error-c2528"></a>コンパイラ エラー C2528

' name ': 参照へのポインターが無効です。

参照へのポインターを宣言することはできません。 ポインターを宣言する前に、変数を逆参照してください。

次の例では、C2528 が生成されます。

```cpp
// C2528.cpp
int i;
int &ir = i;
int & (*irptr) = ir;    // C2528
```
