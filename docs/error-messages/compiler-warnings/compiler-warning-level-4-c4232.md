---
description: '詳細情報: コンパイラの警告 (レベル 4) C4232'
title: コンパイラの警告 (レベル 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: 272fdcbc856ef5e86a8ff043b5aeab98a36413a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291416"
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
