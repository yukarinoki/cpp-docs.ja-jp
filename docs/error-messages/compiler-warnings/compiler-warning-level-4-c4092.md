---
title: コンパイラの警告 (レベル 4) C4092
ms.date: 11/04/2016
f1_keywords:
- C4092
helpviewer_keywords:
- C4092
ms.assetid: 396ae826-a892-4327-bd66-f4762376d72b
ms.openlocfilehash: 675e6ccbc516734a405620aa74eaa04ff2f75087
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219990"
---
# <a name="compiler-warning-level-4-c4092"></a>コンパイラの警告 (レベル 4) C4092

> sizeof は ' unsigned long ' を返します

演算子のオペランドが **`sizeof`** 非常に大きいため、 **`sizeof`** が返されました **`unsigned long`** 。 この警告は、Microsoft 拡張機能 () で発生し [`/Ze`](../../build/reference/za-ze-disable-language-extensions.md) ます。 ANSI 互換 ( **`/Za`** ) では、代わりに結果が切り捨てられます。
