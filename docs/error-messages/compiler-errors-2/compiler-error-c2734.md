---
description: 詳細については、「コンパイラエラー C2734」を参照してください。
title: コンパイラエラー C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c867ef8456be35d0e566056aedc4de43d16c8f14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123176"
---
# <a name="compiler-error-c2734"></a>コンパイラエラー C2734

' identifier ': extern でない場合は、const オブジェクトを初期化する必要があります

識別子が宣言され **`const`** ていますが、初期化されていません **`extern`** 。

次の例では、C2734 が生成されます。

```cpp
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```
