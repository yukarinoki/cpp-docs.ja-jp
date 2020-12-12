---
description: '詳細情報: コンパイラの警告 (レベル 1) C4224'
title: コンパイラの警告 (レベル 1) C4224
ms.date: 11/04/2016
f1_keywords:
- C4224
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
ms.openlocfilehash: f9632ec80ee845da6933be22a6e446ac5251257f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266404"
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
