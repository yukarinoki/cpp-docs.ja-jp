---
description: 詳細については、「コンパイラエラー C2289」を参照してください。
title: コンパイラ エラー C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: ba9af908af6defaccd6825ce3dad412ad6914c77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185961"
---
# <a name="compiler-error-c2289"></a>コンパイラ エラー C2289

同じ型の修飾子が 2 度以上使われています。

型宣言または定義で、型修飾子 ( **`const`** 、 **`volatile`** 、 **`signed`** 、または) が2回以上使用しているため **`unsigned`** 、ANSI 互換 (**/za**) でエラーが発生しています。

次の例では C2286 が生成されます。

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
