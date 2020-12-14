---
description: 詳細については、「コンパイラエラー C2344」を参照してください。
title: コンパイラ エラー C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: 1ad4f1808f407a9f654f5bbf3a022c2dc7b0b3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234762"
---
# <a name="compiler-error-c2344"></a>コンパイラ エラー C2344

align(#): アラインメントは 2 の累乗でなければなりません

[align](../../cpp/align-cpp.md) キーワードを使用する場合は、渡す値は 2 の累乗である必要があります。

たとえば、3 は 2 の累乗ではないため、次のコードでは C2344 が生成されます。

```cpp
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```
