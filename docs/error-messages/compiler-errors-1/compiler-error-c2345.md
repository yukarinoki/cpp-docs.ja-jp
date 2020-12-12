---
description: 詳細については、「コンパイラエラー C2345」を参照してください。
title: コンパイラ エラー C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: 021c792a93fa27712087908ab30e1ddec84d08fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298410"
---
# <a name="compiler-error-c2345"></a>コンパイラ エラー C2345

align(value): 無効なアラインメント値です

[align](../../cpp/align-cpp.md) キーワードに渡した値が有効範囲外の値です。

次のコードでは C2345 が生成されます

```cpp
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```
