---
title: コンパイラ エラー C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 1b3256efb6c0ff8236ba80a9ac681780f34fa8dd
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345647"
---
# <a name="compiler-error-c2379"></a>コンパイラ エラー C2379

仮パラメーターの数が昇格するときに別の種類

指定したパラメーターの型は、互換性のある、以前の宣言で型の既定のプロモーションが。 これは ANSI C でエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) と Microsoft の拡張機能の警告 (**/Ze**)。

次の例では、C2379 が生成されます。

```
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```