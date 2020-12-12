---
description: '詳細情報: コンパイラの警告 (レベル 1) C4033'
title: コンパイラの警告 (レベル 1) C4033
ms.date: 11/04/2016
f1_keywords:
- C4033
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
ms.openlocfilehash: 1d2455d62b3c375b0f1a863e6cfc3064f44e840a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325960"
---
# <a name="compiler-warning-level-1-c4033"></a>コンパイラの警告 (レベル 1) C4033

'function': 値を返さなければいけません

この関数は値を返しません。 定義されていない値が返されます。

**`return`** 戻り値を指定せずにを使用する関数は、型として宣言する必要があり **`void`** ます。

このエラーは、C 言語コード用です。

次の例では C4033 が生成されます。

```c
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
