---
title: コンパイラ エラー C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: 54d501d43652bb8e54092d44042a9525ef6f708f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160914"
---
# <a name="compiler-error-c2710"></a>コンパイラ エラー C2710

'construct': '__declspec(modifier)' は、ポインターを返す関数のみに適用できます

関数の戻り値は、ポインターが唯一の構造体を`modifier`適用できます。

次の例では、C2710 が生成されます。

```
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```