---
description: 詳細については、「コンパイラエラー C2372」を参照してください。
title: コンパイラ エラー C2372
ms.date: 03/23/2020
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: 9cf94e63e673ca226f3f9c3f1b4c3aa0a6bf8016
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174911"
---
# <a name="compiler-error-c2372"></a>コンパイラ エラー C2372

> '*identifier*': 再定義します。さまざまな種類の間接参照

識別子は、別の派生型で既に定義されています。

次の例では、C2372 が生成されます。

```cpp
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```
