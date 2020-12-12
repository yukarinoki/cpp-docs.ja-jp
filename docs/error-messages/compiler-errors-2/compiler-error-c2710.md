---
description: 詳細については、「コンパイラエラー C2710」を参照してください。
title: コンパイラエラー C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: ea9e4eaefa023362647f418be16a72ee14fbd044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320858"
---
# <a name="compiler-error-c2710"></a>コンパイラエラー C2710

' construct ': ' __declspec (修飾子) ' は、ポインターを返す関数にのみ適用できます

戻り値がポインターである関数は、を適用できる唯一のコンストラクトです `modifier` 。

次の例では、C2710 が生成されます。

```cpp
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```
