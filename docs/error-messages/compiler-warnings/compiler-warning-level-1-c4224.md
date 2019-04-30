---
title: コンパイラの警告 (レベル 1) C4224
ms.date: 11/04/2016
f1_keywords:
- C4224
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
ms.openlocfilehash: ed27e6ff63e3d5f3bab4f6d8d9639b84a5606ff2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367337"
---
# <a name="compiler-warning-level-1-c4224"></a>コンパイラの警告 (レベル 1) C4224

使用される標準の拡張機能: 仮パラメーター 'identifier' は型として定義された以前

識別子として使用されていた、`typedef`します。 これにより、ANSI 互換の警告 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

## <a name="example"></a>例

```
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```