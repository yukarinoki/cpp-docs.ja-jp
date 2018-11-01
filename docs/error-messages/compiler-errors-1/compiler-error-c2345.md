---
title: コンパイラ エラー C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: ceb2a835ca94399f27640628105afcde986af1b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479106"
---
# <a name="compiler-error-c2345"></a>コンパイラ エラー C2345

align(value): 無効なアラインメント値です

[align](../../cpp/align-cpp.md) キーワードに渡した値が有効範囲外の値です。

次のコードでは C2345 が生成されます

```
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```