---
title: コンパイラ エラー C2289 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2289
dev_langs:
- C++
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5bf284ee7ada4f32772b5f65ed0b983e08e5988
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067612"
---
# <a name="compiler-error-c2289"></a>コンパイラ エラー C2289

同じ型の修飾子が 2 度以上使われています。

型の宣言または定義で、型修飾子 (`const`、 `volatile`、 `signed`、または `unsigned`) が 2 回以上使用されています。ANSI 互換のオプション (**/Za**) を指定している場合はエラーになります。

次の例では C2286 が生成されます。

```
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```