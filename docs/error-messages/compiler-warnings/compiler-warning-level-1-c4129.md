---
title: コンパイラの警告 (レベル 1) C4129 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e02f38044180c45e221099d2874b7f8ff48d62f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098447"
---
# <a name="compiler-warning-level-1-c4129"></a>コンパイラの警告 (レベル 1) C4129

'character': 文字のエスケープ シーケンスを認識できません

`character`次の円記号 (\\) 文字または文字列の定数はない有効なエスケープ シーケンスとして認識します。 バック スラッシュは無視され、印刷されません。 円記号の後の文字が出力されます。

1 つの円記号を印刷するには、二重の円記号を指定 (\\\\)。

C++ 標準で 2.13.2 のセクションでは、エスケープ シーケンスについて説明します。

次の例では、C4129 が生成されます。

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```