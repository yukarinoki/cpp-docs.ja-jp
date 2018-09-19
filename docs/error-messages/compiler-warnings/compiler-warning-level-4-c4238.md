---
title: コンパイラの警告 (レベル 4) C4238 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4d5f358d08f81e6b8097140ad47d54f4b3b3fed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057029"
---
# <a name="compiler-warning-level-4-c4238"></a>コンパイラの警告 (レベル 4) C4238

使用される標準の拡張機能: 左辺値として使用されるクラスの右辺値

Microsoft の拡張機能、Visual C の以前のバージョンとの互換性 (**/Ze**) のコンテキストで、右辺値を暗黙的または明示的には、アドレスは、クラス型を使用することです。 場合によっては、次の例などの危険な指定できます。

## <a name="example"></a>例

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

この使用法、ANSI 互換のエラーが発生 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。