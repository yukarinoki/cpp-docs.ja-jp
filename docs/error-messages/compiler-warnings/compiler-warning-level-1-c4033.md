---
title: コンパイラの警告 (レベル 1) C4033 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4033
dev_langs:
- C++
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35df279ef7611a62ced5cb6291bdf17331850f0c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102685"
---
# <a name="compiler-warning-level-1-c4033"></a>コンパイラの警告 (レベル 1) C4033

'function': 値を返さなければいけません

この関数は値を返しません。 定義されていない値が返されます。

戻り値のない `return` を使用する関数は、型 `void`として宣言する必要があります。

このエラーは、C 言語コード用です。

次の例では C4033 が生成されます。

```
// C4033.c
// compile with: /W1 /LD
int test_1(int x)   // C4033 expected
{
   if (x)
   {
      return;   // C4033
   }
}
```