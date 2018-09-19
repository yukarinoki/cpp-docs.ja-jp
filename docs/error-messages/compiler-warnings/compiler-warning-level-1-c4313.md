---
title: コンパイラの警告 (レベル 1) C4313 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4313
dev_langs:
- C++
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df3600483ee5c6fe2ec0f9a339ec7ce5b94569af
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090926"
---
# <a name="compiler-warning-level-1-c4313"></a>コンパイラの警告 (レベル 1) C4313

'function': 書式指定文字列内の 'format specifier' が引数 ('type' 型) と競合しています。

指定された書式と渡された値が矛盾しています。 たとえば、32 ビット整数パラメーターを想定している修飾されていない %d 書式指定子に 64 ビット パラメーターを渡しました。 この警告は、コードの 64 ビット ターゲットのコンパイル時にのみ有効です。

## <a name="example"></a>例

次のコード サンプルは、64 ビット ターゲットのコンパイル時に C4313 を生成します。

```
// C4313.cpp
// Compile by using: cl /W1 C4313.cpp
#include <stdio.h>
int main() {
   int * pI = 0;
   printf("%d", pI);   // C4313 on 64-bit platform code
   // Try one of the following lines instead:
   // printf("%p\n", pI);
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information
}
```