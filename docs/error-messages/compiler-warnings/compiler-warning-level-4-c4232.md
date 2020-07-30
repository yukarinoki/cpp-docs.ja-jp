---
title: コンパイラの警告 (レベル 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: 6081acc4a64394c9122650da8b7f4147f724e5de
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219925"
---
# <a name="compiler-warning-level-4-c4232"></a>コンパイラの警告 (レベル 4) C4232

非標準の拡張機能が使用されています: ' identifier ': dllimport ' dllimport ' のアドレスは静的ではありません。 id は保証されていません

Microsoft extensions (/Ze) では、修飾子で宣言された関数のアドレスとして非静的値を指定でき **`dllimport`** ます。 ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では、エラーが発生します。

次の例では、C4232 が生成されます。

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
