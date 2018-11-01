---
title: コンパイラ エラー C3554
ms.date: 11/04/2016
f1_keywords:
- C3554
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
ms.openlocfilehash: 8bc9c465d16aea4714916fa6aa2942eb81c19015
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582300"
---
# <a name="compiler-error-c3554"></a>コンパイラ エラー C3554

'decltype' を他の型指定子と組み合わせることはできません

型指定子を使用して `decltype()` キーワードを修飾することはできません。 たとえば、次のコード フラグメントではエラー C3554 が生成されます。

```
int x;
unsigned decltype(x); // C3554
```