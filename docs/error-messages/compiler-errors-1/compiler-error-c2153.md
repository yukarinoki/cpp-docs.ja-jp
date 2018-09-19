---
title: コンパイラ エラー C2153 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2153
dev_langs:
- C++
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbb3283ff4d27b6c939434ac3df8f8c1febf0eb3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051426"
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