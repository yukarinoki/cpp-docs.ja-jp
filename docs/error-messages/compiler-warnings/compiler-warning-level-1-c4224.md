---
title: コンパイラの警告 (レベル 1) C4224
ms.date: 11/04/2016
f1_keywords:
- C4224
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
ms.openlocfilehash: c58b003e43e74886c65d41e9abd6e49d15825653
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220094"
---
# <a name="compiler-warning-level-1-c4224"></a>コンパイラの警告 (レベル 1) C4224

非標準の拡張機能が使用されています: 仮パラメーター ' identifier ' は型として既に定義されています

この識別子は、以前はとして使用されていました **`typedef`** 。 これにより、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) で警告が発生します。

## <a name="example"></a>例

```cpp
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```
