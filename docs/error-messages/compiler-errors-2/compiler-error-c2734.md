---
title: コンパイラエラー C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: b4952f4705ad94133000fe6d84117cb04a5aa850
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206823"
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
