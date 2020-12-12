---
description: 詳細については、「コンパイラエラー C2379」を参照してください。
title: コンパイラ エラー C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 4b278040107a026ffd5f7bee79e709519647cb54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174716"
---
# <a name="compiler-error-c2379"></a>コンパイラ エラー C2379

昇格時に仮パラメーターの数値の型が異なります

指定されたパラメーターの型は、既定の昇格を通じて、前の宣言の型と互換性がありません。 これは、ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) ではエラーであり、Microsoft 拡張機能 (**/ze**) では警告が発生します。

次の例では、C2379 が生成されます。

```c
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
