---
title: コンパイラ エラー C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: eeb7da509ffb1b8c408763c79d471586eb94f383
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605934"
---
# <a name="compiler-error-c2153"></a>コンパイラ エラー C2153

16 進型定数は、少なくとも 1 つの 16 進数字をいる必要があります。

16 進定数 0 x、0 X、および \x が無効です。 少なくとも 1 つの 16 進数字が従う必要があります x または X。

次の例では、C2153 が生成されます。

```
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```