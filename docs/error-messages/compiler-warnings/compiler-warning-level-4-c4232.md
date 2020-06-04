---
title: コンパイラの警告 (レベル 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: c0e79dfa4564960a5660f0932b142b436370ac05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173921"
---
# <a name="compiler-warning-level-4-c4232"></a>コンパイラの警告 (レベル 4) C4232

非標準の拡張機能が使用されています: ' identifier ': dllimport ' dllimport ' のアドレスは静的ではありません。 id は保証されていません

[Microsoft extensions (/Ze)] では、 **dllimport**修飾子で宣言された関数のアドレスとして非静的値を指定できます。 ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では、エラーが発生します。

次の例では、C4232 が生成されます。

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
